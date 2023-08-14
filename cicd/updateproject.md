
# Project Administration
## Update master systems

This provides instructions to update Lando and Platform.sh project major versions.  It is principly a set of notes for the CI/CD Workflow Project author to do updates to the master project environments on their Lando local machine and after doing so, updating the hosted 'main' that people clone for their easy start Drupal site.

## Lando-update PHP version

Run [lando](https://docs.lando.dev/) in the local copy of the project:
`lando init`

Find the lando yml file and edit the PHP version line to the new one you want:
`# .lando.yml
services:
  appserver:
    type: php:8.1 #edit this line`

Destroy and rebuild after making that php-change:
`lando destroy -y && lando start`

## Update Drupal Core
(You are doing this from you local machine in the CI/CD Workflow Project directory.)
(You have confirmed on the bottom of VSCode that the local is talking directly to 'main' as it is connected to the host copy.)

The following steps make sure the directories are writable, extends time to handle slower connections, updates the core locally in Lando, and get the updates into the Platform.sh host:<br> 
&nbsp;&nbsp;&nbsp;&nbsp;`lando start`<br>
&nbsp;&nbsp;&nbsp;&nbsp;`chmod u+w web/sites/default`<br>
&nbsp;&nbsp;&nbsp;&nbsp;`lando composer config --global process-timeout 2000`<br>
&nbsp;&nbsp;&nbsp;&nbsp;`lando composer update "drupal/core-*" --with-all-dependencies`<br>
&nbsp;&nbsp;&nbsp;&nbsp;`git push -u platform update`<br>
&nbsp;&nbsp;&nbsp;&nbsp;`platform e:activate -y`<br>

<sup><sub>NOTE: Make sure Platform CLI is installed and SSH connection established.</sub></sup><br>

<br>
<br>
<br>

[Back to CI/CD Project Documentation List](../book/drupalcicd.md#i-kind-of-need-to-know-how-it-works)
