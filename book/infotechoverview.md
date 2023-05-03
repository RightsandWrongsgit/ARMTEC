
# Information Technology

## Starters

Crawl to Gallop is what you should aim for here.  Sometimes this technical stuff is head spinning.  However, that is just because no one [got you started on the basics](Novice.md).  Expect to find an understanding of a great safety net with [Git & Version Control](../book/gitbasics.md); it shows how your work can be saved automatically and how you can backpedal to a prior safe point.    Then there are all those many parts and we show how an [Integrated Development Environment](../book/ide.md) presents them to you in an easier to use way.   You worry that you are going to have to spend all that money on those software tools you don't even know if you will really use… so we introduce the concept of [Open Source Tools](../book/opensource.md) to start you for free.  But there is so much to remember!  For that we provide links to the [Cheatsheets](../book/cheats.md) to reference what you need like a pro.  Still lots of things you don't understand that you are worried are even too redimentary to even ask… try our [It May be Basic but sometimes you need a boost!](../book/Novice.md) section.  

## Content Management Systems (CMS)

Most people think of information technology as the web or internet.  These days most things are there at some level; even if it is just to use the pipes to exchange between remotely hosted sites. Sometimes it helps to think of Front-End and Back-End parts to broadly group applications, tools, jobs, etc. Think about the Front-End as your ['browser']( https://en.wikipedia.org/wiki/Web_browser) on a computer, phone, tablet, or other device; the point at which some human interacts with a system.  Tools like HTML, CSS, JavaScript(JS), operate at that Front-End level.  They talk to the Back-End with things like TWIG, PHP, Python, and many more tools that tend to run more heavy duty logic or number crunching.  Behind those are databases where information like those numbers, lists, names, etc. are stored as fields or variables to be worked upon by the logic.   Content Management Systems work across the full breadth of these levels and in that sense have a big leg up over just a simple website.

Lots of the websites you stumble across, especially for tiny businesses, organizations, or individuals just have some images and words in various sizes and locations.  Sometimes they don't even have more than a single page while others they have a menu with say half a dozen pages that are linked.  You ought to [write oen of those yourself using HTML](https://www.tutorialstonight.com/html-web-page-examples-with-source-code] as a good way to practice and understand the basics.   Same sort of thing with [CSS which works to make the HTML structure of a page look better](https://www.tutorialstonight.com/how-to-use-css-in-html).  Find more about [free for practice websites here](../book/hosting.md#a-free-static-website-for-practice).

A Content Management System has the Front-End support of HTML, CSS, JavaScript, while talking to the Back-End for more logic control and to store and retrieve from the database.   What is does is allow you to create formatted buckets to reuse.  You can make a bunch of different buckets in different styles that fit different ways you want to present what you have to say.  In Drupal, these buckets would be called ['Content Types'](https://www.youtube.com/watch?v=soQ6N7oVkI0).   Think about this in the context of something like a newspaper and you might have buckets for the articles and for different styles of ads; you might even have different article styles for the sports, news, financial and social sections.  The main point is you are creating something reusable so you don't have to start from scratch with every minuscule detail each time. 

## Core Plus

Drupal is the premiere Content Management System.   While Wordpress is used on more sites, the largest or more sophisticated sites of universities, governments, major businesses, etc. turn to Drupal.  A lot of that has to do with security advantages and the scope of flexibility offered by Drupal.  We will let the [advocates]( https://www.digitalpolygon.com/blog/top-benefits-of-drupal) [detail the praises](https://www.drupal.org/docs/7/understanding-drupal/what-are-some-of-the-commonly-advantages-of-drupal).  One worth special mention is that Drupal is what is know as ['fieldable'](https://www.drupal.org/docs/7/api/entity-api/an-introduction-to-entities) for all of its entities, not just those content buckets but things like users or even totally customized components.  

Drupal can be a confusing challenge because of all of its flexibility.  So many people make so many very different things with Drupal that its first installation or 'Core' is stripped to a minimum.  Like think of going to buy a car as start with ordering only the frame, wheels, and engine block; then being asked to install the carburetor or fuel injection system, seats, a truck bed, a camper, side mirrors, etc.  If you bought a car that way it would drive you nuts and you would love it when someone offered you some option packages.  In Drupal you now understand Modules… stuff you add on to core that does things you want.  A list of those Modules you most likely will want are provided in the [List of Chapters](chapters.md# drupal-modules).  Understand these are just a fraction of the tens of thousands of Modules available and are presented just because we find them most useful for projects we have done.


## Build/Host

Drupal code is like any other computer code and sits in files in directories on a computer.  There are a whole lot of files and a whole lot of directories.  A broad [roadmap gives you a feel](../cicd/directorymap.md) and the value of using an [Integrated Development Environment](../book/ide.md) becomes pretty clear.   So where exactly are all these files and directories?  If you have a live, production website they are located at the [Host](../book/hosting.md).

You don't typically use that hosted production website as a place where you directly make changes.  It would be dangerous if you mess something up that your site would be off-line until it is fixed.  Also, it is virtually never that you are a one & done website developer; rather you build, deploy, enhance, redeploy, in a series of improvements over time.  How you do that is using a [Continuous Integration/Continuous Deployment workflow](../book/drupalcicd.md) that is provided here.


<br>
<br>
<br>

[More Chapters on - Information Technology](../chapters.md#information-technology)
