
# Edit an Entity 

Entities are a foundational concept in Drupal.  Most commonly people think about the Content Type entity which they most often work with for what they are putting into there website.  Perhaps next they think about User or Permission related entity considerations.  If this entity concept is not part of your existing understanding, before you look at the various contributed modules that follow, please take the time to first read the section on [Architecture and Entities](../book/archandentities.md)


## Exclude Title or Author 

It is standard that out of the box Drupal will put a Title on a Content Node as well as the Authored by/when information.  If you have some reason you don't want this to show up, you can exclude either.

### Exclude Title Module

`composer require drupal/exclude_node_title`<br>
`drush en exclude_node_title`

### Exclude Author Module

`composer require drupal/exclude_node_author`<br>
`drush en exclude_node_author`

# Link an Entity

Remember that in Drupal there all lots of different types of entities even before you would move to [create you own.](#create-one)  The most common are content and user entities but don't forget comments, files, and media.   Linking entities is typical; think about how your content entity probably would benefit from a media entity used in it.  And media entities come in different types like images, videos, audio, and a whole bunch of [Media provider modules;](https://www.drupal.org/project/media_entity) things like Twitter, Facebook, Instagram, etc.

## Media 

The more modern versions of Drupal have incorporated [Media Management](../modules/media.md) right into the Core.  The reason this happened is  media are part of a website content page so often that contributed modules had been built and were heavily utilized to accomplish this.  Several of the most common were integrated and folded into Drupal Core to make it easier for people to get started.  For the new core media basics, it is probably easiest to just go into your Administration/Extend option and enable the media and media library modules.

### Media Entity Browser

The [Media Entity Browser](https://www.drupal.org/project/media_entity_browser) has mostly been replaced by what is in core; but not totally.  So some people might want to go the extra step.  Remember that with Media Entity Browser you basically get the underlying 'Inline Entity Form', 'Entity Embed', and 'Entity Browser'.  <font color=yellow>You care about all of them but having that last one in place is key for several others we will look at next.</font>

### Entity Browser module 

The [Entity Browser module](https://www.drupal.org/project/entity_browser) is probably not something you are going to bother adding on a stand alone basis if you are using the [media management already part of Drupal Core.](../modules/media.md)  However, what follows are several additional entity linking types of modules which have a dependency on it and would, therefore, bring it into play if you elect to use any of them.  The authors describe this as a 'generic picker' module that you can expect to use against all sorts of different entities.  You can even use it to [do something like create checkbox selections of a taxonomy term you added to classify something on your nodes](https://ostraining.com/blog/drupal/embed-entity-in-node-form/)  If you get into [creating your own entity](#create-one) and love all that stuff under [architecture and entities](../book/archandentities.md) this might be a perfect opportunity to clone and edit one of the tools used for another entity type and code your own companion tool for your custom entity.

### Entity Browser Enhanced

This module adds some features like multi-select to the basic entity browser module.  

`composer require drupal/entity_browser_enhanced`<br>
`drush en entity_browser_enhanced`

### Content Entity Browser

The [Content Entity Browser module](https://www.drupal.org/project/content_browser) basically provides a way to displays rows of to see what content is available to select for a view. 

### Entity Embed

The [Entity Embed module](https://www.drupal.org/project/entity_embed) is the way you interface the access to entities into your [CKEditor](https://www.drupal.org/docs/core-modules-and-themes/core-modules/ckeditor-5-module) so you can grab and insert content while WYSIWYG editing.  Besides using Composer and Drush to [install and enable this module, you also need to do some set up to put it in your editor like this.](https://www.youtube.com/watch?v=B3ccBz1LgzQ)

### File Entity Browser

We noted that besides content, user, comment, etc. there is a type of entity that is unique for files.  This [File Entity Browser module](https://www.drupal.org/project/file_browser) is sort of the counter-part to the media or content entity browsers but to see the files available to use. You can [see the basics of its use here.](https://i.imgur.com/MokNcf4.gif)  Make sure you go to the [set up of this module right from the Drupal.Org site](https://www.drupal.org/project/file_browser) as there are a few minor, unique things to use it.

### Entity Embed Links

[Sometimes you might find it valuable to have a link associated with a type of media;](https://www.drupal.org/project/entity_embed_link) perhaps an image thumbnail that the link points to the URL of the full size original.  We might consider the [Linkit module](../modules/linksmodals.md) but more fulling integrated with our entity media management might be to use the Entity Embed Links module.

# Entity Relationship

## Entity Reference
<font color=grey>(automatically in Core)</font>

One of the most powerful concepts in Drupal is an Entity Reference.  Thing of this as helping define things that belong together.  For example, a song might be one-of-many which make up and album and an artist might have more than one albumn.  So you might create a content type for song, then albumn, then article in sort of a hierarchical low to higher logic.  What that is doing is having the lower level item present so that when you create the next higher one the lower is available to point to it.  A [video overview from Drupal.Org shows a simple example with recipes and those who submitted them.](https://www.youtube.com/watch?v=hAhWiqPlKh0&t=142s)

You care a lot about this entity reference stuff and are going to add a bunch of contributed modules that have been developed to make it easier to use.  The general logic of entity reference is better ways to put stuff together rather than re-enter or redundantly maintain stuff.  An example might be something like you wanting to put a staff list in your menu where you have pictures of people, their unique email and phone numbers, but also want to list their business address which is broadly the same for those at the same physical location.  Instead of redundantly putting it in a dozen times, you make a business address entity for each site your business operates, and then when you create an entity with each staff picture and contact information you just 'reference' the business site address entity(ies) you created to plunk them in.  That is an entity reference, one entity referring to another.  

Don't get too hung up on the name of the article or its worry about some pitfalls on how the basic core entity reference can cause some bumps for content editors. But a review of [this article gives a good overview of the logic of being able to not only use entity references but on how to update entities that are involved.](https://www.lullabot.com/articles/dangers-inline-editing-structured-content)  One way you are not going to worry about the update points in that article is that you are going to install and enable the [Entity Reference Revisions module.](#Entity-reference-revisions-module)

### Inline Entity Form module

Think of the [Inline Entity Form module](https://www.drupal.org/project/inline_entity_form) as a shortcut.  In that logic of creating the first or lower level content type first and then referencing it as you create the next up the sequence, you could be going in and out of different Drupal GUI Administrative set up areas.  This module bridges that issue so you can jump from within (inline) and do the creation of what you will reference right in part of the set up.  If your are making a ['block'](../chapters.md#understand-the-many-types-of-BLOCKS-in-drupal) it can be really handy for when you save a content type as a block.  It is worth checking out this video on how you can [create and edit them directly rather than first creating the block you want to embed](https://www.youtube.com/watch?v=PYTb-WwIt40). You can also see a [write up about how this integrates a selection set up to make it easier to do this](https://www.drupal.org/docs/8/modules/entity-browser/inline-entity-form) but Ivan's video makes the benefit more clear if you aren't familiar with the concept.

### Entity Reference Revisions module

Drupal is said to be generally "revisionable".  Meaning sort of what version control does but to an entity within Drupal.  What this module does is provide access to those revisions for entity reference entities.
  
`composer require drupal/entity_reference_revisions`<br>
`drush en entity_reference_revisions`

### Entity Reference Preview module

Another factor around entity reference versions is that the preview is connected to whatever the published looks like, not what you might be currently editing.  What that means is that your edit preview might be the unpublished revision you just worked on but the referenced entity connected to it is the published version.  This Entity Reference Preview module steps up to that issue so you can see a previews of edits on the base entity and on any edits you made 'inline' to the referenced entity. 

`composer require drupal/entity_reference_preview`<br>
`drush en entity_reference_preview`

### Entity Usage module

Alright, you are now so bright you know about entity references and you can even browse entities to find what you might want to reference where.  But, you probably don't remember from last time you worked on the site where all those entity references are and what you have referenced by what.  So you want to install and enable the Entity Usage module.

Entities which are related to one another are set up using some of the approaches provided here.  But the [Entity Usage module](https://www.thedroptimes.com/30817/video-know-more-about-entity-usage-module) is a good one to track what is connected to whatelse so you can manage them as needed.  People tend to like it to track where media from the media manager are used. It will insert an extra tab titled 'Usage' right after the 'View', 'Edit', 'Delete', options.

`composer require drupal/entity_usage`<br>
`drush en entity_usage`

### Rabbit Hole module

This one sounds odd.  But what you need to think about is that almost all the other linking and referencing of entities what we are showing is about expanding access to one part from from another; e.g. a block within a node.  What if you want to limit rather than expand access?  An example might be that you have a slideshow you have developed as a content type but you don't want to let me click on the individual slide images as they come up and get to them; you just want them to see the slideshow itself.  You want the [Rabbit Hole module](https://www.youtube.com/watch?v=EkLS1hlLFnI) to bring this enhanced level of control; if they do click on it and you don't want it to do the normal thing, what do you want it to do?  Do a redirect, send a warning, etc.

# Create One
## Entity Construction Kit (ECK)

Under architecture and entities we noted you could actually make a whole new entity type with [the Entity Construction Kit.](../book/archandentities.md#just-make-one) This module is only going to be of value for some pretty specific needs; but important ones when they arise.  It actually supports you in creating a whole new 'Entity TYPE'.  Not just an additional 'content type' which is a subset of the Node Entity.  A User Entity is another existing entity type.  But what happens is that entity types have bundles associated with them like fields in content type node entities.  You, however, may not want to be at the mercy of Drupal standard entities because of the bundle definitions.  A one to many heirarchy but that has different allowable substructures is an example where two different bundles of your own making is important.  Vehicles might split by cars, trucks, motorcycles, airplanes, tanks, etc. and the same feature fields wouldn't always be common (although some are).  Thus you might want to make your own content type for vehicles but split the bundles by those different vehicle types so that trucks can have beds, airplanes different wing configurations, etc.  The ECK module is the tool for you to do this type of thing.  An old, but still relevant [video gives the basic logic even if the exact GUI might have shifted some with module updates.](http://codekarate.com/daily-dose-of-drupal/drupal-7-entity-construction-kit)

`composer require drupal/eck`<br>
`drush en eck`


<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)


