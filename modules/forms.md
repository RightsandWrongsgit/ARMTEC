
# Drupal Forms

Forms are a fundamental part of Drupal.  You can think of what you put into drop when setting up or working with a content type as basically using a drupal form; via the [Form API.](https://www.drupal.org/docs/drupal-apis/form-api/introduction-to-form-api)  You set up fields in Drupal and you tell it about them with a form.  You tell Drupal what content you want to display basically using a form.

Since you may want to do some of your first level of uniquely odd things by modifying a Drupal form to get the inputs in that you need to pull it off, the form may be the first time you get the nerve to mess with actual code in Drupal.  So the next item is a quick overview on how you would code a customized form; they use an employee registration as the type form to demonstrate. 

## Basic

[Understanding how a form is built](https://www.specbee.com/blogs/enhancing-user-experience-with-drupals-form-api) will actually give you a leg up in just starting to understand a little more about php code, and things like a module's `.info.yml` file and how 'routes' work (hint is to simply thing of it like secret code for how an application knows where stuff is like a sub-directory organization does).  

## WebForm Module

Someone in the world always things there is a better mousetrap.  And, that is why we have so much good stuff.  Well a fellow named [Jacob Rockowitz](https://www.drupal.org/u/jrockowitz) has run deep on better forms with the [Web Form Module.](https://www.drupal.org/project/webform) 

I have only met him electronically in some chats on his other mission in life around [Schema.org](https://www.drupal.org/project/schemadotorg)  If you have the chance, enjoy.  But the most likely chance you will have to get to know Jacob is via some of his absolutely outstanding contribution to documentation.  If every Drupal developer did documentation like Jacob there would be no other CMS in the world.  

Start with his [Introduction to the Web Form Module.](https://www.youtube.com/watch?v=VncMRSwjVto).  Go for the [Web Form Submissions and Options Limits.](https://www.youtube.com/watch?v=fdkv10v3AX4) Have you even thought about [Web Form Cards.](https://www.youtube.com/watch?v=bDugc2gWQnw) But that is only one of the [Web Form Variants.](https://www.youtube.com/watch?v=53aB_mTkrI4) Then you know there would be [Web Forms for Designers.](https://www.youtube.com/watch?v=-7lxtfYgidY)  Or how about [Web Forms for Health Care.](https://www.youtube.com/watch?v=YiK__YobDJw) And of course [Web Forms for Government.](https://www.youtube.com/watch?v=WQG6163r9Rs)  This could go on and on; so just sign up to his YouTube Channel if you find what he offers fits your use case.

Now all that said, there are some 'watch outs' with how this module works.  It is kind of 'outside' the mainstream of Drupal's underlying code in some ways and you will face of challenges in assuring the variables from Jacob's forms can get into your system for best use with other Drupal tools.  Not to say "Don't Do It" but make sure your needs are for some real 'Form' oriented uses to make sure that the extra integration efforts you will face are properly accounted for compared to working with the Form API approach and some nice Front-end work to present them well.

<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)

