
# WebForms, Workflows, and Content Moderation

When you start working with Drupal you will quickly jump into the 'Administration/Structure/Content Types' part of the GUI menu system.  There you will find the initially installed Article and Basic Page content types.  Elsewhere we talk about how to [make the other content types you may want to add.](../book/contenttypes.md) As you work with Drupal you will then go to 'Administration/Content' and select which you plan to work on for any given set of pages you want to create.  Pick one and the first you will see is a form where you can put in some content.  What you see on that form is probably already very familiar to you because as a content type is set up of the [first tasks is to say what 'fields' of information that particular content type should contain.](../book/contenttype.md#add-content-type)  By george, you already know how to use a form in Drupal.  Infact, if you put some fields you wanted into one of those content types you actually created or defined a classic Drupal form.

The first section of this page is all about extra things you might consider adding to the 'Classic' type of Drupal forms.  Following that is another section on a 'Webform' series of tools that are more specifically devoted to Form Management as a separate application need for certain types of websites we might develop.

## Classic Forms

### Forms Steps module

Forms are a point of input.  Too much can overwhelm.  Since you might aim to pretty up the forms associated with some node where you want an authorized end-user to contribute some content, you want to keep it clean and simple.  One way to gather this input would be to have a sequence of input pages rather than a giant one.  Think of the [Entity Form Steps module](https://www.drupal.org/project/entity_form_steps) as a way to break things into a series of input step pages.  [See its simple set up.](https://www.drupal.org/files/project-images/Screen%20Recording%202022-05-23%20at%201.50.12%20PM.gif)  

`composer require drupal/forms_steps`<br>
`drush en forms_steps`

### Forms Mode Control module

The form steps module above may combine with the [form mode control module](https://www.drupal.org/project/form_mode_control) to offer even more friendly end-user input.  You can use the form mode control module to control how the fields are displayed in the edit form of content such as nodes and taxonomy terms.  Once you install and enable the form_mode_control module, go to your 'admin' menu and the 'structure' tab.  There is a 'Display Mode' item on the menu and you select that.  Now, instead of just a display view mode control option you have a 'Form modes' option.  And you can add a form mode or configure ones you have.  What is especially cool about this contributed module is that it works on all the various entity types that include the basic 'form' from core Drupal.  So you can use it on Blocks, Content, Taxonomy, etc.  The first two might be the most common use cases, but there is value in the others as well.

`composer require drupal/form_mode_control`<br>
`drush en form_mode_control`


[Make a node out of a form submission](https://github.com/owenmorrill/subtonode)

User Contribution Entry Using Traditional Form/Display approach by adding "Form Modes" to the form option via a contributed module:

For something like Taxonomy you see how to get to the "Manage form display" in the operations area with the pull down on the right. 


The 'Content' form might have a slimmed down version for end-users to input into a simplified form and a richer form for an editor to grab and work that contribution into a clean node.  In the example below you just hit the 'Add form mode' to create a new one; and I have already done one I called 'Contributing User' and another called 'Full'.  Try to keep the names you use descriptive but generic enough to use in different content types or even with different entity types. 


Once you have added them to a content entity you will see the addition of a "CUSTOM DISPLAY SETTINGS" box at the bottom of the form.  And within it, you will see the names of the different form modes you created.  Then just use it like you do with different 'display modes'.


composer require 'drupal/formblock:^2.0@beta'

****************

## Webform Module Series

If you have a substantial use case requirement around forms, you will want to look at the [webform module;](https://www.drupal.org/project/webform) and its numerous additional components.  This is probably one of the best documented series of modules in all of Drupal.  [Get an overview here.](https://www.youtube.com/watch?v=VncMRSwjVto)

As exciting and powerful as this webform module series is, there is a little 'watch out' gotcha associated with it.  Remember, this is NOT your standard Drupal input form or a tweaked version of it like offered earlier.  Rather, it is a form system first and it has the opportunity to interface with Drupal.  On the incorporate it level, that is straight forward.  On the get data out of the form and into standard Drupal 'fields' it is more challenging.  Rather than fields, Webform stands separately by calling them 'elements'.  The easiest way to wrap your head around this is to [watch this short video on setting up a simple form which demonstrates the use of elements to define what your form contains.](https://www.youtube.com/watch?v=fr3kTiYKNls)



### Webform base

The base module has a whole variety of features within it.  But because this series is so well documented, it makes no sense to repeat all that here; just [jump to this great overview of all that it does and works with.](https://www.drupal.org/docs/contributed-modules/webform/webform-features)

`composer require drupal/webform`<br>
`drush en webform`

### Webform Cards

One thing to call out is how using Webforms with a Cards set up is like a step flow.  You might think of the [Webform Cards module as the 'step' counter-part](https://www.youtube.com/watch?v=bDugc2gWQnw) of a traditional stepped form noted earlier, but on steroids.  It you start getting into lots of steps the user experience of the traditional approach can bog down.  But the Webforms Cards approach is a client-side JavaScript Webform Wizard approach that then talks to Drupal; thus fast on the screen refreshes as you move through pages.  One of the very valuable concepts of stepping through a form is that you can make subsequent steps 'conditional'.  Here is an example of [using conditional logic to create a preferred content method and then either asking for a phone number or an email address depending on which the user preferred.](https://www.youtube.com/watch?v=ic4wu-iZd4Y)


***********

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


***************




[Using Taxonomy Terms in Webform](https://www.webwash.net/taxonomy-terms-as-webform-options-in-drupal/)

If hierarchy is an issue, try --
composer require 'drupal/shs:^1.0@alpha'


Workflow add-on modules that are worth considering (But first be sure to check the Content Moderation and Workflow basics in core (discussed shortly):

Make [a multi-page flow work blazing fast with JavaScript Convert automatically](https://www.youtube.com/watch?v=bDugc2gWQnw)

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


<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)



