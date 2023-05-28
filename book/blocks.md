# Blocks

Drupal website pages are made up of different sections called 'Regions'.  Where these Regions come from is your ['Theme'.](../theme/frontoverview.md)  Most people are familiar with websites having a main content area, a header, a footer, one or more sidebars, etc. and these would be Regions.  What you put into these regions are 'Blocks'.  So, for example, you might put a search block in a sidebar region or an extra navigation block in the footer region.  [Blocks and Regions are intimately tied in Drupal.](https://www.drupal.org/docs/user_guide/en/block-concept.html)

[Managing Blocks in Regions will be a significant part of what you do with Drupal](https://www.drupal.org/docs/core-modules-and-themes/core-modules/block-module/managing-blocks) regardless of how you work toward builing your website.  The Layout Builder approach is yet an additional step to make it easier for site builders to take advantage of Drupal's extraordinary capabilities while staying away from code level work.  Yet, for developers they can do all sorts of thing using code to streamline building or populating blocks in a website.

Even novice users are likely to want to make [Custom Blocks](https://youtu.be/sI2wrbn3cPg) that serve their purpose; an example might be the hours and location of your business.  The interesting thing about Blocks is that most are reusable and thus you may put them into different locations on your website as you find appropriate. 

## Blocks and Layout Builder

[Layout Builder](../modules/layoutbuilder.md) is a tool in Drupal for site builders to use a somewhat drag and drop functionality as they work on their website.  This tool uses Blocks to place in Regions and Section of webpages as one builds.  The reusablity of Blocks for Layout Builder users has been dramatically improved with a [Section Library module](https://www.drupal.org/project/section_library) which is [explained in some detail in this video](https://www.youtube.com/watch?v=E68DxSLcCd0)

## Block Visibility Groups module
#### Enhancement to control and placement of blocks

You can put the [Block Visiblity Group module](https://www.drupal.org/project/block_visibility_groups) in the "greater than sliced bread" category!  Think of website building as putting chucks of things in different areas for display.  You probably already know this relative to 'Regions' that your theme includes.  People who have used an older approach called Panels also know about moving chucks of stuff in different parts of a region.  Drupal from version 8 forward rallys around the use of Blocks for the term of what these chucks are called; and if you use the GUI drag-n-drop Layout Builder function included in Drupal Core you also know how moving the blocks around is pretty cool.  You also may know about how in the 'Administration/Structure' menu in your Drupal site building system you can look at a Blocks Layout Page you can see on what content type and region blocks appear.  But sometimes you want those blocks to show up conditionally; say for a logged in user versus a stop-by.  See this [quick video on how the Block Visibility Group module adds conditional control in a very simple, comfortable way.](https://www.youtube.com/watch?v=ZKwkaMUbJIs)

`composer require drupal/block_visibility_groups`<br>
`drush en block_visibility_groups`

## Block and TWIG

[Drupal Blocks Relationship to TWIG Templates (Video)](https://www.youtube.com/watch?v=Q-Pp0mw0Wm4)

[Understanding the many types of Blocks in Drupal](https://git.drupalcode.org/project/twig_tweak/-/blob/3.x/docs/blocks.md)


## Details

[Selwyn Polit's extensive coverage of Blocks](https://selwynpolit.github.io/d9book/blocks.html)

<br>
<br>
<br>

[Learn more... Drupal Basics](../chapters.md#drupal-basics)
