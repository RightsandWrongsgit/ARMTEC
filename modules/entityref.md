
# Entity Reference modules


## Exclude Node Title module

`composer require drupal/exclude_node_title`<br>
`drush en exclude_node title`

## Media Entity Embed module
#### Inline Entity Form, Entity Browser, Entity Embed dependencies

"consider this module a priority" 

`composer require drupal/media_entity_browser`<br>
`drush en media_entity_browser`

## Entity Reference Revisions module

`composer require drupal/entity_reference_revisions`<br>
`drush en entity_reference_revisions`

## Entity Browser Enhanced module

`composer require drupal/entity_browser_enhanced`<br>
`drush en entity_browser_enhanced`

## Entity Usage module

`composer require drupal/entity_usage`<br>
`drush en entity_usage`

## Entity Reference Preview module

`composer require drupal/entity_reference_preview`<br>
`drush en entity_reference_preview`

## Link Related Entitities module

[Linking two related entities (e.g. person like spouses, children)](https://www.drupal.org/project/cer)


## Block Visibility Groups module
#### Enhancement to control and placement of blocks

You can put the [Block Visiblity Group module](https://www.drupal.org/project/block_visibility_groups) in the "greater than sliced bread" category!  Think of website building as putting chucks of things in different areas for display.  You probably already know this relative to 'Regions' that your theme includes.  People who have used an older approach called Panels also know about moving chucks of stuff in different parts of a region.  Drupal from version 8 forward rallys around the use of Blocks for the term of what these chucks are called; and if you use the GUI drag-n-drop Layout Builder function included in Drupal Core you also know how moving the blocks around is pretty cool.  You also may know about how in the 'Administration/Structure' menu in your Drupal site building system you can look at a Blocks Layout Page you can see on what content type and region blocks appear.  But sometimes you want those blocks to show up conditionally; say for a logged in user versus a stop-by.  See this [quick video on how the Block Visibility Group module adds conditional control in a very simple, comfortable way.](https://www.youtube.com/watch?v=ZKwkaMUbJIs)

`composer require drupal/block_visibility_groups`<br>
`drush en block_visibility_groups`

## Add Another module
#### Sort of speed copy another replication of a node

`composer require drupal/addanother`<br>
`drush en addanother`

## Content Type Modules

[Acquia](https://www.acquia.com/) is a commercial company founded by the [original developer of Drupal.](https://dri.es/)  They continue to [Open Source](../book/opensource.md) many of the tools they use.  You might want to glance through their GitHub repository, especially their [Acquia/CMS that provides some modules aimed at building some valuable content types.](https://github.com/acquia/acquia_cms/tree/develop/modules) for things like Person, Event, Place, Document, etc.
************




Media Entity Embed Module:
Media is discussed more later but one thing you probably want to consider it that media also may be reused in other entities more than once, so we can treat it like an entity reference with this module to embed it as we needed.  This module leverages the 'Inline Entity Form' module, the 'Entity Browser' module, and the 'Entity Embed' module (https://www.youtube.com/watch?v=PA9PVwWClX0); so if we logically prioritize it for installation and being enabled, we can do a bunch of things we want all at once.  It is also worth checking out Ivan's video on how you can embed blocks in an entity like an article, basic page or whatever in a much more coordinated way then is found just in Core (https://www.youtube.com/watch?v=PYTb-WwIt40). Using Firefox has some GUI advantages with using this resizing step over Safari or Chrome.

- CONSIDER THIS MODULE A PRIORITY FOR INSTALLATION AND ENABLING -

composer require drupal/media_entity_browser
drush en media_entity_browser


Entity Reference (automatically in Core):
You care a lot about this entity reference stuff and are going to add a bunch of contributed modules that have been developed to make it easier to use.  The general logic of entity reference is better ways to put stuff together rather than re-enter or redundantly maintain stuff.  An example might be something like you wanting to put a staff list in your menu where you have pictures of people, their unique email and phone numbers, but also want to list their business address which is broadly the same for those at the same physical location.  Instead of redundantly putting it in a dozen times, you make a business address entity for each site your business operates, and then when you create an entity with each staff picture and contact information you just 'reference' the business site address entity(ies) you created to plunk them in.  That is an entity reference, one entity referring to another.  

Don't get too hung up on the name of the article or its worry about some pitfalls on how the basic core entity reference can cause some bumps for content editors. But a review of this article gives a good overview of the logic of being able to not only use entity references but on how to update entities that are involved …  https://www.lullabot.com/articles/dangers-inline-editing-structured-content

Entity Reference Revisions module:
So one way you are not going to worry about the update points in that article is that you are going to install and enable this module.  

composer require drupal/entity_reference_revisions
drush en entity_reference_revisions


Entity Browser module: 
Sounds like a good idea to use that entity reference stuff but how about chasing down what you have available to reference?  Yeah, figuring that out on a site of any size in terms of stuff or entities already developed can be a pain, so some bright people developed the Entity Browser module to solve the problem; install and enable it.

composer require drupal/entity_browser
drush en entity_browser



Entity Browser Enhanced module:
This module add some features like multi-select to the basic entity browser module.  

composer require drupal/entity_browser_enhanced
drush en entity_browser_enhanced



Entity Usage module:
Alright, you are now so bright you know about entity references and you can even browse entities to find what you might want to reference where.  But, you probably don't remember from last time you worked on the site where all those entity references are and what you have referenced by what.  So you want to install and enable the Entity Usage module.

composer require drupal/entity_usage
drush en entity_usage



Entity Reference Preview module:
As that link on entity references warns, the 'revision' management relationship for referenced items isn't out of the box in synch with the edits you might have made to the parent entity it is linked to.  What that means is that your edit preview might be the unpublished revision you just worked on but the referenced entity connected to it is the published not the unpublished working edit version.  This Entity Reference Preview module steps up to that issue so you can see a previews of edits on the base entity and on any edits you made 'inline' to the referenced entity. 

composer require drupal/entity_reference_preview
drush en entity_reference_preview



Entity Construction Kit (ECK) Module:
This module is only going to be of value for some pretty specific needs; but important ones when they arise.  It actually supports you in creating a whole new entity TYPE.  Not a content type with is a Node Entity.  A User Entity is another existing entity type.  But what happens is that entity types have bundles associated with them like fields in content type node entities.  You, however, may not want to be at the mercy of Drupal standard entities because of the bundle definitions.  A one to many heirarchy but that has different allowable substructures is an example where two different bundles of your own making is important.  Vehicles might split by cars, trucks, motorcycles, airplanes, tanks, etc. and the same feature fields wouldn't always be common (although some are).  Thus you might want to make your own content type for vehicles but split the bundles by those different vehicle types so that trucks can have beds, airplanes different wing configurations, etc.  The ECK module is the tool for you to do this type of thing.  An old, but still relevant video gives the basic logic even if the exact GUI might have shifted some which module updates … http://codekarate.com/daily-dose-of-drupal/drupal-7-entity-construction-kit

composer require drupal/eck
drush en eck


<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)


