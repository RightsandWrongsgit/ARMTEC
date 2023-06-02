
# Email

## Core

Drupal has email capability out of the box.  So, for example, when a [new user signs up it can trigger a confirming email.](https://www.drupal.org/docs/8/core/modules/contact/overview) You set up the basic choices for your email system under the 'configuration' option in the Administration menu.

<img src="../modules/images/Admin Menu.png"  width="600">

You basically will see some choices regarding the 'parts' of the email system.  What the heck do 'parts' mean with regard to email.  Since we use email all the time we don't tend to think about the fact that there are at least two major chunks to the process; Format and Mail it.  

<img src="../modules/images/configuremail.png"  width="600">

Another thing that the underlying mail API in Drupal has is an ability to point to a specific module.  Without going nuts on reading code, just look at the second line listed below and the first item in parentheses; it says $module.

<img src="../modules/images/emailcode.png"  width="400">

If you are interested in [the underlying email system in Drupal](https://www.drupal.org/docs/contributed-modules/mime-mail/how-email-works-in-drupal) you kind of need to be in the mindset that it is meant to deliver core functions to be used by other, more capable mailing alternatives.  What is provided as part of Drupal core will basically only provide a plain text format email and send it.  Most people are going to want to do more than that with their email.  Having an HTML format capability to present a better look, include images in the email, allow for attachments, are sort of considered fundamental if you want to send emails that are more than a sign-up confirmation.

Since the sort of basic way the core email system is used is around confirming a sign-up, you can actually work the first level use of it from the Administration/Configuration/Account settings part of your website.

<img src="../modules/images/signupemail1.png"  width="200">

From within that area, you put in the address that will be default in your website for who any emails will be 'from'.  Then there are a bunch of standard email templates that you can use directly or you can edit.  Notice the odd little brackets aroudn some items and what these represent are variables or fields that get custom filled to personalize the emails from other information in your site.  There is something called [Tokens](../modules/development.md) that can be turned on to further expand things that can be inserted into emails outlined in the Contact forms where you move past these standard templates to some of your own.

<img src="../modules/images/signupemail2.png"  width="900">

When you select which form you want to work with, you get some options that will look very familiar to anyone who has started to work with [Content types and Fields](../book/contenttype.md) which is probably the most heavily used part of working with Drupal.  You will see the opportunity to add fields to the form, to create a form display, and to define the final output display.

<img src="../modules/images/contactemail4.png"  width="600">

You can also see that there is a part of the display where a users picture can be included in their profile on the site.

<img src="../modules/images/contactemail6.png"  width="600">

#### What to send

As noted, besides the mechanics of sending mail, there is a need to actually format or create it.  So you start by looking under Administration/Structure/Contact forms.

<img src="../modules/images/contactemail7.png"  width="300">

You can add a contact form and then you can clone a prior, edit, manage fields present, their form and display, and even interface with Devel if you have that module installed. 

<img src="../modules/images/contactemail8.png"  width="800">

When you click to add one, you give it a name, then the subject of the email, they go into your editor and fill out the body.

<img src="../modules/images/contactemail2.png"  width="600">

Continuing on the form you indicate who you are sending it to and you can also indicate a reply address of the site default or some other email address you want any replies to go to.

<img src="../modules/images/contactemail3.png"  width="600">

You can see that multiple contact forms can be defined and applied to your List of contacts.

<img src="../modules/images/contactemail9.png"  width="800">

You will note that even a note in Drupal core Contact forms/Contact settings notes the requirement of adding something like the Swiftmailer contrib module to use HTML mailings.

<img src="../modules/images/contactemail10.png"  width="800">

## Contrib Modules

To better [understand what is and isn't in the email capability of Drupal Core you might want to listen to this.](https://events.drupal.org/seattle2019/sessions/amazing-emails-drupal-8) One of the most insightful graphics from the presentation pulls forward what should really be present in a full fledged email system.

<img src="../modules/images/amazingmailpresentation.png"  width="400">

That graphic notes the use of Swift Mailer replacing or leveraging the core formatting and sending(transport) functions in Drupal's base mail system.  The other functions it points out are really all about taking full advantage of the fact that Drupal CMS has a database that you ought to be able to store stuff in like templates and history plus an interface with functions that allow much better editing, and things like event or scheduled triggering.  The individual presenting in that video is the person behind the [Easy Mail module.](https://www.drupal.org/project/easy_email)  We could be all over heading in this direction with a well integrated mailing add-on except for a watchout to check if the module has passed Drupal's secuity check when you decide.

Let's take a look at some other contributed module options to help see the alternatives.

### Simple Mail module

The [Simple Mail module](https://www.drupal.org/project/simple_mail)  


