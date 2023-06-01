
# Views

One of the most powerful things Drupal, and probably why you selected a content management system (CMS) approach to your site, is the availability of VIEWS into your information.  Think about creating content.  You selected or created a content type, you managed the fields within it, and you populated the content (e.g. think multiple articles).  You logically aren't going to create a menu link to each individual article once the count is over say half a dozen.  You aren't going to string a stacked sequence of every article you create on top of each other on a single page or node.  Rather, you probably want to give your user a summary of article titles, maybe a short trimmed amount of its content, and maybe the date on a list, some cards, some blocks around a front or section page, etc.  Then you want to create those with a View.

## Views & Views UI modules

The Views and Views UI modules are part of Drupal Core.  You may want to confirm they are enabled under Admin/extend to see that they are check-marked.  With that you are ready to use this basic views capability.   [WebWash provides a nice video training overview to get you started](https://www.webwash.net/getting-started-with-views-in-drupal/)

### Combining Filters

There is so much power in Views it is hard to communicate it all.  One often overlooked is an option under the 'Filter Criteria' for a Global filters: Combine Fields.   Without sending one down a whole additional computer language, it might help to understand that Views is basically making an [SQL](https://en.wikipedia.org/wiki/SQL) query into the database to pull the specific information filtered to exactly what you are seeking to display. You can even [configure Drupal to show the actual SQL Query syntax of your View.](https://www.drupal.org/docs/8/core/modules/views/configure-views-for-debugging)  An [example of how you might set up a Search View across multiple fields may help; and you even get to see the SQL Query is set up as 'AND' combinations in how this one was set up.](https://www.webwash.net/search-across-fields-in-views-using-combine-fields-filter-in-drupal-8/)

### Views of Forms

The crazy thing about Drupal is that it is built upon itself.  What this means is that when a User signs up to your website, the little form they fill out is actually built by a View.  Since that little form is a [User Entity type](../book/archandentities.md) you can add more to the sign up form that comes out of the box.  It would be common to add asking for some information about your airplane model on an aviation site, or what ratings you have, or how many hours.  But simply [adding fields to an entity](../modules/fields.md) is not where it stops.  Heck, you can add a whole new tab on the form.  An example might be [a tab for the articles that a user has contributed to the website.](https://www.webwash.net/custom-tab-user-profile-page-views-drupal-8/)  But basically, you can add a custom tab for a variety of purposes.  Infact, if you can define a query of something that is part of your website, you can use Views to present the results in a ton of different ways.

### No result

If the above example, it would be logical that a new user would not have any articles they contributed yet.  In fact, in any number of the Views queries that take place, there is a reasonable likelihood that in some situations nothing will meet the criteria.  So the results are null, empty, nothing, and yet you have some sort of 'home' you have set aside for those result to appear.  You don't want an empty home to show up. [What do you do with a no result return in Views?](https://www.webwash.net/hide-block-if-no-results-are-returned-using-views-in-drupal/)

### View a Field as a Block

Views in core can do a ton of things.  That includes taking a Field from your content entity and pulling it out of the body of the node it is part of and [displaying it as a Block that you can place in a Region.](https://www.youtube.com/watch?v=B0XBQ2Ra5dk&t=0s) As that video shows, Views can handle this task and leverage all sorts of configuration settings for a View in doing so.  But sometimes you want just the KISS approach to allow you to set a field as a block right from your traditional 'Manage Display' settings tab for the content type.

## Views modules

### Fieldblock module

There is a popular contributed module that does [allow you to set a field as a block from the 'Manage Display' settings tab.](https://www.youtube.com/watch?v=Q-F0ZFcfYps) 

`composer require drupal/fieldblock`<br>
`drush en fieldblock`

### Views Block Expose Filter Blocks module

One of the things you see toward the end of that video is how you can create a 'block' view from a copy of the 'page' view and then set the block view as independent so you can edit it down to something more unique and narrow in scope.  You also saw that you can set up filters that a user can control rather than just how you might have done a filter down to the subset of what underlying content is viewed.  By putting that filter in the users hands they can focus where they want.  But you might want to use that filter on a block and place it physically in a separate block visually; this module gives you that power. 

`composer require drupal/views_block_filter_block`<br>
`drush en views_block_filter_block`

### Views Flipped Table module

Views offers options on the way it displays the query results. Things like an unformatted list, grid, table, etc.  This module simply flips the rows and columns from a standard table to display the other way around in case you happen to have more columns than rows in what you are pulling. 

`composer require drupal/views_flipped_table`<br>
`drush en views_flipped_table`

### Views Slideshow module

The [Views Slideshow module](https://www.drupal.org/project/views_slideshow) is more than an image slideshow.  You can slideshow any item; like the last X articles, the latest forum posts, the newest products, etc.  [Go to the Drupal.org site for the installation of this module](https://www.drupal.org/project/views_slideshow) as it requires some JavaScrip libraries be installed above and beyond your traditional composer install...

### Views Infinite Scroll module

A typical deployment of views has a pager that you can configure for how many pages, style of paging, etc.  The [Views Infinite Scroll module](https://www.drupal.org/project/views_infinite_scroll) adds one more option to that which adds content as you scroll down rather than clicking to a new page.  [See how to install it and even customize the scroll behavior.](https://www.webwash.net/create-infinite-scroll-pages-using-views-infinite-scroll-in-drupal/)

`composer require drupal/views_infinite_scroll`<br>
`drush en views_infinite_scroll`

### Views Layout module 

The [Views Layout module](https://www.drupal.org/project/views_layout)is sort of like a stripped down Layout Builder that lets you select different column counts in stacked rows to display Views output in a little more creative way than just grids or tables.  It can be used with the Layout Plugin Views module if you want to go incrementally a little more nuts on field level presentation in the rows you are stacking.

`composer require drupal/views_layout`<br>
`drush en views_layout`


### Core Views Facets module

If you want to use [Facets](../modules/facetedsearch.md) within Views, also install and enable this add-on.

`composer require drupal/core_views_facets`<br>
`drush en core_views_facets`



<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)


