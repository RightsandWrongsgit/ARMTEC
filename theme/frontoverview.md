
# Front-end Overview

Drupal [Content Management System (CMS)](chapters.md#chapter-content-management-system-cms) is an integrated website platform.  You select it because you have 'Content' that you wish to 'Display' in a user's 'Browser' in a 'Templated' manner which has some consistency.  A common example might be a newspaper which presents articles that have a title, subject, author, date, and story element consistently included in a template.  You might use the 'subject' to reference the sports, financial, lifestyle, business, and other sections in your newspaper.  In each of those sections you might 'present' the article in a slightly different style; font, color, size, etc.  Drupal has all the parts needed to control and manage the integrated workflow of all this stuff.

Think of the workflow like this:

<font color=fcb9aa>CSS & JS→Display in Browser</font><br>
<font color=ffdbcc>TWIG/HTML→CSS & JS</font><br>
<font color=eceae4>PHP(core)→TWIG/HTML</font><br>
<font color=a2e1db>Database→PHP(core)</font><br>
<font color=55cbcd>Content→Database</font><br>

The <font color=55cbcd>'Content'</font> is what you would write and it is stored in the <font color=a2e1db>'Database'</font> for each article in your newspaper.  The Drupal <font color=eceae4>'PHP' core</font> has the code not only for a content type called <font color=eceae4>'Article'</font> but you probably have other content types for, the newspaper's name, for advertisements, for your about the editor/publisher and contact each department type information, etc.  And all that defines your newspaper to the database so it knows where to store different parts.  And that also talks to the <font color=ffdbcc>'TWIG' layer</font> which are <font color=ffdbcc>templates</font> for what goes in each region or section of your newspaper.  Now the look and feel of each section appear in their <font color=fcb9aa>'presention'</font> is further managed by CCS or JavaScript(JS) that interact with the reader's browser. 

When we talk about the "Front-end" we are referencing the TWIG, HTML, CSS, and JS parts of your Drupal website that are key to managing how the content of your website is displayed.  Drupal core offers a 'theme' layer for this display called "Olivero".  You might also use themes offered by others and "Bootstrap" is a common powerhouse.  Underlying such themes is the "TWIG" templating engine and you can work with it directly.  At a more advanced level, there is "Decoupled" Drupal which might use Vue, React, or some other browser level framework that reaches back into Drupal to grab content but that does a lot more independently.

## Olivero

Drupal comes with a standard theme automatically.  The most current version of Drupal is using a presentation theme called [Olivero](../theme/olivero.md).  It is a relatively new addition that looks clean and modern.  For a fairly basic website you might give it a try.  It has a nice menu approach, is responsive for different devices, and it known for its accessiblity.  It is going through further updates and that might correct some potential limitations; because of some limits to your ability to customize certain parts of it you risk having your website sort of look generic. 

## Bootstrap

[Bootstrap](../theme/bootstrap.md) is one of the more common and powerful front-end frameworks.  It opens up a ton of flexiblity to go your own way with the look and feel of your website.  Flexibility is usually at the price of complexity and there is a little more to go this way.  However, because it is so commonly used, a version of [Bootstrap called Barrio](https://www.drupal.org/project/bootstrap_barrio) is set up specifically for use in Drupal.

## Alternatives

There are other alternatives that can be installed with Drupal. Right on the [Drupal website](http://Drupal.org) under the 'build' menu option you will find themes listed and a search function to look at some.  There are also commercially available themes but a watch out is that you need to be careful that the version of Drupal is supported before you buy one.  And, you might end up doing as much work with these commercial themes as just using the free ones as your starting point. 

## Install Themes

Installing a base theme is a straightforward process.  First, one theme came as default in what you installed Drupal.  [To install a Drupal theme](https://www.drupal.org/docs/user_guide/en/extend-theme-install.html) after you find it, you use [composer](../book/Novice.html#setting-up-your-basic-system) just like you do to install [Drupal modules](chapters.md#drupal-modules).  Keep in mind that you not only have to install it, but you need to set it as 'default' before it is the one that your website will be using.  To do that you go into ADMINISTRATION/APPEARANCE and install and make default.  The default theme files from Core are underneath the Core/themes subdirectory; <font color=red>YOU DO NOT EDIT ANYTHING IN CORE EVER!</font>  You can, however, copy stuff from core or from most 'contributed themes', into [your own custom theme's templates sub-directory (see last sub-directory listed in the red line section on this map)](../cicd/directorymap.html).  That is where any TWIG templates you will edit for your own unique proposes should be located. 

## TWIG

PHP itself renders a first level of HTML output but delivering it to TWIG templates. Those TWIG templates really goose things up a notch in terms of HTML display of your content.   Then, like in most website work, CSS and JS really leverage the power of display control.   

Drupal themes have TWIG templates.  Those templates are located in sub-directories under Drupal core are the base for any display that you haven't overridden.  You override them by installing 'contributed themes' in your themes sub-directory (see above note for location).  <font color=yellow>YOU DO NOT EDIT EITHER THE CORE OR CONTRIBUTED THEMES!</font>  This is because any updates to either as you refresh your site would then overwrite your edits and your work is screwed...  Rather, you make a custom theme in its own sub-directory.  Drupal, being as smart as it is, starts looking first in your custom theme sub-directory for a template, then falls back to the base contributed theme, and finally to the core base theme for any template backups it needs. What that customization for your own unique purpose is called is [creating a subtheme](../theme/twig.md#sub-theming).

It is very common that you might find a template under your base theme that you might want to tweak in some way; either across all places it is used on your site or on a specific page or node.  You are going to <font color=yellow>edit a copy of a twig template.</font>  TWIG templates are very similar to HTML with just three additional basic TWIG specific pieces of syntax; [how to proceed with your own TWIG edits is outlined here.](../theme/twig.md)

## Decoupled

Think of a de-coupled Drupal site as using something like a JavaScript(JS) framework like React or Vue and having it grab content from Drupal.  There are some performance benefits of a JS client inactive deployment.  There are also some breadth of device opportunities when we think of moving past computers, tables, and mobile to watches, smart TV's, vitual, other devices, and AI.  But all of these need the data or content and this brings in a real Drupal strength.  

You probably should think of decoupled as a continuum rather than a cleaver.  The front-end and back-end need to talk one way or another.  There have been some [bleeding edge attempts at decoupled Drupal and interesting bumps along the way](https://www.youtube.com/watch?v=RK4BG3hsN3I).  Excitement and reality have some tendency to diverge, so be careful on your approach.

Closer to home, there are a few current and emerging modules that might be considered.  For the options closer to home but that add capability, a review of a presentation from an Asheville Drupal Camp in the summer of 2020 is worth watching.  ['An Overview of Front End Component Integration Methods in Drupal'](https://www.youtube.com/watch?v=UQ-SRGVV9k8) is especially worth watching about 17 minutes into the video where two broad approaches to integration of components are compared.  One is 'Mapping Data In Code' and you can think of that as more at the TWIG or even PHP preprocessing level (which backend programmers probably gravitate toward).  The other is 'Mapping Data In Admin UI' and you can think of this as aiming toward integration with things like PatternLab and Storybook components.  This video is about understanding the options and their pros and cons; but it doesn't just boldly give an answer.

As discussed earlier, the variables from Drupal go through Twig Templates to provide a first level rendering of an entity like a page, block, etc.  You are going to want to work at the level of these templates at some point and we showed how different names, from generic to specific are shown with you have debug on.  To make that even easier, you might want to install and enable the Twig Debugger module that lets you click the little edit pencil from your GUI view of your page and then use your browser's 'source' view to see how that specific area of your page is controlled by a certain twig template (composer require drupal/twig_debugger and the drush en twig_debugger).

At the TWIG level two other helper modules are discussed in the video; 'Twig Field Value' and 'Twig Tweak'.  That later of these is broadly more capable so is worth considering.  The way to think about Twig Tweak as a module is that it aims to bring a richer toolset; but unlike a lot of modules don't necessarily think of it as a GUI keeping you away from code level efforts.  TWIG is a pretty rich framework in and of itself.  Drupal only brings a portion of it to bear.  What Twig Tweak will do is give you access to all the functions of the broader framework.  

At the practical level, take a look at 'How To Use Twig Tweak Module' here: https://www.youtube.com/watch?v=7UlGAeKYoa8



If you start getting into TWIG template editing, you may want to go to TwigFiddle.com where you can practice editing approaches. 


Components and how they fit with certain theme decisions:
The 'Map Data in Admin UI' direction is rapidly emerging.  As noted, not going to decoupled but that remains a possibility.  Instead, think about two 'Component' library or additions with Javascript that have developing or beta projects in Drupal aimed to facilitate their use integration; PatternLabs and Storybook.  Some of the PatternLabs modules are discussed in the back half of the 'An Overview of Front End Component Integration Methods in Drupal' video.  

Let's look at the Storybook emerging option.  First, Storybook itself can be found at https://storybook.js.org/  Note that it, like Drupal is also OpenSource.



When you look at Storybook, you will find it can be used with React, Angular, etc. and thus might be able to use the decoupled Drupal approach should you eventually go that way.  But for now, lets look at some Drupal modules that are specifically designed to integrate the two.  The Component Libraries Module works toward a regular Twig template combined with a metadata.json file describing the input data to connect the component JavaScript to the template.



Expect some pretty detailed set up steps but the documentation link to a GitLab repo read.me is pretty helpful in walking you through it. https://git.drupalcode.org/project/cl_server/-/blob/1.x/docs/storybook.md


To understand just how powerful and comprehensive Storybook is, you really need to go to the site and drive around.  You will see specific examples of components being deployed in many ways, even with links to access the underlying example code.  So if you are going to be doing a number of sites, it may be worth the trouble of the complex setup of the components so you have your own library.  And, of course, keep an eye out for others who publish their Drupal-Storybook Component to adopt. 

This module works with the Component Libraries: Theme Server.  You can go to the Theme Server module on Drupal.org and there is a link to a 'Step-by-Step' tutorial.


The newly release 'Component Libraries: Blocks' module it the third in this group that further expands the power of this approach.  It appears to integrate well with Views, Layout Builder, and other standard Drupal core common tools.



<br>
<br>

[Learn More - CMS Front-end](../chapters.md#front-end)
