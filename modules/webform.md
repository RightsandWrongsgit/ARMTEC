
– WebForms, Workflows, and Content Moderation --

User Contribution Entry Using Traditional Form/Display approach by adding "Form Modes" to the form option via a contributed module:

This form steps module may combine with the form mode control module to offer the end-user input I want in several places;  this stepping making it easier on the end-user.
composer require 'drupal/forms_steps:^1.5'



composer require 'drupal/form_mode_control:^2.0@RC'

drush en form_mode_control

















Once you install and enable the form_mode_control module, go to your 'admin' menu and the 'structure' tab.  There is a 'Display Mode' item on the menu and you select that.  Now, instead of just a display view mode control option you have a 'Form modes' option.  And you can add a form mode or configure ones you have.



















What is especially cool about this contributed module is that it works on all the various entity types that include the basic 'form'  from core Drupal.  So you can use it on Blocks, Content, Taxonomy, etc.  The first two might be the most common use cases, but there is value in the others as well.















For something like Taxonomy you see how to get to the "Manage form display" in the operations area with the pull down on the right. 


The 'Content' form might have a slimmed down version for end-users to input into a simplified form and a richer form for an editor to grab and work that contribution into a clean node.  In the example below you just hit the 'Add form mode' to create a new one; and I have already done one I called 'Contributing User' and another called 'Full'.  Try to keep the names you use descriptive but generic enough to use in different content types or even with different entity types. 






















Once you have added them to a content entity you will see the addition of a "CUSTOM DISPLAY SETTINGS" box at the bottom of the form.  And within it, you will see the names of the different form modes you created.  Then just use it like you do with different 'display modes'.





composer require 'drupal/formblock:^2.0@beta'



__________________________________________________________________________
composer require 'drupal/webform:^6.0'
drush en webform

composer require 'drupal/webform_content_creator:^2.0'
drush en webform_content_creator

composer require 'drupal/webform_node_element:^1.1'
composer require 'drupal/webform_node_element:1.x-dev@dev'   (Drupal 9)
drush en webform_node_element


composer require 'drupal/form_mode_manager:^2.0@RC'
If having trouble with other approaches to user inputs via the form display approach, you might try this.  The D9 version is nearing final testing. 

composer require 'drupal/config_entity_revisions:^1.6'
drush en config_entity_revisions
(https://www.youtube.com/watch?v=YKr-vLCRaJo)


Make a node out of a form submission:
https://github.com/owenmorrill/subtonode



Using Taxonomy Terms in Webform:

Ivan's overview
https://www.webwash.net/taxonomy-terms-as-webform-options-in-drupal/

If hierarchy is an issue, try --
composer require 'drupal/shs:^1.0@alpha'


Workflow add-on modules that are worth considering (But first be sure to check the Content Moderation and Workflow basics in core (discussed shortly):

Make a multi-page flow work blazing fast with JavaScript Convert automatically:

https://www.youtube.com/watch?v=bDugc2gWQnw

drush en inline form errors
composer require clientside validation
composer require webform clientside validation
composer require webform cards


Operational:
webform config ignore
webform config key value (experimental)
webform views
composer require 'drupal/webform_views:^5.0@alpha'
webform submission views token field (drupal 8 but not 9 yet)


