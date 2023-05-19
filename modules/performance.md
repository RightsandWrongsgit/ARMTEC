
# Performance modules

## Purge module

The [Purge module](https://www.drupal.org/project/purge) is a cache management alternative.  It allows you to set up certain cache components to retain 'infinitely' those items that have not had a change.  This improves performance by not having to load stuff that was already fine just like it was. 

`composer require drupal/purge`<br>
`drush en purge`


## Quicklink module

[Quicklink](https://www.drupal.org/project/quicklink) uses Google's JavaScript Quicklink library to enable faster subsequent page-loads by prefetching in-viewport links while your input otherwise may be idle. It is [claimed to improve load times by 50% via a sort of "look ahead" JavaScript effort.](https://fivejars.com/blog/quicklink-tool-boosts-website-conversions-50)

`composer require drupal/quicklink`<br>
`drush en quicklink`

## Advanced CSS/JS Aggregation module 

If you are using the set up established by the Drupal CICD Base Project you don't need this module because we handle doing this directly at the php level as [noted it that project's documentation](../cicd/envsettings.md#More stuff to put in my-example.settings.local.php).  Also, keep in mind that you have the basic control capabilities as part of Core under your Administration options.  But if you really want to leverage all of it and aren't comfortable working at the php file level, the [Advanced CSS/JS Aggregation module](https://www.drupal.org/project/advagg) can give you GUI access to jump your frontend performance.

`composer require drupal/advagg`<br>
`drush en advagg`







Search:
Drupal already has basic search built in.  However, if you have substantial content you will improve performance via enhancing modules.  

Search API module:
This is a good basic interface enhancement module to support initial basic search yet be ready to move to Apache Solr search integration.  You will need to do some experimentation in terms of setting it up with the facets module in the more current versions of Drupal.  



The set up process is relatively complex because of the range of options for what can be indexed.  This video walks you through the process and it also shows about 25 minutes into it how to switch the indexing server to Solr (requiring the Solr Search module to be installed and enabled).  https://events.drupal.org/barcelona2015/sessions/building-amazing-searches-search-api


The main watch out you hear in the video is to remember to manage the access options so you aren't exposing unpublished or other unintended information from your site via people finding it in the search.  Beyond the video, effort must be done around the approach to setting up a solr server in your hosted site container via your DevOp procedures; this is NOT discuss here but should be investigated with your host's documentation.

https://www.drupal.org/project/search_api

https://www.drupal.org/project/search_api_solr



<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)

