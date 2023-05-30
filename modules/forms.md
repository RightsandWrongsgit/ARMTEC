
# Forms and WebForms

Forms are a fundamental part of Drupal.  You can think of what you put into Drupal when setting up or working with a content type as basically using a Drupal form; via the [Form API.](https://www.drupal.org/docs/drupal-apis/form-api/introduction-to-form-api)  You set up fields in Drupal and you tell it about them with a form.  You tell Drupal what content you want to display basically using a classic PHP form.

When you start working with Drupal you will quickly jump into the 'Administration/Structure/Content Types' part of the GUI menu system.  There you will find the initially installed Article and Basic Page content types.  Elsewhere we talk about how to [make the other content types you may want to add.](../book/contenttypes.md) As you work with Drupal you will then go to 'Administration/Content' and select which you plan to work on for any given set of pages you want to create.  Pick one and the first you will see is a form where you can put in some content.  What you see on that form is probably already very familiar to you because as a content type is set up of the [first tasks is to say what 'fields' of information that particular content type should contain.](../book/contenttype.md#add-content-type)  By george, you already know how to use a form in Drupal.  Infact, if you put some fields you wanted into one of those content types you actually created or defined a classic Drupal form.

The first section of this page is all about extra things you might consider adding to the 'Classic PHP' type of Drupal forms.  Following that is another section on a 'Webform' series of tools that are more specifically devoted to Form Management as a separate application need for certain types of websites we might develop.

## Classic PHP Forms

### Forms Steps module

Forms are a point of input.  Too much can overwhelm.  Since you might aim to pretty up the forms associated with some node where you want an authorized end-user to contribute some content, you want to keep it clean and simple.  One way to gather this input would be to have a sequence of input pages rather than a giant one.  Think of the [Entity Form Steps module](https://www.drupal.org/project/entity_form_steps) as a way to break things into a series of input step pages.  [See its simple set up.](https://www.drupal.org/files/project-images/Screen%20Recording%202022-05-23%20at%201.50.12%20PM.gif)  

`composer require drupal/forms_steps`<br>
`drush en forms_steps`

### Forms Mode Control module

The form steps module above may combine with the [form mode control module](https://www.drupal.org/project/form_mode_control) to offer even more friendly end-user input.  You can use the form mode control module to control how the fields are displayed in the edit form of content such as nodes and taxonomy terms.  Once you install and enable the form_mode_control module, go to your 'admin' menu and the 'structure' tab.  There is a 'Display Mode' item on the menu and you select that.  Now, instead of just a display view mode control option you have a 'Form modes' option.  And you can add a form mode or configure ones you have.  What is especially cool about this contributed module is that it works on all the various entity types that include the basic 'form' from core Drupal.  So you can use it on Blocks, Content, Taxonomy, etc.  The first two might be the most common use cases, but there is value in the others as well.

Using different display modes in Drupal is second nature.  People are most familiar with having a 'full content' node display and a stipped down 'teaser' display; the teaser often used when you make a view of say the five most recent article in a sidebar region.  Sort of think of Form Mode has having this same content but with differing levels of detail for different purposes on a form.  One stripped down form might be for an end-user submission of the basics while another cut of the same form has all the information around submission, revisions, dates, etc. that the section content editor of your site in charge of this area can work with.

`composer require drupal/form_mode_control`<br>
`drush en form_mode_control`

### Form Block module

The [Form Block module](https://www.drupal.org/project/formblock) allows presentation of things like a user registration, a contact form, or even an end-user page submission to be presents as a form in a block format. Placing blocks into the appropriate region on a webpage makes the display of the resulting into very flexible.

`composer require drupal/formblock`<br>
`drush en formblock`

### Building one

[Understanding how a classic PHP form is built](https://www.specbee.com/blogs/enhancing-user-experience-with-drupals-form-api) will actually give you a leg up in just starting to understand a little more about php code, and things like a module's `.info.yml` file and how 'routes' work (hint is to simply thing of it like secret code for how an application knows where stuff is like a sub-directory organization does).  

## Webform Module Series

Someone in the world always thinks there is a better mousetrap.  And, that is why we have so much good stuff.  Well a fellow named [Jacob Rockowitz](https://www.drupal.org/u/jrockowitz) has run deep on better forms with the [Web Form Module.](https://www.drupal.org/project/webform) 

I have only met him electronically in some chats on his other mission in life around [Schema.org](https://www.drupal.org/project/schemadotorg)  If you have the chance, enjoy.  But the most likely chance you will have to get to know Jacob is via some of his absolutely outstanding contribution to documentation.  If every Drupal developer did documentation like Jacob there would be no other CMS in the world.  

Start with his [Introduction to the Web Form Module.](https://www.youtube.com/watch?v=VncMRSwjVto).  Go for the [Web Form Submissions and Options Limits.](https://www.youtube.com/watch?v=fdkv10v3AX4) Have you even thought about [Web Form Cards.](https://www.youtube.com/watch?v=bDugc2gWQnw) But that is only one of the [Web Form Variants.](https://www.youtube.com/watch?v=53aB_mTkrI4) Then you know there would be [Web Forms for Designers.](https://www.youtube.com/watch?v=-7lxtfYgidY)  Or how about [Web Forms for Health Care.](https://www.youtube.com/watch?v=YiK__YobDJw) And of course [Web Forms for Government.](https://www.youtube.com/watch?v=WQG6163r9Rs)  This could go on and on; so just sign up to his YouTube Channel if you find what he offers fits your use case.

Now all that said, there are some 'watch outs' with how this module works.  It is kind of 'outside' the mainstream of Drupal's underlying code in some ways and you will face the challenges in assuring the variables from Jacob's forms can get into your system for best use with other Drupal tools.  Not to say "Don't Do It" but make sure your needs are for some real 'Form' oriented uses to make sure that the extra integration efforts you will face are properly accounted for compared to working with the Form API approach and some nice Front-end work to present them well.

Remember, this is NOT your standard, classic Drupal PHP input form or a tweaked version of it like offered earlier.  Rather, it is a 'form system' first and it has the opportunity to interface with Drupal.  On the incorporate it level, that is straight forward and powerful.  On the get data out of the form and into standard Drupal 'fields' expect some extra effort.  Rather than fields, Webform calls them 'elements'.  The easiest way to wrap your head around this is to [watch this short video on setting up a simple form which demonstrates the use of elements to define what your form contains.](https://www.youtube.com/watch?v=fr3kTiYKNls)

Relating the Webform 'form system' elements to 'PHP fields' within classic Drupal forms may not be for the faint of heart.  Webform has the ability to export CSV files of the elements Webform has collected.  It also has the ability to present YAML files of this information.  And there is a [way to relate the YAML file data elements collected back to to standard Drupal PHP fields that the database uses with the Drupal Form API.](https://www.jrockowitz.com/blog/webform-apis)  A [tutorial on setting up and using forms in this manner provides a more step-by-step outline](https://www.specbee.com/blogs/drupal-9-webform-module)  It may be that your goal is to display a view of the webform collected data and if that is the case, the [Webform Views Module](#webform-views-integration-module) may be the easier solution.  If you dare to not only use that module but want to see if you can tweak some code available from GitHub, a contributiong user has presented a way to [make the Webform elements into Drupal nodes.](https://github.com/owenmorrill/subtonode) However, if you prefer avoiding coding level work to get a node out of a webform submission you probably want to look at the [Webform Content Creator module.](#webform-content-creator-module)

### Webform base

The base module has a whole variety of features within it.  But because this series is so well documented, it makes no sense to repeat all that here; just [jump to this great overview of all that it does and works with.](https://www.drupal.org/docs/contributed-modules/webform/webform-features)  This [brief tutorial from Yale University shows some easy ways to use this module](https://yalesites.yale.edu/module-tutorials/webform) Or you may prefer a [step-by-step install and use guide.](https://www.webwash.net/courses/using-webform-in-drupal-8/)

`composer require drupal/webform`<br>
`drush en webform`

### Webform Cards

One thing to call out is how using Webforms with a Cards set up is like a step flow.  You might think of the [Webform Cards module as the 'step' counter-part](https://www.youtube.com/watch?v=bDugc2gWQnw) of a traditional stepped form noted earlier, but on steroids.  It you start getting into lots of steps the user experience of the traditional approach can bog down.  But the Webforms Cards approach is a client-side JavaScript Webform Wizard approach that then talks to Drupal; thus fast on the screen refreshes as you move through pages.  One of the very valuable concepts of stepping through a form is that you can make subsequent steps 'conditional'.  Here is an example of [using conditional logic to create a preferred content method and then either asking for a phone number or an email address depending on which the user preferred.](https://www.youtube.com/watch?v=ic4wu-iZd4Y)

### Webform Views Integration module

The [Webform Views module](https://www.drupal.org/project/webform_views) is a way to utilize data collected via Webform in Drupal [Views](../modules/views.md).  A [step-by-step guide presents the basics of using Webform elements within Views.](https://www.drupal.org/docs/8/modules/webform/webform-cookbook/how-to-create-a-view-for-displaying-fields-values-of/step-by-step-guide)  However, do keep in mind that Views itself is extraordinarily powerful, so many additional alternatives from this base guide might fit your specific use case even better.

### Webform to entity

It was noted earlier that getting Webform element information into a Drupal field was more challenging than the reverse.  Here you can see the [way that you can provide an entity from Drupal into a Webform element selection option; taxonomy terms are demonstrated but other entity type access is also briefly shown.](https://www.webwash.net/taxonomy-terms-as-webform-options-in-drupal/)  This is a basic part of Webform, not dependent on installing an additional module.  Since Webform is capable of being used to set up Survey's, you can see how the response categories on closed-end questions being taxonomy terms might be valuable.

### Webform Content Creator module

It may make it easier to have your webform feed its content to a Drupal node, you should take a look at the [Webform Content Creator module](https://www.drupal.org/project/webform_content_creator)  This creates content entities after submitting webforms.  You have mappings between the fields of the created content entity and webform element values.  It is possible to use tokens and/or custom values.

`composer require drupal/webform_content_creator`<br>
`drush en webform_content_creator`

### Webform Config Ignore module

A watchout with Webform is that it behaves a little different than the rest of Drupal with respect to how it doesn't retain values in the database; without some of the interconnections just discussed.  There is good and bad in some of these difference.  For example, site editors can be making form and option list changes without it impacting the rest of the items.  On the other hand, the work they do will be over written by a redeploy of a site, say for updates of something else, that the changes they have made to the forms and list will be overwritten.  The [Webform Config Ignore module](https://www.drupal.org/project/webform_config_ignore) is the work around for that issue.


### Webform a Configuration entity

In the introduction about [Drupal basics we noted that there are a handful of entity types; two prominent ones being content and configuration.](../book/archandentities.md)  For the most part much of what we put 'inside' of Drupal is content.  And how we set up Drupal is configuration; things like menu structures, views, the basic site name/logo/slogan, etc.  The content stuff pretty much is doing right into the database.  But the configuration stuff is in the code; that is until we export it to YAML files in a sync sub-directory and then have those file tucked away in the database so they are secured, plus sharable with others and across deployment environment.  Webform falls into the configuration entity bucket.  Thus, we need to use something like the [Configuration Entity Revisions module](https://www.drupal.org/project/config_entity_revisions) to [take advantage of the version history and other advantages of Drupal being inherently revisionable.](https://www.youtube.com/watch?v=YKr-vLCRaJo)

`composer require drupal/config_entity_revisions`<br>
`drush en config_entity_revisions`


<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)


