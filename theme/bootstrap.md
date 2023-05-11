
# Bootstrap Theme

[The Bootstrap framework](https://getbootstrap.com/) is a highly capable website front-end toolkit.  It is [responsive](https://www.youtube.com/watch?v=srvUrASNj0s) so your website will look good on a computer, a tablet, a phone, etc.  It is also well integrated with CSS via a call from the 'head' and with JavaScipt (JS) from a similar script call.  The Flexbox capability allows the creative use of a grid style which provides interesting layout throughout your web pages; though do leverage [Semantic Design principles](https://www.semrush.com/blog/semantic-html5-guide/) as you manage your design deployment.  Another great factor that draws one to Bootstrap is its inclusion of [many prebuilt components](https://getbootstrap.com/docs/5.0/components/accordion/).


## Bootstrap Barrio

Bootstrap is so commonly used with Drupal that tens of thousands of site report using it via the [Bootstrap Barrio](https://www.drupal.org/project/bootstrap_barrio) theme.  What this offers over the basic Bootstrap is that someone has written loads of [TWIG templates](../theme/twig.md) to jumpstart your own site.  Think of this as having things like off the shelf components for stuff like cards already available to use directly in Drupal.  Since Barrio is built upon Bootstrap you can also go native if you need something beyond what has been pre-built.

Another thing that makes Bootstrap Barrio's popularity an advantage is there are [good videos on how to install and use it](https://www.youtube.com/watch?v=D5A_aFdlWEs); don't be thrown off that the Bootstrap version has been updated since this video as all that is covered is still accurate.  You also have probably heard about Drupal's own ['Layout Builder' module](https://www.specbee.com/blogs/layout-builder-in-drupal-9-complete-guide#:~:text=Scroll%20to%20the%20bottom%20and,of%20the%20view%20modes%20present.) that offers some nice drag and drop site building support.  The good news is that [Layout Builder and Bootstrap can play nice together as demonstrated in this video on using Bootstrap's card component in it](https://www.youtube.com/watch?v=iwJW18NA_S4).

## Install Bootstrap Barrio

[Bootstrap Barrio installation](https://www.drupal.org/project/bootstrap_barrio) has enough features and options plus frequent updates you are best off following the modules' specific instructions on the Drupal.org site.

## Extras/modules

If you decide to use the Bootstrap theme (or it's Barrio deployment) you may want to at the following contributed modules to enhance its utility even further.

### Views Bootstrap 

This module has unique install instructions depending on the version of Bootstrap you are using in theming. Views is one of the most powerful features of Drupal so having bootstrap features integrated with it is great.   Go to the Drupal.org site for the right version install instructions to [match your Bootstrap and Drupal versions](https://www.drupal.org/project/views_bootstrap).


### Bootstrap Layout Builder

First try using native Layout Builder after you have Bootstrap installed and set as default.  Then consider adding this views bootstrap module to get some potential additional functionality around accordion, carousel, etc.  Bootstrap Layout Builder uses different configuration settings for the grid layout choices, gutters, container widths, etc.  You can jump start the utility of its combination with Bootstrap by using this module.  See how using the [GUI interface in modern Drupal to do much of your front-end work, is enhanced by using this module with the Bootstrap theme.](https://www.youtube.com/watch?v=sMbiqSMiZ6Y)

`composer require drupal/bootstrap_layout_builder`<br>
`drush en bootstrap_layout_builder`

### Bootstrap Block Styles

The Block Styles Module adds a styles selector at the end of the block configuration form.  Included styles support Bootstrap Styles on submodule for (modal, Dropdown, card, and collapse). The assumption is that a dependency on the Styles API will install it at the same time.

`composer require drupal/block_styles`<br>
`drush en block_styles`

### Bootstrap Styles

This underlies the Bootstrap Layout Builder's styles plugins. 

`composer require drupal/bootstrap_styles`<br>
`drush en bootstrap_styles`

### Bootstrap Layout Builder Library

This is key to [saving reusable layout sections and whole templates within Bootstrap Layout builder's GUI interface](https://www.youtube.com/watch?v=-dhI5-Fs4qk) so you can speed development by grabbing stuff from a library you build up specific to your site.  Learn more about how this library add-on module allows for sharing templates and discussion of establishing a repository of templates](https://www.youtube.com/watch?v=E68DxSLcCd0) you might benefit from others work efforts. 

`composer require drupal/section_library`<br>
`drush en section_library`

### Bootstrap external link

This module provides a Pop up Modal warning of an external link leaving site.

`composer require drupal/bootstrap_external_link_popup`<br>
`drush en bootstrap_external_link_popup`

### Bootstrap SASS
[Bootstrap SASS](https://www.drupal.org/project/bootstrap_sass) provides the SASS approach to CSS compiling within Bootstrap.  It is typically listed as an option on the [Bootstrap Barrio theme overview.](https://www.drupal.org/project/bootstrap_barrio) Confirm that it isn't already installed via some sort of a dependency with the basic theme.  If you need to add the SASS Start Kit separately it is installed like a normal theme with composer.

`composer require drupal/bootstrap_sass`<br>
`drush en bootstrap_sass`

### Bootstrap Local

You probably don't need this module.  Normally the 'head' of your website pages will tell the page to look for the bootstrap library on the web.  There are times when having that bootstrap library locally can be useful.  For example, if you have an existing theme on your site and are replacing it with bootstrap you may prefer to do all your work locally; say in a Lando or other local Docker container instance of your website and put it through your normal [CI/CD workflow (e.g. GitOps).](../book/drupalcicd.md)  If you want to load the bootstrap library locally you use this module; otherwise you set up the CDN approach.

`composer require drupal/bootstrap_library`<br>
`drush en bootstrap_library`




May also consider adding this module for the capability that it enhances the normal link dialog in CKEditor to allow CSS classes, ID's, and Relation control (e.g. no follow, etc.).
composer require 'drupal/editor_advanced_link:^1.8'

The External Links module is a small module used to differentiate between internal and external links. Using jQuery, it will find all external links on a page and add an external icon  indicating it will take you offsite or a mail icon  for mailto: links.
composer require 'drupal/extlink:^1.6'

Flexslider module provides carousels and picture sliders; requires several configuration steps beyond the install and enable:
composer require 'drupal/flexslider:^2.0'
The flex slider Library is needed: http://flexslider.woothemes.com/
How TO: http://codekarate.com/daily-dose-of-drupal/drupal-8-flexslider-module
	https://www.youtube.com/watch?v=sKmmAL_dZtU&list=PLKdePeSydSBv9ro-	oJoxnhAFInyDdU4o9&index=1
COMPARE THIS TO SLICK CAROUSEL MODULE BEFORE COMMITTING:
composer require 'drupal/views_accordion:^2.0'
composer require 'drupal/views_slideshow:^4.8'

A pop up blocks. Use case might be cleaner log in, special offer with click through, ...
composer require 'drupal/simple_popup_blocks:^2.7'

This one needs serious testing and awaits Aimee's comments back on the sanity of even considering it.   But it offers Layout Builder on the fly block customization and export security potential risk reduction between environments.
composer require 'drupal/simple_block:^1.2'

Add classes to any block.  But make sure to test this with Layout Builder and the Bootstrap install because it requires modification of PHP level code at install.
composer require 'drupal/block_class:^1.3'


The Asset Injector Module is to inject both CSS and JS editor to tweak things without a full-fledged theme hack.  Consider it on a test site before jumping forward with it because it may be just as easy to do your own TWIG, HTML, CSS and JS editing without the overhead; so see how easy it is and if it carries negative overhead.
composer require 'drupal/asset_injector:^2.7'


Potential libraries to see if they have anything worth adding and testing if they are even compatible with Bootstrap framework:
Animate.css
Hover.css


Potential free image sources -
	Pexels.com
unsplash.com/
upsplash.com


composer require 'drupal/components:^3.0@beta'
Could be that the components module may offer some easy style editing via its GUI.  But you are probably better to stick with direct TWIG and CSS and JS editing.



****
Wow!   “you the man”.  Love your advice and it makes sense.  Bootstrap 4 Barrio seems so capable at the TWIG level.  And I have both made copies of those TWIG templates to modify them in my custom theme and I have added CSS to make further adjustments. The key is that I am probably pretty unskilled at it and thought I might be able to benefit from the components in Olivero to speed things up. But them when I started looking at what I would have to do to build the ‘functional’ elements I wanted to add to Olivero I headed your way for that key wisdom (Barrio -> Olivero, not Olivero -> Barrio).
I want to see if I am correctly understanding something else about this overall process.  At the foundational level, PHP itself has some potential to ‘theme’; and before Drupal 8 that was in fact where some level of it was done.  At the PHP level there are variables and in TWIG based Drupal, TWIG starts by addressing those variables and then doing something with them [if this first step is correct, is there a good way or tool to dump what PHP variables are most logically brought into TWIG for then further theming].    Within TWIG there isn’t too much you do to ‘make it pretty’ but that is where you might apply logic like any looping or functional manipulation that would benefit a theme.  But it is also within TWIG that you are to write your HTML that might hardcode something into the template while the template also grabs what is being pulled from the database to be presented.  The HTML is where you are preparing the first level ‘display’ characteristics of the presentation so you are defining a ‘card’, a ‘grid’, an ‘accordion’, ‘checkboxes’, ‘radio buttons’, etc. with that code; and most importantly defining ‘class’.  Then CSS generally is adding color, location, size, font style, and the ‘pretty’ aspects to the final presentation.    [please let me know if this is correct or where it is goofed up].
Assuming I am reasonably on track with the above, then the balancing act becomes how one might think about the HTML portion in the Layout Builder world.  If I was going to write native HTML I would be all worried about the DIV stacking so one part of the code isn’t stepping on the next.  But is it reasonable to assume that with Layout Builder you are assembling the blocks you have defined into a node and after you have it generally laid out using that tool you could look at the code in the developer view in your browser and you would see all the DIVs, Classes, IDs, etc. all ready generated; thus allowing you to tweak with CSS by addressing them at that point to make any final customization you desire?
I am hoping to get a broad handle on all the interconnections with the thought that I might copy, paste, and edit some components from one theme  to a totally different theme.  Like if I want to to grab some features I really like from Olivero and put them in Bootstrap.  I really like Olivero’s site-style logo & image contraction upon scroll and the menu approach and responsive presentation.  So that is mainly what I want to try to recreate.  Color schemes, and font styles, etc. are easy to make it look like that.  But I am thinking the core parts I like are doing to be much harder to figure out how they have set up because I suspect it is an interworking of PHP pass of the title, image and slogan fields to TWIG and then not only HTML and CSS but may involve JS to try to figure out.  But, if my description about how all these connect are generally on track, then it will be good practice to work on this.
Any place you know of that outlines ‘best practices’ on how you approach interconnecting these moving parts?  Seems like Drupal allows so many ways I could approach it.  But experienced people must has some principles they tend to stick to so others can work on their code later. Drupal 8+. In earlier versions of Drupal, you were able to insert PHP into theme files (the .tpl.php files) because of the theming “engine” that was being used. When Drupal 8 switched to Symphony, the theming engine was replaced with TWIG. Part of the reason was because TWIG is more code agnostic than what was used in earlier versions of Drupal, but also because it is a HUGE security risk to put PHP in the theme layer, because that is what gets executed last on a site. So any code in a .tpl.php file (or more likely the template.php file) was a big risk.  TWIG basically acts as an intermediary between PHP and the front end layer, by allowing you to perform simpler operations (if statements, loops, variables) without the need for full blown PHP functions. Therefore, you can have front end people working on the theme without opening security holes, but also giving you access to the more commonly used elements of PHP. That being said, you CAN still execute PHP in a theme, it is just relegated to the .theme file in your theme. This is mostly for setting theme wide variables that PHP interacts with but also for doing pre and post process steps. If you look at Barrio you will see a lot of what they do on the theme is contained in that because it was the easiest way to bring in Bootstrap 4 functionality to Drupal.  There is nothing wrong with copying over some of the functionality that you like from Olivero (or whatever) to your theme, I would just caution that you understand how the TWIG files are setup when you are copying - there are likely other variables that get referenced within the theme that you need to track down and then recreate in yours to get the full functionality. I would also say that a lot of Olivero may just be accomplished through modern CSS, though I honestly haven’t played with it in a while so I can’t remember. With a little bit of trial and error though, you should be able to recreate your desired effects through copying the TWIG files and mimicking the CSS in there. 

***
Beyond Core -

Drupal core is already very capable.  And there is even a tool called Layout Builder (in core, but must be enabled) and it really gives lots of ability to the newer users.   However, there are a ton of what are known as "front-end" options to use with Drupal; all the way to even doing a de-coupled site with a JS framework like React or Vue grabbing content from Drupal.  Closer to home, there are a few current and emerging modules that might be considered. 

For the options closer to home but that add capability, a review of a presentation from an Asheville Drupal Camp in the summer of 2020 is worth watching.  It is titled 'An Overview of Front End Component Integration Methods in Drupal' and can be found here:  https://www.youtube.com/watch?v=UQ-SRGVV9k8
About 17 minutes into the video two broad approached to integration of components is compared.  One is 'Mapping Data In Code'  and you can think of that as more at the TWIG or even PHP preprocessing level (which backend programmers probably gravitate toward).  The other is 'Mapping Data In Admin UI' and you can think of this as aiming toward integration with things like PatternLab and Storybook components.  This video is about understanding the options and their pros and cons; but it doesn't just boldly give an answer.

As discussed earlier, the variables from Drupal go through Twig Templates to provide a first level rendering of an entity like a page, block, etc.  You are going to want to work at the level of these templates at some point and we showed how different names, from generic to specific are shown with you have debug on.  To make that even easier, you might want to install and enable the Twig Debugger module that lets you click the little edit pencil from your GUI view of your page and then use your browser's 'source' view to see how that specific area of your page is controlled by a certain twig template (composer require drupal/twig_debugger and the drush en twig_debugger).

At the TWIG level two other helper modules are discussed in the video; 'Twig Field Value' and 'Twig Tweak'.  That later of these is broadly more capable so is worth considering.  The way to think about Twig Tweak as a module is that it aims to bring a richer toolset; but unlike a lot of modules don't necessarily think of it as a GUI keeping you away from code level efforts.  TWIG is a pretty rich framework in and of itself.  Drupal only brings a portion of it to bear.  What Twig Tweak will do is give you access to all the functions of the broader framework.  

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

