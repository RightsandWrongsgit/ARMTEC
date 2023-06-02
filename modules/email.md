
# Email

## Core

Drupal has email capability out of the box.  So, for example, when a [new user signs up it can trigger a confirming email.](https://www.drupal.org/docs/8/core/modules/contact/overview) You set up the basic choices for your email system under the 'configuration' option in the Administration menu.

<img src="../modules/images/Admin Menu.png"  width="600">

You basically will see some choices regarding the 'parts' of the email system.  What the heck do 'parts' mean with regard to email.  Since we use email all the time we don't tend to think about the fact that there are at least two major chunks to the process; Format and Mail it.  

<img src="../modules/images/configuremail.png"  width="600">

Another thing that the underlying mail API in Drupal has is an ability to point to a specific module.  Without going nuts on reading code, just look at the second line listed below and the first item in parentheses; it says $module.

<img src="../modules/images/emailcode.png"  width="400">

If you are interested in [the underlying email system in Drupal](https://www.drupal.org/docs/contributed-modules/mime-mail/how-email-works-in-drupal) you kind of need to be in the mindset that it is meant to deliver core functions to be used by other, more capable mailing alternatives.  What is provided as part of Drupal core will basically only provide a plain text format email and send it.  Most people are going to want to do more than that with their email.  Having an HTML format capability to present a better look, include images in the email, allow for attachments, are sort of considered fundamental if you want to send emails that are more than a sign-up confirmation.

<img src="../modules/images/configuremail.png"  width="600">


<img src="../modules/images/contactemail5.png"  width="600">


<img src="../modules/images/contactemail6.png"  width="600">

#### What to send

As noted, besides the mechanics of sending mail, there is a need to actually format or create it.  So you start by looking under Administration/Structure/Contact forms.

<img src="../modules/images/contactemail7.png"  width="600">

You can add a contact form and then you can clone a prior, edit, manage fields present, their form and display, and even interface with Devel if you have that module installed. 

<img src="../modules/images/contactemail8.png"  width="600">

You can see that multiple contact forms can be defined and applied to your List of contacts.

<img src="../modules/images/contactemail9.png"  width="600">

You will note that even a note in Drupal core Contact forms/Contact settings notes the requirement of adding something like the Swiftmailer contrib module to use HTML mailings.

<img src="../modules/images/contactemail10.png"  width="600">

## Contrib Modules

To better [understand what is and isn't in the email capability of Drupal Core you might want to listen to this.](https://events.drupal.org/seattle2019/sessions/amazing-emails-drupal-8) One of the most insightful graphics from the presentation pulls forward what should really be present in a full fledged email system.

<img src="../modules/images/amazingmailpresentation.png"  width="400">

That graphic notes the use of Swift Mailer replacing or leveraging the core formatting and sending(transport) functions in Drupal's base mail system.  The other functions it points out are really all about taking full advantage of the fact that Drupal CMS has a database that you ought to be able to store stuff in like templates and history plus an interface with functions that allow much better editing, and things like event or scheduled triggering.  The individual presenting in that video is the person behind the [Easy Mail module.](https://www.drupal.org/project/easy_email)  We could be all over heading in this direction with a well integrated mailing add-on except for a watchout to check if the module has passed Drupal's secuity check when you decide.

Let's take a look at some other contributed module options to help see the alternatives.

### Simple Mail module

The [Simple Mail module](https://www.drupal.org/project/simple_mail)  


