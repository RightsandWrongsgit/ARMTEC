
# Faceted Search

Two parts, Search and Facets.  Search if just what it says, finding stuff.  But how to tell the system what you want to find might be just typing a word(s) into an input box and hitting a submit button.  Facets are most easily understood as those little checkboxes on the left side of the shopping options on something like the [Amazon shopping site.](https://amazon.com)  If you thing about it, they can be used together since you probably told Amazon the category of things you are wanting to buy but the facets are then presented for the size, color, or other option choices in further narrowing down the results card grid that is presented.

## Basics Video

[Ivan Zugec of WebWash does the simplest 'Search' within the standard Drupal database and then shows putting Facets on them at the end.](https://www.youtube.com/watch?v=dj4gtbc4LyY) He does admit at the end that using the Search API rather than the basic standard search in core Drupal is much, much stronger but also much more challenging to set up.  So consider using the basic search for reasonably basic sites without huge content volumes that need speed and sophisticated combination queries.  


**********
## Solr Search

### Overview

Mike from Acro Media does a good job of [setting up a Solr Search in Drupal and then putting in Facets for using them as filters.](https://www.youtube.com/watch?v=PeaiWXy6ZsY)  The limits on this video are:<br>
a) He does NOT show his creation of a Solr Core because he did it in advance; so look at Lando Solr and Platform.sh Solr container set ups and make sure to create a uniquely 'named' core in the process. (His pre-established 'core' is called Products in his video but you want yours to be something unique to your project intent unless you are doing commerce as well.)<br>  
b) He sets the search up under a Product from the the Ecommerce module he has installed and you may want to search on something different like Content or Taxonomy Term (if you watch closely you will see where he makes this selection about the 5.0 minute mark of the video).<br>  
c) Unless you start snapshot screen captures as the video plays, it may go by too fast so the next section that has screens shots may be better references as you work. 

### Cookbook

If you find you want to move to the [Search API level of Facet deployment you might follow this.](https://www.specbee.com/blogs/how-configure-faceted-search-drupal-8-and-9-easy-step-step-tutorial)

Installing the Facets Module for Drupal.  As previously discussed, we will be implementing Faceted search using Drupal’s Search API module.

#### Install the Facets and Search API modules

- Prerequisite:

`composer require drupal/facets`<br>
`composer require drupal/search_api`

- Step 1: Enabling the modules
Install and enable these modules      

`drush en facets`<br>
`drush en search_api`

- Step 2: Creating Content Types

[Create the content you would like to include in the faceted search.](https://www.drupal.org/docs/user_guide/en/structure-content-type.html)  You can also use the default content types provided by Drupal.

- Step 3: Configuring the Search server

Navigate to Configuration -> Search and metadata -> Search-API from the admin interface to configure your search server. Give a name to your search server. 
 
- Step 4: Configuring the Search Index

Next, configure the search index to improve the search performance. Navigate to Configuration -> Search and metadata -> Search-API -> Index -> data_index.

Give a name to your index and then select Content as your Datasources since we will be indexing the Content entities here.  You can then move on to the next section - Configuring the Datasource (here – Content).  Here you can choose to select all the bundles or only select a few from the below list to index.  Next, select your server that you had already created (here - data server).  Select the “Index items immediately” option to begin the indexing process. Click on Save.

- Step 5: Adding Fields for Indexing

Next, we need to add Fields to be indexed. Navigate to Configuration -> Search and metadata ->Search API -> data index and select the Fields tab. Click on the Add fields button to create fields according to your requirement.

- Step 6: Indexing the Content

Under the same location, click on the View tab to start the process of indexing your content. In the Start Indexing Now section, click on the Index Now button. It will then show you a progress bar with the status of the number of items that have been indexed.
 
- Step 7: Creating a View

Now we will be creating a view for the data that needs to be indexed and displayed to your users. Navigate to Structure -> Views -> Add View.

Give a name for the View.  Under View Settings dropdown list, select the index that you have created in Step 4.  Create a page for your search results by clicking on the Create a page checkbox under the Page Settings tab. Give a name and a path for the same.  Under Items to Display, select 0 if you want to display all the results in one page. Else, select a number of results to be displayed.  Under Page Display settings, you can select the format in which you want to display your results – Table, Grid, HTML list or Unformatted list. We have selected Unformatted list here. Click on Save.

- Step 8: Adding Fields to the View

Here we will be adding fields that we have indexed earlier to the View. Go to Views, click on Add button next to the Fields section. Select the Fields, click on Add and Configure.  Under Render Settings, select the Link to Content checkbox so that the results displayed are clickable.  Click Save.


- Step 9: Configuring the Facets

Now let’s begin configuring and enabling the facets. Navigate to Configuration -> Search and meta data -> Facets  Click on the Add Facet button.
 
Select the Facet Source; This will be your View that you created previously.  Select the Field; This will display the fields you had added for indexing in Step 5. Give a name to the Facet.  Click on Save.

Next, you will then see more configuration options for displaying the facets. Widgets will list out a number of options like List of links, array, dropdown, etc. You can choose what suits your website the best.  Select the “Transform entity ID to label” to avoid displaying the machine name of the content type.  Click on Save.

- Step 10: Placing the Facet blocks in the chosen page regions
 
Next, place the Facets you created as blocks in a page region of your choice.  Navigate to Structure -> Block Layout. Select the region of the page where you would like to place the block containing the Facets.  Here, we are selecting Sidebar. Click on the Place Block button next to the Sidebar.  In the next dialog box, search for the Facet name and click on Place Block.
 
Placing the Facet blocks in the chosen page regions  Step 10: Placing the Facet blocks in the chosen page regions 
In the Configure Block section, mention the Search page path that you had previously created. Here -“site-search” is our page we had created.  Give a display name for your Block and select the Display title checkbox if you want the block name to be displayed (here – Type). Click on Save Block.

- The Result
And just like that, your faceted search page and functionality is ready! Notice the Facet called Type (display name) that has Basic page and Article listed as content types to filter against.

 
[See what this is](https://www.youtube.com/watch?v=nmUgBTy2hls)

This is a very, very slow video overview of the steps.  Start about 3.5 minutes into it.  The key summary points are noted here:

**********


# Facets Modules

Using Composer, install the Facets module.  Then under extend, activate the module.  You also need to install the Search API with Composer and activate it under extend as shown below.

## Facets module

Giving the User the power to leverage taxonomies beyond a search box.

`composer require drupal/facets`<br>
`drush en facets`

## Facets within Views

`composer require drupal/core_views_facets`<br>
`drush en core_views_facets`

## Facet Block Module

The facet block module is an add-on to facets that places multiple search facets into a combination block you can then place; for example multiple taxonomies used in a combo filter. 
 
`composer require drupal/facets_block`<br>
`drush en facets_block`



<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)

