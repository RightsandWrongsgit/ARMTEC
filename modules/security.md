
- Modules to provide site Security -

Security Kit Module:
This module has protections against a wide range of threats.  Your host may also cover a lot of security and the use of a container deployment may also.  So you don't want to blindly go into this but the Security Kit Module is one you should consider.

Here is a detailed review of it - https://www.droptica.com/blog/security-kit-drupal-module-overview/









































First Line of Defense:  
Make users sign up for an account before they can upload anything.
Use of a separate file system for anonymous upload contributions. Read more here:
https://www.drupal.org/psa-2016-003


Antibot Module:
This basically aims to protect against your site being flooded by a bot pumping in comments or signup forms or other things where you take inputs.  Besides installing and enabling it, you need to point it to those input form ids and then it should be good to go.

composer require 'drupal/antibot
drush en antibot





































Honeypot Module:
This is very similar to the Antibot module, so don't install both.  One thing to note is that this is by Jeff Geerling who is a pretty highly skilled and recognized community member.  Other than that try a search or some Slack conversations to see if you have preference of one versus the other. 

composer require 'drupal/honeypot
drush en honeypot









































Captcha type modules: 
There are a bunch of specific modules that put the CAPTCHA type of filter in front of user form submissions; e.g. pick the pictures with boat, type in the funny looking letters and numbers you see.  Think of using these as a back up line of defense.  First make it required that a user have an account to upload anything.  But the user sign up is a form, so to avoid flooding it next put in the antibot or honeypot type of javascript dependent filter but note to users they need javascript OR select the alternative of a Captacha screening.  Could be some work to get them to work together nicely but it is an option.

composer require drupal/captcha
drush en captcha



<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)

