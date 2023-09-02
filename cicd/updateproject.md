
# Project Administration
## Update master systems

This provides instructions to update Lando and Platform.sh Drupal CI/CD project major versions.  It is principly a set of notes for the CI/CD Workflow Project author to do updates to the master project environments on their Lando local machine and after doing so, updating the hosted 'main' that people clone for their easy start Drupal site.

## Start with a Backup

It makes sense to be sure whatever you have in place that you are happy with is [backed Up on Platform.sh before you do any updates.](../cicd/basebeforesplit.md#lets-do-a-platformsh-backup) 

## General Drupal Requirements
[Drupal.Org link](https://www.drupal.org/docs/getting-started/system-requirements)

## Composer-update version
[Version requirements](https://www.drupal.org/docs/system-requirements/composer-requirements)<br>

How you update..<br>
`composer self-update`

## PHP version

### Version you are on...

#### Drupal
Check under "Status report": /admin/reports/status

Or run `drush core:status` 

#### Platform.sh

You can look at the PHP and/or Composer versions that Platform.sh is using by examining the copy of `platform.app.yml` in your local copy of the project; right near the `composer.json` file.

<img src="../cicd/captures/platformshcomposerphpversions.png"  width="500">

### Version you are moving to...

[First check the Host PHP version cabability before moving it forward too far!](https://www.drupal.org/docs/getting-started/system-requirements/php-requirements)
<font size="4" color=yellow> don't move forward more than the Drupal version you are updating to can run.</font> 

#### Platform.sh

Edit the copy of `platform.app.yml` in your local copy of the project; right near the `composer.json` file. Then do your `Git commit`, `Git sync` in your VSCode IDE to get it up to the host. 

<img src="../cicd/captures/platformshcomposerphpversions.png"  width="500">

#### Lando

Run [lando](https://docs.lando.dev/) in the local copy of the project:
`lando init`

Find the lando yml file and edit the PHP version line to the new one you want:<br>
`# .lando.yml
services:
  appserver:
    type: php:8.1 #edit this line`

Destroy and rebuild after making that php-change:<br>
`lando destroy -y && lando start`

## Update Drupal Core
<font color=yellow>(On your local machine in the CI/CD Workflow Project directory.)</font><br>
<font color=yellow>(Confirmed 'main' on the bottom of VSCode, connected to the host copy.)</font><br>
<font color=yellow>(If in doubt, first do a `composer update --dry-run`)</font>

The following steps make sure the directories are writable, extends time to handle slower connections, updates the core locally in Lando, and get the updates into the Platform.sh host:<br> 
&nbsp;&nbsp;&nbsp;&nbsp;`lando start`<br>
&nbsp;&nbsp;&nbsp;&nbsp;`chmod u+w web/sites/default`<br>
&nbsp;&nbsp;&nbsp;&nbsp;`lando composer config --global process-timeout 2000`<br>
&nbsp;&nbsp;&nbsp;&nbsp;`lando composer update "drupal/core-*" --with-all-dependencies`<br>
&nbsp;&nbsp;&nbsp;&nbsp;`git push -u platform update`<br>
&nbsp;&nbsp;&nbsp;&nbsp;`platform e:activate -y`<br>

<sup><sub>NOTE: Make sure Platform CLI is installed and SSH connection established.</sub></sup><br>

## Update Drush

Sometimes updating Drush will overcome issues occuring from the Drupal update.

`composer require drush/drush:^11`


## I screwed up
## Back me out
<font color=yellow>This assumes the local lando Drupal update isn't running right AND that you haven't pushed the update to the host (Platform.sh and GitHub)!</font>
You are going to flush the whole local copy of the project and simply clone the clean copy you have in the repository to restore the local.

a) Go to the project in your VSCode IDE at its top level.  Then do a `shift-command-P` to pull up the command bar where you will start typing `Gitclone <project name>` to pull it back local.

b) Go to the terminal in VSCode and type `lando start` to make sure the project that was restored is what you expected.  

c) Make your next move!

<font color=yellow>This assumes the local lando Drupal update isn't running right AND you also made the error of pushing the bad update to the host (Platform.sh and GitHub)!</font>
Nearly the same as if you hadn't pushed it to Platform.sh EXCEPT <font color=yellow>first you are going to restore the backup you made on Platform.sh</font> then you are going to flush the whole local copy of the project and simply clone the clean backup copy you have in the repository to restore the local.

a) Go toward the end of the section discussing [back Up on Platform.sh ](../cicd/basebeforesplit.md#lets-do-a-platformsh-backup) and you will see the "Restore" option on the image which you can select and bring that copy back live. Give it a chance to run, especially if it happens to be large.

b) Go to the project in your VSCode IDE at its top level.  Then do a `shift-command-P` to pull up the command bar where you will start typing `Gitclone <project name>` to pull it back local.

c) Go to the terminal in VSCode and type `lando start` to make sure the project that was restored is what you expected.  

d) Make your next move!

<br>
<br>

## Some possibly good references to reveiw

[A guide, explaining how to upgrade a Drupal application to PHP 8 keeping backward compatibility with PHP 7. This is to allow deploying to production without the need to synchronize with the update of the servers to PHP 8.](https://metadrop.net/en/articles/updating-drupal-php-8)<br>


## Working Note Material

Got to the Platform.sh "current" version deploy options on their site; it will likely offer more than one so confirm what your intended upgrade path plan is (e.g. Drupal 9 to Drupal 10, some minor 10.0 to 10.2 upgrade, etc.).  Don't hit the deploy button there; rather, follow the link they provide to the Git Repository for that version. 

### Drupal, the application
Pop into the `composer.json` file for the upgrade target in that Git repository and in it should find lines near the top that look something like this ...

```
"require": {
    "composer/installers": "^2.0",
    "drupal/core-composer-scaffold": "^10.0",
    "drupal/core-project-message": "^10.0",
    "drupal/core-recommended": "^10.0",
    "drupal/redis": "^1.6",
    "drush/drush": "^12",
    "platformsh/config-reader": "^2.4"
```
These are showing the Drupal project versions.  Note the ^ symbol is implying... “Compatible with version”, will update you to all future minor/patch versions, without incrementing the major version. ^1.2.3 will use releases from 1.2.3 to <2.0.0

So you know the Drupal version is 10, up to but excluding 11.  You know the Drush version is 12 up to but excluding 13.

### Platform.sh, the host environment

In that same Git repository, look for the file `.platform.app.yaml` and open it up.  You should see lines like these...
```
# The name of this app. Must be unique within a project.
name: 'drupal'

# The runtime the application uses.
type: 'php:8.1'

dependencies:
    php:
        composer/composer: '^2.1'

runtime:
    # Enable the redis extension so Drupal can communicate with the Redis cache.
    extensions:
        - redis
        - sodium
        - apcu
        - blackfire
```
You see that the php version is 8.1 and that the composer version is 2.1 up to but excluding 3.


<br><br>
<br>

[Back to CI/CD Project Documentation List](../book/drupalcicd.md#i-kind-of-need-to-know-how-it-works)
