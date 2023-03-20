# Drupal CI/CD Base Project

## What is CI/CD?

Are you tired of spending countless hours manually deploying your website? Or maybe your don't even know how. With our continuous integration and deployment solution, you can launch your website quickly and easily. Our solution allows you to build, test, and deploy your website in stages, so you can make sure that everything is working correctly before launching and keep your base site running while you develop enhancements. Plus, our platform is designed to be user-friendly so that even the most novice user can get up and running quickly.  We even lead you to open source tools to help you have a brilliant [design](book/opensource.md#Design-Your-Site:) for your website before you put in the effort to start programming things. 

## Version Control

When we talk about versions, you might think much more incrementally than say a version reprint of a book.  That is perhaps a good analogy for full fledged updates of your published or 'production' website.  But version control is also used a sort of an incremental backup process as you code or install new features while you are working.  You don't want to go to bed at night or even to lunch worrying if what you just invested a bunch of effort in is going to be safe.  People use [Git](book/gitbasics.md) and its related connecting parts to manage this version control process. 


## Drupal development with CI/CD version control

[Drupal]() is a really outstanding content management system ([CMS]()) style website development building tool.  With great power and flexibility comes a level of complexity that can make people initially uncomfortable.    There are thousands of underlying files to scare you; but, you probably aren't going to really touch all that many.  You are, however, at some point likely need to look at the [directory structure](../cicd/directorymap.md) where those things are organized and find your way into a few.  To do that we use an open source 'integrated development environment'(IDE) tool called [VSCode]().

VSCode integrates with that 'Git' version control stuff.  'Git' version control is on your personal computer. You are going to have a 'local' environment with a [container]() called [Lando](book/lando.html) running your local copy of your website.  That 'local' copy needs to connect to a publicly available 'hosted' copy of your website called its 'main' production branch.  In our case we are using a host called [Platform.sh](https://platform.sh/).  Our 'local' copy under 'Git' control is also going to be connected to a 'Git Repository', which in our case will be on [GitHub](https://github.com/).    This workflow process is a basic approach to [DevOps](https://www.atlassian.com/devops#:~:text=DevOps%20is%20a%20set%20of,and%20collaboration%2C%20and%20technology%20automation.) and in our case the Platform.sh host is doing a ton of the heavy lifting.  More good news, this project documentation is cookbook like to get things going and offered in two flavors – 1) tell me the way it is put together or 2) just show me how to use it.  

## I just want to use it
-  [How to use it](../cicd/howtouseit.md)


## I kind of need to know how it works
-  [Overview](../cicd/cicdoverview.md)
-  [Prerequisites](../cicd/prerequisites.md)
-  [Install 'main' on Host](../cicd/platformshdrupal.md)
-  [Local Copy](../cicd/bringitlocal.md)
-  [Using our IDE](../cicd/vscodedrupallocal.md)
-  [Safely Connect](../cicd/gitignore.md)
-  [GitHub Too](../cicd/cruisevscode.md)
-  [Mid-Point Check](../cicd/midpoint.md)
-  [Split Preparation](../cicd/basebeforesplit.md)
-  [Directory Map](../cicd/directorymap.md)
-  [Protect Config at root](../cicd/configatroot.md)
-  [Intro to Split Configuration](../cicd/configsplit.md)
-  [Configuration Directories & Module](../cicd/configsplit2.md)
-  [Configurations by Split: Table](../cicd/configsplit3.md)
-  [Environment Indicator](../cicd/envindicator.md)
-  [Environment Settings](../cicd/envsettings.md)
-  [Put Config Split In Place](../cicd/splitcheck.md)
-  [Structure Sync](../cicd/structuresync.md)
-  [UUIDs: Friend or Foe](../cicd/UUID.md)


## &nbsp;&nbsp;&nbsp;&nbsp;* Appendices
- [Adding php xdebug](../cicd/xdebug.md)
- [CSS & JS Advanced Aggregation](../cicd/advancedaggregation.md)
- [Drupal Scaffold ("overwrite": false) solution](../cicd/scaffold.md)
- [Reestablishing your GitHub-Platform.sh Integration](../cicd/expiredconnection.md)
- [SubTheme Setup](../cicd/subtheme.md)
- [UUIDs: Actually Change them](../cicd/changeUUID.md)



