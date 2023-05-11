
# Decoupled Drupal

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
<br>

[Learn More - CMS Front-end](../chapters.md#front-end)
