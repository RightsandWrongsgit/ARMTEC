
# Olivero Theme

Drupal earned itself a bad reputation.  Even if people bought into the point that it is the powerhouse [CMS](../book/cms.md) they were turned off by the initial look of it; a function of the [Bartik theme](https://drupalize.me/tutorial/core-themes-bartik) being from a past generation. 

The world experiences the web with highly graphical beauty.  Heck, some sites seem to offer little more than pictures.  Drupal was built for function and it speaks to the developer community who create performance that way.  Drupal has been on a tremendous update mode for several years now and has learned to speak to both Developers and Site Builders.  That later group probably migrated from trying [Wix](https://www.wix.com/) not really having to know anything but wanting more, rolled through [WordPress](https://wordpress.com/) but hit the wall quickly, and has now heard Drupal can accomplish any of their goals.  A new "WELCOME" sign is out with the Olivero theme presenting a clean, modern style while front-ending real functionality.

## This Changes Everything

[The new Olivero theme is something you need to see.](https://imagexmedia.com/blog/drupal-new-front-end-theme-olivero)  The menu flow if outstanding.  The graphic frame is clean.  It has the ability to work with a [Drupal GUI drag and drop tool called Layout Builder.](https://www.youtube.com/watch?v=OOM4yRWv7Ew)  Olivero is worth a quick review of its [many features and benefits](https://evolvingweb.com/blog/hands-drupal-10-olivero-new-theme-meaningful-name) before you consider any other alternatives.  Olivero is just the theme part of the recent advances in Drupal.  There are many more; see [The Best Of Drupal 10.](https://pantheon.io/blog/explore-best-drupal-10)

[To really get under the hood and see what a powerhouse Olivero really is, you should hear from its lead developer.](https://www.youtube.com/watch?v=dn-JN2bcw1s)  Sure, he gives you some nuts and bolts level things but more importanly he reviews its huge range of features.  When you listen to his presentation please think about if and how any other approach you are going to try to build your own site with is going to handle all these critical things.  [Olivero not only has outstanding navigation and great accessiblity features, its Flexbox deployment provides super responsiveness on devicesThe Making of Olivero](https://www.youtube.com/watch?v=ohPaYEbC4Lk); <font color=yellow> Please jump ahead to 19:30 to get to the good stuff on this video.

## Sites By Olivero

[APL Pest Control](https://aplpestcontrol.com/)
[Herchel](https://herchel.com/)

## Olivero Sub-theme

https://developpeur-drupal.com/en/article/create-drupal-9-olivero-sub-theme

<br>



https://designkojo.com/drupal-theme-primer-part-1-creating-drupal-sub-theme








*************



- Theming & Modules for some Good Specific Themes -
(You probably used a default theme as you laid out your fields, content types, blocks, etc.
Making your site look good leverages themes and you can do a lot to even customize the Core)

There is a lot of functionality right in Core.  You have a WYSIWYG editor, you have a media library for images, videos and more, you have the base theme, and you have the potential to leverage TWIG templates along with HTML, CSS, and JS in managing your presentation of you website.  The key thing to understand about Drupal is that it is a CMS or Content Management system and therefore, the first thing you are doing is setting up precise detail about what is in the content sections you will build.  So that is why thinking about fields, taxonomies, and the content types or nodes/blocks they will be presented in is the first order of business.  Making it look pretty with the theme you select, the images you apply, and the display of all the content happens after; the good news being that this separation of duties in Drupal allows you to later modify the look you present without having to redo all the content you have already dropped in.



PHP itself renders a first level of HTML output but delivering it to TWIG Templates really gooses things up a notch in terms of HTML display of your content and with HTML5 some might argue state management might be enough to be done at that level.  But most will want to further enhance with CSS and JS to really leverage the power of display control.   

Installing a base theme is a straightforward process.  First, one probably came by default in what you installed.  And if you want to change themes you go into ADMINISTRATION/APPEARANCE and install and make default a different one.  The default theme with Core are underneath the Core/themes subdirectory; YOU DO NOT EDIT ANYTHING IN CORE EVER!  You do, however, copy stuff from core, especially under your base theme's templates subdirectory which is where the TWIG templates live.


It is very common that you might find a template under your base theme that you might want to tweak in some way; either across all places it is used on your site or on a specific page or node.  You are only going to edit a copy of a twig template.  Note two things on the next image; a) there is a themes subdirectory at the same level as the core subdirectory and that is where you are going to put any customization to your base them (ie. where you are going to put the copy to edit) and b) there is a sites/default subdirectory also starting at that top level and in it is a services.yml file (which you can make by duplicating the default.services.yml file and renaming it).

The logic of messing with the services.yml file is that you are going to make one super simple edit within it.  Look down say 50-60 lines for the word 'debug:' and where it says false, change it to true and same the file.  Clear your cache and when you 'inspect source' on any page on your Drupal site you will find a list of the TWIG file that is active PLUS some suggested names of an 'override' file.  


Overriding is done all over Drupal as the way it is so flexible.  Drupal is a super CMS out of the box but the fact you can override all sorts of stuff makes it the best CMS out there to service a huge range of applications.  The TWIG template override is a first line of flexibility and the debug you just turned 'true' means the inspection of source will note a) where the template used in that area is located (helpful to find it to make a copy) at the bottom of the snippet below; b) the name of the currently used template (the one with 'x' in front of it below); and c) some alternative names you might consider for a copy you want to use as an override on the copy you are editing (from bottom upward, more general to more specific).  If you are overriding all uses of the current across your whole site you can keep the same name on the copy but if you are targeting the edit, think how focused you need it to be and move up the list accordingly. 


You aren't editing the original twig template in core, you are doing it to the copy under your custom theme.  In the example below, the subdirectory for that custom theme is named 'eg' and underneath it are subdirectories for 'templates' where the twig templates go and another subdirectory for 'css' styling.  It is standard practice in Drupal to separate your css into 'base', 'components', and 'layout'; so you see those as even deeper subdirectories in the image below.

In addition to having the twig and css assets in your custom theme subdirectories, you need to tell Drupal about where they are.  First you simply tell Drupal about what you are calling the custom theme and what base theme it is built upon in the file <yourcustomthemesname>.info.yml; in the example the custom them is simply called 'eg'.  See that file name in the same subdirectory at the css and templates subdirectories in the image above.

The content of that file are simple, as are most yml or yaml files.  The key thing when ever you do an of these file is the indents are TWO SPACES (so don't 'tab').  Here is what eg.info.yml looks like:


You also need to more specifically tell Drupal about the assets by showing where the css files you will use are located via <yourcustomthemesname>.libraries.yml; in the example at that same subdirectory level it is eg.libraries.yml and what is inside it is shown below:



The examples above are from some excellent training videos on YOUTUBE that Acquia has provided to the Drupal community.  Follow this link to the "Intro to twig templates" but make sure to watch those after it in the series to get a further understanding: https://www.youtube.com/watch?v=2cHe50tp_U4&list=PLpVC00PAQQxG0sW9YOueVgouRp4aj1bng&index=23


Beyond Core -

Drupal core is already very capable.  And there is even a tool called Layout Builder (in core, but must be enabled) and it really gives lots of ability to the newer users.   However, there are a ton of what are known as "front-end" options to use with Drupal; all the way to even doing a de-coupled site with a JS framework like React or Vue grabbing content from Drupal.  Closer to home, there are a few current and emerging modules that might be considered. 

For the options closer to home but that add capability, a review of a presentation from an Asheville Drupal Camp in the summer of 2020 is worth watching.  It is titled 'An Overview of Front End Component Integration Methods in Drupal' and can be found here:  https://www.youtube.com/watch?v=UQ-SRGVV9k8
About 17 minutes into the video two broad approached to integration of components is compared.  One is 'Mapping Data In Code'  and you can think of that as more at the TWIG or even PHP preprocessing level (which backend programmers probably gravitate toward).  The other is 'Mapping Data In Admin UI' and you can think of this as aiming toward integration with things like PatternLab and Storybook components.  This video is about understanding the options and their pros and cons; but it doesn't just boldly give an answer.

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



Bootstrap Barrio Theme:

How to set up your own subtheme using Bootstrap Barrio:
https://www.webwash.net/getting-started-with-bootstrap-4-using-barrio-in-drupal-8/


composer require 'drupal/bootstrap_sass:^5.0'

Confirm is the sass subtheme install automatically installs the barrio base theme; if not, here it is:
	
composer require 'drupal/bootstrap_barrio:^5.1'



Potential libraries to see if they have anything worth adding and testing if they are even compatible with Bootstrap framework:
Animate.css
Hover.css

composer require 'drupal/components:^3.0@beta
	
Could be that the components module may offer some easy style editing via its GUI.  But you are probably better to stick with direct TWIG and CSS and JS editing.






<br>
<br>
<br>

[Learn More - CMS Front-end](../chapters.md#front-end)
