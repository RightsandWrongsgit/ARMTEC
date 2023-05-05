
# TWIG

Wow!  As usual "you the man".  Love your advice and it makes sense.  Bootstrap 4 Barrio seems so capable at the TWIG level.  And I have both made copies of those TWIG templates to modify them in my custom theme and I have added CSS to make further adjustments. The key is that I am probably pretty unskilled at it and thought I might be able to benefit from the components in Olivero to speed things up. But them when I started looking at what I would have to do to build the 'functional' elements I wanted to add to Olivero I headed your way for that key wisdom (Barrio -> Olivero, not Olivero -> Barrio).

I want to see if I am correctly understanding something else about this overall process.  At the foundational level, PHP itself has some potential to 'theme'; and before Drupal 8 that was in fact where some level of it was done.  At the PHP level there are variables and in TWIG based Drupal, TWIG starts by addressing those variables and then doing something with them [if this first step is correct, is there a good way or tool to dump what PHP variables are most logically brought into TWIG for then further theming].    Within TWIG there isn't too much you do to 'make it pretty' but that is where you might apply logic like any looping or functional manipulation that would benefit a theme.  But it is also within TWIG that you are to write your HTML that might hardcode something into the template while the template also grabs what is being pulled from the database to be presented.  The HTML is where you are preparing the first level 'display' characteristics of the presentation so you are defining a 'card', a 'grid', an 'accordion', 'checkboxes', 'radio buttons', etc. with that code; and most importantly defining 'class'.  Then CSS generally is adding color, location, size, font style, and the 'pretty' aspects to the final presentation.    [please let me know if this is correct or where it is goofed up].

Assuming I am reasonably on track with the above, then the balancing act becomes how one might think about the HTML portion in the Layout Builder world.  If I was going to write native HTML I would be all worried about the DIV stacking so one part of the code isn't stepping on the next.  But is it reasonable to assume that with Layout Builder you are assembling the blocks you have defined into a node and after you have it generally laid out using that tool you could look at the code in the developer view in your browser and you would see all the DIVs, Classes, IDs, etc. all ready generated; thus allowing you to tweak with CSS by addressing them at that point to make any final customization you desire?

I am hoping to get a broad handle on all the interconnections with the thought that I might copy, paste, and edit some components from one theme  to a totally different theme.  Like if I want to to grab some features I really like from Olivero and put them in Bootstrap.  I really like Olivero's site-style logo & image contraction upon scroll and the menu approach and responsive presentation.  So that is mainly what I want to try to recreate.  Color schemes, and font styles, etc. are easy to make it look like that.  But I am thinking the core parts I like are doing to be much harder to figure out how they have set up because I suspect it is an interworking of PHP pass of the title, image and slogan fields to TWIG and then not only HTML and CSS but may involve JS to try to figure out.  But, if my description about how all these connect are generally on track, then it will be good practice to work on this.

Any place you know of that outlines 'best practices' on how you approach interconnecting these moving parts?  Seems like Drupal allows so many ways I could approach it.  But experienced people must has some principles they tend to stick to so others can work on their code later.
Drupal 8+. In earlier versions of Drupal, you were able to insert PHP into theme files (the .tpl.php files) because of the theming “engine” that was being used. When Drupal 8 switched to Symphony, the theming engine was replaced with TWIG. Part of the reason was because TWIG is more code agnostic than what was used in earlier versions of Drupal, but also because it is a HUGE security risk to put PHP in the theme layer, because that is what gets executed last on a site. So any code in a .tpl.php file (or more likely the template.php file) was a big risk.  TWIG basically acts as an intermediary between PHP and the front end layer, by allowing you to perform simpler operations (if statements, loops, variables) without the need for full blown PHP functions. Therefore, you can have front end people working on the theme without opening security holes, but also giving you access to the more commonly used elements of PHP. That being said, you CAN still execute PHP in a theme, it is just relegated to the .theme file in your theme. This is mostly for setting theme wide variables that PHP interacts with but also for doing pre and post process steps. If you look at Barrio you will see a lot of what they do on the theme is contained in that because it was the easiest way to bring in Bootstrap 4 functionality to Drupal.  There is nothing wrong with copying over some of the functionality that you like from Olivero (or whatever) to your theme, I would just caution that you understand how the TWIG files are setup when you are copying - there are likely other variables that get referenced within the theme that you need to track down and then recreate in yours to get the full functionality. I would also say that a lot of Olivero may just be accomplished through modern CSS, though I honestly haven’t played with it in a while so I can’t remember. With a little bit of trial and error though, you should be able to recreate your desired effects through copying the TWIG files and mimicking the CSS in there. 



[EXAMPLE CONNECTING PHP TO THEME YMAL AND TWIG THAT SHOWS USE OF HOOKS](https://www.youtube.com/watch?v=AXtozyHIa040)

## TWIG Tweak

`composer require drupal/twig_tweak`
`drush en twig_tweak`

[Practice trial TWIG edit approaches](TwigFiddle.com)
[Twig Tweak Cheatsheet](https://git.drupalcode.org/project/twig_tweak/-/blob/3.x/docs/cheat-sheet.md)
[Twig Tools and Pattern Lab component linking](https://www.videodrupal.org/video/20210127/integrating-components-drupal-mapping-fields)


## TWIG - Command Line
Selwyn Polit's online Drupal book is also helpful if you are ready to work at the [detailed TWIG code level help](https://selwynpolit.github.io/d9book/twig.html)


<br>
<br>
<br>

[Learn More - CMS Front-end](../chapters.md#front-end)
