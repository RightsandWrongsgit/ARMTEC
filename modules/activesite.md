
# Manage an Active Site

## [Visitors Module](https://www.drupal.org/project/visitors)

Would it be cool to know all this about your site?<br>

<img src="../modules/images/visitors.png"  width="400">


`composer require drupal/visitors`<br>
`drush en visitors`

<br>

## [FAQ Field Module](https://www.drupal.org/project/faqfield)

Fundamentally this is a simple accordion that drops in on all your content types if you add this field to that content type.  You might put it on any given content type to make the field available to put helpful questions and answers directly in the context of the associated page. When you configure it, you can do things like set a zero default so it doesn't show up at all unless populated and set the available Q and A's to unlimited so you can put in all you want.  Because the answer block can use the various HTML formatting options, you can not only go wild with your WYSIWYG editor including images or any other tools you have folded into your CKEditor.   If, when you set it up and are asked for a Title, by putting in FAQ you get the common use but you can do other titles as you put it on a content type and have say a picture accordion or some other options for usage. 

`composer require drupal/faqfield`<br>
`drush en faqfield`

<br>

## [Website Feedback Module](https://www.drupal.org/project/website_feedback)

Don't know about you, but I always worry a link is broken, I have a typo, or I was blantly wrong about something.  This module provides the way you can get feedback from your website users.  The idea that they can screen capture it is cool.  And if it doesn't give you a specific page node location out of the box, you can just bring [tokens](../modules/development.md#token-module) play with it.

`composer require drupal/website_feedback`<br>
`drush en website_feedback`

<br>

## [Webform Module](https://www.drupal.org/project/webform)

If you want to do more than monitor your visitors, like interact and engage them, survey them, collect more about them, you want to install the Webform module.  It is extensive and you should go to the Drupal.org site to look at the module.  In addition, there are extensive videos on they many uses and features of this module; some of which you can link to right off the module page.  See [Webform and Workflows control for more.](../modules/forms.md#webform-module-series)

<br>

## [XML Site Map module](https://www.drupal.org/project/xmlsitemap)

Search engine performance is impacted by a site map conforming to the sitemaps.org specifications.  So use this module to generate and submit the map to the search engines. 

`composer require drupal/xmlsitemap`<br>
`drush en xmlsitemap`

<br>

## [Metatag Module](https://www.drupal.org/project/metatag)

This is the base module with over 250 metatag control functions across search, google+, Facebook, Dublin Core, etc.    Because it Schema Metatag has a dependency upon it, and that module is noted next, install it as indicated and this will be added automatically (may need to be independently enabled). 

`composer require drupal/metatag`<br>
`drush en metatag`

<br>

## [Schema Metatag Module](https://www.drupal.org/project/schema_metatag)

You obviously want to enhance SEO performance if you are bothering to use Google Analytics, so you probably want to add a way to manage Metatags better.  As an enhancement to the basic Metatag Module, this Schema_Metatag module will press your installing and enabling the former as well.

`composer require drupal/schema_metatag`<br>
`drush en schema_metatag`

<br>

## [Views Bulk Operations Module](https://www.drupal.org/project/views_bulk_operations)

Once you are working with content, you may have repetitive actions you want to carry out.  A simple action might be you are done with development where you have generated mock content with Devel Generate and now want to get rid of it.  Instead of individually deleting 50 generated nodes, leverage the Bulk Operations.

`composer require drupal/views_bulk_operations`<br>
`drush en views_bulk_operations`

<br>

## [DIFF Module](https://www.drupal.org/project/diff)

This module can be helpful to the content editors.  You should set it up so it has an association with that Role as you do permissions.  What it will do is allow you to put above/below or side-by-side comparisons of versions as you make revisions.  So it is an enhancement of the core revision capabilities in that it allows you do more than just revert to prior version but actually examine the differences.

`composer require drupal/diff`<br>
`drush en diff`

<br>

 ## File delete module
[Sometimes you need to clean up content and using a fancy file delete module gives the editors much better control.](https://www.webwash.net/delete-files-instantly-using-fancy-file-delete-in-drupal/)

`composer require drupal/file_delete`
`drush en file_delete`

<br>


## [Override Node Options module](https://www.drupal.org/project/override_node_options)

Drupal has a pretty powerful role permission capability out of the box.  You can set up roles, grant them access to various things at an already pretty granular level.  But, sometimes you might want to have a trusted content person control publishing, promoting, revisioning settings, and stuff even a little deeper so some bright person added this contributed module to do so.  Things like this …

`composer require drupal/override_node_options`<br>
`drush en override_node_options`







<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)
