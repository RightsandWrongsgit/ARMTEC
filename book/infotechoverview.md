
# Information Technology

## Starters

Feeling overwhelmed with technical stuff. Don't worry, we can help you [get started with the basics.](Novice.md)

[Git Version Control](../book/gitbasics.md) is a great tool for saving your work automatically and rolling back to a safe point. Additionally, [Integrated Development Environments](../book/ide.md) can present all the different parts you work with in a more user-friendly way.

Concerned about spending money on software tools?  There are [Open Source Tools](../book/opensource.md) you can use for free and they provide outstanding functionality.

As for remembering everything, we have [links to cheatsheets](../book/cheats.md) that you can consult whenever you need to reference something. And if you still have questions about something that seems too basic, don't hesitate to check out our ["It May be Basic But Sometimes You Need a Boost!" section.](../book/Novice.md)

Remember, the key is to start slow and crawl before you can gallop. Good luck!
 
## Content Management Systems (CMS)

Information technology is more than just the internet. These days most things are internet connected; even if just to use the pipes between remotely hosted sites. It can help to think of the Front-End and Back-End parts of applications and tools. The Front-End is what we interact with on our devices, like [browsers.]( https://en.wikipedia.org/wiki/Web_browser)  HTML, CSS, and JavaScript are examples of Front-End tools. They communicate with the Back-End, which handles heavy logic and number crunching using tools like TWIG, PHP, and Python. Behind it all are databases where information is stored. Content Management Systems excel at managing all these levels, making them superior to simple websites.

Lots of the websites you stumble across, especially for tiny businesses, organizations, or individuals just have some images and words in various sizes and locations.  Sometimes they don't even have more than a single page while others have a menu with say half a dozen linked pages.  You ought to [write one of those yourself using HTML](https://www.tutorialstonight.com/html-web-page-examples-with-source-code) as a good way to practice and understand the basics.   Same sort of thing with [CSS which works to make the HTML structure of a page look better](https://www.tutorialstonight.com/how-to-use-css-in-html).  Find more about [free for practice websites here](../book/hosting.md#a-free-static-website-for-practice).

A [Content Management System (CMS)](../book/cms.md) uses HTML, CSS, and JavaScript for the front-end, while connecting to the back-end for logic control and database storage. It allows you to create reusable "buckets". In the [Drupal CMS](https://www.drupal.org/) these buckets are called [Content Types;](https://www.youtube.com/watch?v=soQ6N7oVkI0) like an 'article' styles and an 'advertisement' style for a newspaper. This saves time by not starting from scratch with every detail.

## Core Plus

Drupal is the go-to Content Management System for universities, governments, and major businesses due to its security advantages and flexibility. It's not as widely used as Wordpress, but it's the top choice for sophisticated sites. One standout feature of Drupal is its ['fieldable' entities,](https://www.drupal.org/docs/7/api/entity-api/an-introduction-to-entities) allowing customization beyond just content buckets. However, Drupal's flexibility can also be overwhelming, as it comes with a stripped-down core installation. Think of it as buying a car without all the necessary components. To enhance Drupal's functionality, you can add modules, which are like option packages. Check out our [list of recommended modules](../book/chapters.md#drupal-modules); they're just a fraction of what's available, but we've found them most useful for our projects.  Don't believe us?  We will let the [advocates]( https://www.digitalpolygon.com/blog/top-benefits-of-drupal) detail the [praises of Drupal](https://www.drupal.org/docs/7/understanding-drupal/what-are-some-of-the-commonly-advantages-of-drupal).  

## Build/Host

Drupal code is like any other computer code and sits in files in directories on a computer.  There are a whole lot of files and a whole lot of directories.  A broad [roadmap gives you a feel](../cicd/directorymap.md) and the value of using an [Integrated Development Environment](../book/ide.md) becomes pretty clear.   So where exactly are all these files and directories?  If you have a live, production website they are located at the [Host](../book/hosting.md).

You don't typically use that hosted production website as a place where you directly make changes.  It would be dangerous if you mess something up that your site would be off-line until it is fixed.  Also, it is virtually never that you are a one & done website developer; rather you build, deploy, enhance, redeploy, in a series of improvements over time.  How you do that is using a [Continuous Integration/Continuous Deployment workflow](../book/drupalcicd.md) that is provided here.


<br>
<br>
<br>

[More Chapters on - Information Technology](../chapters.md#information-technology)
