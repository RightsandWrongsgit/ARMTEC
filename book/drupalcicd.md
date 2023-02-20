# Drupal CI/CD Base Project

## What is CI/CD?

Continuous integration and continuous deployment is a fancy way of saying "instead of building everything at once, launch your website and enhance it in steps".   Sure you have a brilliant [design]() because you put in the effort in advance of starting to program things.  Even if you think it is perfection now, any website grows better with feedback and improvement steps.  But you don't want to "break" what is out there now to add a new feature.  So people work on a copy of their site, test the full updated site, and then deploy or replace what was out there with the new, improved version.

## Version Control

When we talk about versions, you might think much more incrementally than say a version reprint of a book.  That is perhaps a good analogy for full fledged updates of your published or 'production' website.  But version control is also used a sort of an incremental backup process as you code or install new features while you are working.  You don't want to go to bed at night or even to lunch worrying if what you just invested a bunch of effort in is going to be safe.  People use ['Git](book/gitbasics.md)' and its related connecting parts to manage this version control process. 


## Drupal development with CI/CD version control

[Drupal]() is a really outstanding content management system ([CMS]()) style website development building tool.  With great power and flexibility comes a level of complexity that can make people initially uncomfortable.    There are thousands of underlying files to scare you; but, you probably aren't going to really touch all that many.  You are, however, at some point likely need to look at the 'directory structure' where those things are organized and find your way into a few.  To do that we use an open source 'integrated development environment'(IDE) tool called [VSCode]().  And VSCode integrates with that 'Git' stuff we talked about a moment ago.  Since that 'Git' version control is going to have a 'local' environment with a [container]() called [Lando](book/lando.html) running your development copy of your website, somehow this needs to connect to a publicly available 'hosted' copy of your website called its 'main' production branch.  In our case we are using a host called [Platform.sh](https://platform.sh/).  That host really talks to a copy which you 'Git' control puts out in a 'Git Repository', which in our case will be on [GitHub](https://github.com/).    What sounds like it might be a complicated process is also known as [DevOps]() and in our case that Platform.sh host is going to do a ton of the heavy lifting.  More good news, this project documentation is cookbook like to get things going and offered in two flavors – 1) tell me the way it is put together or 2) just show me [how to use it](to the GitHub readme).  

-  [Prepare my computer setup](cicd/prerequisites.md)
-  [How to use it]()
-  [Install Drupal with Platform.sh Template](/ARMTEC/blob/gh-pages/platfromshdrupal.md)
-  [Tell me how it is put together]()


