
# Architecture & Entities

In the [Content Management System Overview](../book/cms.md) it was noted that a CMS has a database component and a display component where "There is also code in between the data and display that applies any logic."  Some of that logic might be things you code to do stuff unique to your website; either coded directly or grabbed from a [contributed module](../chapters.md#drupal-modules) that has underlying code accomplishing what you want.   All that is being applied to Drupal's Core.  Understanding some of the logic in what Drupal Core is doing can be helpful in using Drupal no matter if you are just working with modules as a site builder or you get under the hood as a developer.

##  Information Types

In addition to the "parts" of a CMS being the front-end, the back-end, and the database, there are different ["information types" in Drupal.](https://api.drupal.org/api/drupal/core%21core.api.php/group/info_types/10)  The information types might be thought of cutting across all the parts but where an understanding of them is very valuable is between the back-end and the database.  The basic information types in Drupal are:

-  Session
-  State
-  Configuration
-  Content

The [Session information,](https://www.drupal.org/project/session_api) being things like is someone logged in, can be used in how you design or run your system.  This is especially true with things like ['Permissions by Role'](https://www.drupal.org/docs/7/understanding-drupal/users-permissions-and-roles) which Drupal is known to have extraordinarily effective management of in how it works.  Think about what you might show to an anonymous user versus a logged in user, verses a premium paying users, versus editors, and developers; all under your control.   And if what is in Core isn't enough there are contributed modules that take things even further with [Groups or what might be thought of as Departments in your organization.](https://www.drupal.org/project/group)

[State information]( https://www.drupal.org/docs/8/api/state-api/overview) can be thought of as more mechanical stuff the system itself generates.  Not as likely to be directly used in things you may do unless you are a developer.  Think of it often valuable in relating to 'time'; like when the the cache last updated or [CRON](https://www.drupal.org/docs/administering-a-drupal-site/cron-automated-tasks/cron-automated-tasks-overview) last run. 

[Configuration information](https://www.drupal.org/docs/drupal-apis/configuration-api) is something you care a lot about.  What will happen if you don't do anything with importing and exporting configurations, the work you do in setting things the way you want them as you get started will disappear.  I don't mean your Drupal installation will be gone.  Rather, things like the name you set, the theme change you made, the logo you applied, those will revert back to the default starting point because you didn't really save them.  The basics of saving your configuration are simply to think that what you have done [doesn't get saved until it gets converted into files, something called YML formats, and those making their way into the database.](https://www.youtube.com/watch?v=s46oXPDsJ3M)   That is the basic way, but if you are using the [Continuous Integration and Continuous Development Base Project we provide this configuration management process is set up across our multi-environment workflow.](../cicd/configatroot.md#you-care-about-this-one-now)

## Content Information Type
### Different than Content Type

"Content Information Type" is a step broader in context than the familiar [content type & adding fields to them](../book/contenttype.md) with which even novice site builders quickly become comfortable.  People quickly learn to use the 'article' and 'basic' content types present at installation and it is pretty straightforward to [create additional content types right from the Admin/Structure/Content Types GUI interface](https://www.drupal.org/docs/user_guide/hy/structure-content-type.html) 

### Content Entity

Both Configuration Information Types and Content Information Types are common "Entities" in Drupal.  Back to basics, just look at the definition of an [Entity](https://www.merriam-webster.com/dictionary/entity) as something of an independent, separate, or self-contained existence.  That is broad enough not to be terrible useful in telling us what Drupal actually considers as Entities of either of these types but does communicate the critical importance of separate and independent.  You intuitively know what 'Content' is in the context of ["Content Types"](../book/contenttype.md) like articles or what are on basic pages.  However, Drupal Core also considers a "User" as an entity of the "Content Information Type".  Makes sense; its not like an article, or a vendor, or a recipe, or a tree but it is an existing, independent, separate thing or entity.   Drupal also considers "Vocabulary", "Block", "Media", "Comment", and "Contact Form" as "Content Information Types".  Contributed modules have added [several more.](https://www.drupaleasy.com/blogs/ultimike/2021/01/10-fieldable-entity-types-every-drupal-developer-should-know-about)  With a tool called [Drupal Console](https://drupalconsole.com/) you can actually [query your system to see which entity types are available.](https://trainingcloud.io/blog/2021/05/drupal-8-9-listing-available-entity-types/)

### Fieldable

One of the things that makes Drupal superior is that it is 'fieldable'.  Not a farming term.  Rather, in the discussion on ['content types'](../book/contenttype.md) we saw how you can associate all sorts of different fields for you to use with them.  Not all 'Content Information Types' are necessarily fieldable.  'Content types' like articles and even users are.  But a 'content information type' like 'file' is not.  

Regarding field on 'content information types' we sort of need to think of a couple broad kinds.  One you might not normally think of is sometimes called 'properties' which are universally used; I mean unique individually but universally present.  An example is an 'id' for the entity or a 'vid' for the version of an entity. 

Another thing of about 'fieldable' is that in something like the 'article' content type that come with the initial install of Drupal, the field 'title' is a standard element within it.  There are times when you might not want the title. For example, let's say you are setting up just an image of magazine covers with an associated link that people click on to go to the magazine's website.  The cover of the magazine itself shows the name or title of it; so you do NOT want to display a redundant title obligated by the content type.  This is an area where you would look to [contributed modules that have been built by the Drupal community members to drop the title requirement from an entity.](../modules/entityref.md#exclude-title-module)

The better you understand the basics of these principles, the easier working with Drupal will be.  While a little old, one of the [clearest explanations of some of these field, node, type, bundle, entity things is from a video that Drupalize.me presents.](https://www.youtube.com/watch?v=coephBu07Ks)

## Entities

### Database

If you are from the database world you probably know about how you can see tables, relationships between tables, and fields in tables in an [Entity Relationship Diagram.](https://betterprogramming.pub/what-is-an-entity-relationship-diagram-d5db69a87971)  The data model presented in a good diagram can communicate additional perspective with the line end symbols you see between tables which communicate one-to-one, one-to-many, and many-to-many relationships.  For another time and place, you might even talk to a professional data architect and learn the interesting schema approaches that are used for various types of optimization.  Even more interesting might be to see an actual [entity relationship diagram for a modern Drupal database instance.](https://www.drupal.org/files/Drupal8_UPsitesWeb_Schema_10-19-2013.png)  Don't get too excited if you can't tell much from looking at the database storage view of a Drupal instance.

### Object Oriented 

Drupal is built using an Object Oriented Programming (OOP) approach with the [Symfony framework of PHP.](https://symfony.com/)   With Drupal's use of OOP you can think of [the PHP code driving the database and the front-end controller hints at the many functions the code pulls off relative to the underlying database.](https://api.drupal.org/api/drupal/core%21lib%21Drupal%21Core%21Database%21Database.php/class/Database/10)  If you glance through the related functions or classes listed as being associated with that database controller you and see how it makes fields, allows insertions, deletions, changes, etc.  This is the way you should think about Drupal data more so than trying to study its database tables.   For example, since additional entities can be created, you can assume that OOP is able to allow the insertion of a table into the relational database for storage needs unique to it.  For now, probably far enough down this part of the rabbit hole but if you are a developer you may want to understand [Drupal's Database abstraction layer](https://api.drupal.org/api/drupal/core%21lib%21Drupal%21Core%21Database%21database.api.php/group/database/10)  The key highlights to understand are that Drupal's domain module is [decoupled not only from the user-interface](../theme/decoupled.md) but also from storage.  Think about that last point in the sense of being able to select different databases that you connect to your Drupal website.  Without getting into PHP programming, you should also understand that Drupal's data domain is a configurable, structured, translatable, revisionable, typed document.   To understand what that means relative to Drupal being fieldable you need to <font color=yellow>shift your mindset from Drupal as database application to it really be a services and objects application in an</font> [object oriented programming (OOP)](https://en.wikipedia.org/wiki/Object-oriented_programming) <font color=yellow>language.</font> 

This may sound confusing and it would be if you had to build it all from scratch.  However, here's the thing.  With Drupal and OOP you get to stand on the shoulders of giants.  The reason is that PHP leverages the principle of ["Object Inheritance"](https://www.php.net/manual/en/language.oop5.inheritance.php) in an absolutely great way.  And, to some extent, this is why some people are so fixated on Drupal version history as a way to really obtaining an absolutely full understanding.  For our purposes, what we need to understand is that someone most likely as plowed the ground we want to work with long before use and has built and packaged the underlying parts.  Sort of like in that database front-end controller noted in the prior paragraph.  You don't have to write code for the process of adding a field, inserting and deleting a record in it, checking format requirement rules, retrieving key:value pairs to use in your logic, etc.  You jut need to know the package of actions you need and "extend" from it to "Inherit" all the goodies for your purposes.

With that mindset and the fact that "Classes" in OOP provide the definition for data formats and may even contain data you can think of Drupal as programmatically inserting fields when and where it needs it via code syntax.  Then it has things like its [DataDefinitions and Creation types of functions to have the data if dynamically defines inject what is needed into the supporting database](https://www.youtube.com/watch?v=mQHkKq5UUHo) you have elected to use.  Unless you are aiming to be a Core Contributor to Drupal, you probably will find the actual complexity mind boggling but here is an example of the many functional parts that are called together to just assemble a basic field in Drupal.  

<img src="../book/images/media/datadefinition.png"  width="500">

Perhaps of more direct practical value is to look at the [Drupal Entity API.](https://api.drupal.org/api/drupal/core%21lib%21Drupal%21Core%21Entity%21entity.api.php/group/entity_api/10)  Again, if we remember that we should think about Drupal as a services and objects OOP application that drives the supporting data structure, it is more valuable to know how the classes and functions in Drupal's [Symfony](https://symfony.com/) underpinnings are interacting to define and manage data, entities, and fields.


### Understand? Care?

However, even that might be more than a basic site builder is going to care alot about in Drupal.  Rather, one probably simply wants to think of Drupal as able to make new entities, edit, and insert or remove fields in them, and manage the supporting the database structure behind all this that makes a home to store your important stuff.  From that mindset, you can then probably better understand [contributed modules which do extra things on your behalf around the entity concept.](../modules/entityref.md) 

It has previously been noted that Object Inheritance in OOP sets up a way to call various pre-established sub-functions to then build upon for your own use.  This can involve 'BaseXxxxx' being "Extended" and using the "Get" function to use things you need.  With respect to moving from the GUI world to really getting into creating Entities at the code level this veiw of the [Enitity API interactions with the database](https://www.youtube.com/watch?v=FrSjwe8bh7I) is a pretty long and complicated overview but will help you understand if you want to move into the full developer world.  The only caution I would suggest in watching it is to pay attention in the many "you can to it several ways" examples to the last, and preferred way in each; then take notes or screenshot that syntax to get yourself going.

Trying to relate a GUI you have been used to working with and the underlying OOP that is behind it, especially with the Object Inheritance stringing all sorts of part together needs you to consider using the [WebProfiler Module.](https://www.webwash.net/debug-site-performance-using-web-profiler-in-drupal-8/) About 3-minutes into that video you will see Ivan go into configuration and activate two part to the module that weren't on by default.  After he does that you will all of a sudden get the idea on how all these PHP components are available and being used to create a potentially simple looking page.  Another step to seeing the developer world view of Drupal.

## Just Make One

Ok, you don't need to know how to be a great chef to enjoy a good meal.  Same thing with adding a whole new entity type.  There are tools that help do this on your behalf.  That [Drupal Console we talked about earlier is one way to add a custom entity.](https://www.youtube.com/watch?v=leodwoFUm54) And just like so many other things in Drupal, there's also [a module to create a custom entity](https://www.youtube.com/watch?v=9eDyAWE5WHw)


<br>
<br>
<br>

[Learn more... Drupal Basics](../chapters.md#drupal-basics)
