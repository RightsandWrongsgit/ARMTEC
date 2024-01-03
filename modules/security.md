
# Site Security

## First Line of Defense

Make users sign up for an account before they can upload anything.
Use of a separate file system for anonymous upload contributions. [Read more here:](https://www.drupal.org/psa-2016-003

## Password Policy module

The [Password Policy module](https://www.drupal.org/project/password_policy) offers you the opportunity to add more specific requirements to what sort of password your website will find acceptable.  For example the minimum number of characters, mix of alpha and number and symbols, et.

## Security Review module

It might be worth your trouble trying the [Security Review module](https://www.drupal.org/project/security_review) to get a perspective on your specific vulnerabilities.  The good thing about this module is that it doesn't automatically make changes.  Rather think of its results as a checklist and its resources providing ways to manually secure your site. 

## Hacked module

This one takes an interesting approach.  The [Hacked module](https://www.drupal.org/project/hacked) basically works by redownloading your modules and checking what is installed against that to see if unexpected changes imply you have been hacked.  Presenting a "Difference" view sort of like a typical Git management approach you can see what has changed.  Again, it don't just go in an start doing things, more about finding things because it could be you have a module where a change is nothing more than a patch you applied.

## Security Kit module

The [Security Kit module](https://www.drupal.org/project/seckit) has protections against a wide range of threats.  Your host may also cover a lot of security and the use of a container deployment may also.  So you don't want to blindly go into this but the Security Kit module is one you should consider.  [For a detailed review...](https://www.droptica.com/blog/security-kit-drupal-module-overview/)

# Antibot module

The [Antibot module](https://www.drupal.org/project/antibot) basically aims to protect against your site being flooded by a bot pumping in comments or signup forms or other things where you take inputs.  Besides installing and enabling it, you need to point it to those input form ids and then it should be good to go.

`composer require drupal/antibot`<br>
`drush en antibot`

# Honeypot module

The [HoneyPot](https://www.drupal.org/project/honeypot) is very similar to the Antibot module, so don't install both.  One thing to note is that this is by Jeff Geerling who is a pretty highly skilled and recognized community member.  Other than that try a search or some Slack conversations to see if you have preference of one versus the other. 

`composer require drupal/honeypot`<br>
`drush en honeypot`

# Captcha type modules 

There are a bunch of specific modules that put the CAPTCHA type of filter in front of user form submissions; e.g. pick the pictures with boat, type in the funny looking letters and numbers you see.  Think of using these as a back up line of defense.  First make it required that a user have an account to upload anything.  But the user sign up is a form, so to avoid flooding it next put in the antibot or honeypot type of javascript dependent filter but note to users they need javascript OR select the alternative of a Captacha screening.  Could be some work to get them to work together nicely but it is an option.

`composer require drupal/captcha`<br>
`drush en captcha`



<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)

