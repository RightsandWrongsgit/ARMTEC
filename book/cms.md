
# Content Management System (CMS)

In a content management system (CMS) you have many pages of content that are displayed in some common format(s).  You can generally think that the content is stored in the database portion of the system and the display of it is in code.  There is also code in between the data and display that applies any logic.  


## Drupal

Drupal is one of the most powerful content management systems that integrates these three basic parts.  You can use a number of different databases with Drupal but it is pretty common that 'my-SQL' is used.  Regardless of the specific database, you are likely to have an [ODBC compliant(https://www.ptsmobile.com/what-is-odbc.htm) type that can exchange data with other databases and which can be directly queried using a language called [SQL](https://www.codecademy.com/learn/learn-sql).  For the most part, Drupal will simply handle what you need about the basic database interactions, so we don't generally need to dive any deeper on website projects.  For our analytical work or performance optimization work we may.

The logic portion of Drupal uses a version of the PHP language called [Symfony](https://symfony.com/).  Content editors and Site Builders probably don't need to know more.  Developers will want to know some basic PHP skills and general object oriented programming principles.  The [chapters from Selwyn head into the Developer skill level](chapters.md#chapters-from-selwyn-polit).

The display part of Drupal is a presentation layer that uses [TWIG](../theme/twig.html), HTML, [CSS](../book/opensource.md#front-end), and JavaScript.  Again, you may not have to worry about this if you are a content editor.  Even site builders can use some standard included "Themes" like [Olivero](../ARMTEC/chapters#front-end)  and produce some very capable and attractive websites.  However, you probably will want to advance into more customization of the displays by learning more about working with Drupal's front-end tools.

## Drupal Front-end

Drupal themes provide a foundation for menu's, headers, footers, sidebars, and main content areas of your website.  These are termed ['Regions'](https://www.drupal.org/docs/user_guide/en/block-regions.html) in Drupal jargon.  You will be able to customize which Regions you use right from the GUI interface of the system without knowing any code.  But you can also go into a coding level and do lots more, up to building your own theme.

It would actually be pretty rare to build a whole Drupal theme.  You see the way it works is people clone base themes and customize various parts to serve their specific needs.  Any part you don't customize, just follows a drop-back logic and defaults to a more foundational base.  What is most common is that you download one of the available 'Contributed' themes, which themselves are build on top of some Drupal core theme, and you clone the 'Contributed' theme to make your own 'Custom' them.  Then Drupal knows to start to look for your custom theme templates use what is found; but if one isn't found for that specific need it falls back to the 'Contributed' theme and if not found there falls back to the 'Base' theme.  

## Install a Theme

Drupal.org has a menu section called 'Build' and under it is a option for 'Themes' where you can go to find what you want.  Make sure you use the [Composer installation approach](../book/Novice.html#setting-up-your-basic-system) to install the theme of your choice.  Here is a [short video on installing the Bootstrap theme}(https://www.youtube.com/watch?v=M2wcy-vzcWE&list=PLTANew7ttSXfn6azbqjobJk-zkkRSPd7t&index=4).  The one they show is a little outdated but the process is pretty much the same for most.  Of course the exception is for the [Bootstrap Barrio theme](https://www.drupal.org/project/bootstrap_barrio) which is an ARMTEC, Inc. preference.  That theme follows most the the same installation principles but has a few extras shown on that link.


## Customized a Theme

As mentioned, it is fairly common that people want to customize there theme.  This practice is called 'sub-theming'.  It is reasonably straightforward to do at the basic level.  There are two real keys, a) where it belongs in terms of your project directory structure and b) copying and renaming several files; first to 'name' your new theme and second to bring across copies of some of the templates you want to edit.

The templates are what are known as [TWIG](../theme/twig.html) files.  TWIG is first and foremost how your front-end talks to the back-end or database parts of the system where your content is stored.  TWIG grabs the variables and prints or displays them to the screen in an HMTL translated format.  TWIG also has some logic level stuff it can do.  TWIG can also have HTML code written directly to it and even [CSS](../book/opensource.md#front-end) (but what is known as "inline" CSS is generally discussed to simpler maintenance of your website). 

You are likely to want to learn at least some TWIG stuff unless you are going to stick with a totally standard, out-of-the-box theme.  Here is a [pretty good video on TWIG basics](https://www.youtube.com/watch?v=vuZtCwWbt2U); but be aware you should skip to minute 8 to start it so you can jump over all the introduction of the meeting it was filmed at and you can probably stop it at minute 28 unless you are bored and just have nothing better to watch.

[More on TWIG and some special support modules here](../theme/twig.md)

<br>

## Front-End Tools

There are a number of [important front-end tools](chapters.md#front-end) to get your website to look good.  Some are just the standard theme options and others are code level tools that allow you to control colors, locations, animation, and much more.  HTML is integral with and can be added to TWIG.  Remember that HTML will provide names for then elements it tells the browser to display and these can be controlled with things like the 'classes' or 'ids' you use on the elements for real focus or can be broadly applied to whole sections.  Then CSS especially can be targeted to do its thing upon that elements by putting a 'period' infront of the element name in your CSS code and telling it what you want to happen to that element (e.g. size, color, actions, etc.).  Keep in mind that you want to [tell Drupal about the CSS and JS aspects of your customization of a them like this](https://www.youtube.com/watch?v=afoIrMeZyts&list=PLTANew7ttSXfn6azbqjobJk-zkkRSPd7t&index=5)


## Render Arrays

Unless you are a Developer, you probably don't need to go here.  Even then you may only run deep if you have to deal with an old version of Drupal that you might be converting.  Drupal used to use [.tpl or template files before shifting to TWIG](https://www.youtube.com/watch?v=vuZtCwWbt2U). TWIG offers [security advantages versus using straight PHP]( https://www.drupal.org/docs/security-in-drupal/writing-secure-code-for-drupal) code and is the preference approach.  If there is some really specific situation where TWIG can't accomplish something you can still go the [Render Array route](https://events.drupal.org/neworleans2016/sessions/aha-understanding-and-using-render-arrays-drupal-8).  Once again, [Selwyn Potlit's GitHub pages book provides help on Render Arrays.](https://selwynpolit.github.io/d9book/render.html)








<br>
<br>
<br>

[Learn More - CMS Front-end](../chapters.md#chapter-content-management-systems-cms
