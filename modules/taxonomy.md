
# Using Taxonomy
### Basic unstructured 'Tagging' and Simple Taxonomy are in Core.

Content of any depth needs a way to be presented to users filtered conveniently to their interests.  Thus content can be marked or 'tagged' with terms which can then act as filters to find and view what the users wants.  Drupal, out of the box, supports 'Tags' as a sort of "free form" classification of terms you can associate with content.

More often you will want to create a structured taxonomy to associate with content to aid in finding the precise interests of the user.  For that were leverage a number of Taxonomy modules.  The Taxonomy module itself is an out of the box Core capability, just make sure it is enabled. [Drupal.Org does a detailed job of showing how to set up a taxonomy](https://www.drupal.org/docs/user_guide/en/structure-taxonomy-setup.html).

Just like the biological application of the classification concept of taxonomy, Drupal allows you to have levels or a hierarchy.  But if you were to try to do the domain, kingdom, phylum, class, order, family, genus, and species level of depth it is pretty complex for a user to work with.  Often, it is better to use several taxonomies.  An example might be to use Resturant Cuisine, Resturant Style, Resturant Meal Occassions, Dietary Accomodations, and Resturant Features rather than trying to fold all that into some sort of complex hierarchical uni-taxonomy.

## Taxonomy Manager
To help with those hiearchical levels you do want to use.  [The Taxonomy Term module is good to copy and paste extensive taxonomy terms from source files, and for searching and editing terms while displaying the whole tree.](https://www.webwash.net/manage-terms-bulk-using-taxonomy-manager-in-drupal/)  You do need to still use the core taxonomy option to move and reorder terms via its dragg and drop interface.

`composer require drupal/taxonomy_manager`<br>
`drush en taxonomy_manager`


## Term CSV Export/Import module
Often you will have some source file with a list of classification terms you can use as a taxonomy.  Or, you might find it easiest to organize taxonomy terms by looking at them in a spreadsheet; which you can then export as a CSV file.  Importing Taxonomy terms from a CSV file or backup is done with this module.

Watch where this module stand in terms of development to see if it meets your minimum stability requirements.   Also, make sure you are aware that the previously noted taxonomy_manage module already has some level of file import capability.

`composer require drupal/term_csv_export_import`<br>
`drush en term_csv_export_import`

## Feeds Tamper module

Install this enhancing module for more control of the files.  It is a companion of the Feeds module as a way that files can be pulled into you site to populate content. What this 'tamper' does with that is give you lots of control over flows, parsing, etc.  Given it has a dependency on the Feeds module, that module will install automatically with it. 

`composer require drupal/feeds_tamper`<br>
`drush en feeds_tamper`

The easiest way to relate to the feeds module is to watch the demo video they provide a [link to on the Drupal.org page for the module](https://www.youtube.com/watch?v=DBsg6cVbmf8)

<font color=yellow>You will note the video is for an old D7 version but the logic is the same for the current version.  Note you may need to allow 'beta' level modules in your composer.json to install to use the current version.</font><br>
<br>
<br>
<br>
# Getting Them 'In' 
### Easier selection of taxonomies and terms Widgets
#### (CHOOSE ONE)
You know in Drupal how you set up the fields in content, a form for input, and a display for how it should look.  Those tabs you go to in order to do this are widgets.  If you start getting into more complex taxonomies, some special widgets can be added with these two contributed modules.  Working with the presentation of the taxonomies is added with these widgets. They give you control of relationships between things like views.  Here are two candidates.  Test if the first one is actually better than the second for your purposes.

## Term Reference Tree 

`composer require drupal/term_reference_tree`<br>
`drush en term_reference_tree`

OR<br>

## Entity Reference Tree

`composer require drupal/entity_reference_tree`<br>
`drush en entity_reference_tree`<br>
<br>

# User Presentation 
<br>

## Client-Side Hierarchical Select
One of the best ways to present a filtered list of content is using [Views.](../modules/views.md)  Views itself offers an ability to filter but adding the [Client-Side Hierarchical Select module](https://www.drupal.org/project/cshs) makes the use of taxonomy terms as filters, especially where there is some <font color=yellow>depth</font> to the taxonomy, a great combination.  For an overview of how to set this up, [watch this.](https://www.youtube.com/watch?v=jq7p98wXWkA)

## Facets module
To give the user the power to leverage taxonomies beyond a search box you might want to use facets.  Thing of these as the boxes you see on the left of the large shopping sites where you chose your size, color, price, etc. preferences. [Instructions on setting this module up.](https://www.specbee.com/blogs/how-configure-faceted-search-drupal-8-and-9-easy-step-step-tutorial)

`composer require drupal/facets`<br>
`drush en facets`

## Core Views Facets module
If you want to use Facets within Views, add this module.

`composer require drupal/core_views_facets`<br>
`drush en core_views_facets`

## Facet Block module
If you need multiple search facet combination blocks, try this module.

`composer require drupal/facets_block`<br>
`drush en facets_block`

## Taxonomy Menu module
Another way to display taxonomy terms to a site visitor is through menus.  Now that might not seem logical if your head is wrapped around the Main Menu that you have on your site.  But don't forget that Drupal has multiple menus that are in different regions of your page; e.g. say in the footer or for user log-in in the upper right corner. Plus, you can make and place menus in other regions where it works for your design.  This module is used to grab taxonomy terms and make them menu items you can than arrange for your purposes. 

`composer require drupal/taxonomy_menu`<br>
`drush en taxonomy_menu`

## Private Taxonomy Terms module
If you have paid, logged in users with a higher priority permissions, there may be occasions that you want to grant them the rights to associate a personalized taxonomy with site content.  For example, you run a classic car site with sections with articles, manuals, parts for sale, etc.  Your public taxonomy might get you to make and model classifications but a user enthusiast may want to further categorize content items for their specific engine type, door configuration, etc.  In such a case, you might want them to be able to have their own taxonomy but not gum up the public taxonomy which may already be extensive, complex, multi-level.  Grant them this right using the private taxonomy terms module.

`composer require drupal/private_taxonomy`<br>
`drush en private_taxonomy`

## Tagify module

The agify module](https://www.drupal.org/project/tagify)is basically a JS interface that improves the user experience in tagging terms. Commonly used with entity reference deployments, the ability to quick select and edit what terms you want to associate with what is being tagged is a user friendly addition.

<br>

# Taxonomy w/ Other Modules

[Taxonomy works in valuable ways](https://www.youtube.com/watch?v=5A3y0N_1Ufk) with the [Token Module](../modules/development.md#token-module).

## Permissions by Term module
You can also leverage the powerful [Permissions by Term](https://www.youtube.com/watch?v=dYNcfa0ALj0) module to tightly control what entities are seen by specific users; content entities and even menu entities:

`composer require drupal/permissions_by_term`<br>
`drush en permissions_by_term`

## Hierarchy Select module

If you are dealing with a large taxonomy it is likely it has some sort of hierarchical depth to it.  A list of every country in the world perhaps first presented by its continent or hemisphere might be an example.  You might want to leverage on of these hierarchy select modules to work with such a taxonomy.  

The [Client-Side Hierarchy Select module](https://www.drupal.org/project/cshs) is used to provide a field widget for selecting taxonomy terms in a hierarchical fashion.  By preloading a taxonomy's hierarchy the client browser it provides select boxes to allow a user to pick options one by one with a parent-child-grandchild sequence set by the depth you select.  Very good for complex hierarchies with many levels.  [Nice Example Video!](https://www.youtube.com/watch?v=jq7p98wXWkA)

There is another [module called Simple Hierarchy Select](https://www.drupal.org/project/shs) with similar intent.  While dated in version, its principles are the same as in this [video on Simple Hierarchy Select](https://www.webwash.net/using-simple-hierarchical-select-module-in-drupal-7/)

## Webform taxonomy

The [Webform series of modules](../modules/forms.md#webform-module-series) moves past the classic PHP forms serving content set up and display within Drupal to a role much more specific to form generation.  As such it uses elements which are parallel in concept to Drupal fields yet separate.    The discussion under the [Forms modules](../modules/forms.md) explains all that much further.  But one thing to be aware of is that there are some opportunities to [coordinate your taxonomy with Webforms.](https://www.webwash.net/taxonomy-terms-as-webform-options-in-drupal/)

# Going Native
In addition to leveraging contributed modules that help with taxonomy, there are opportunities to work more directly with taxonomy related code. [Selwyn Polit](https://www.drupal.org/u/selwynpolit) has a chapter in his github pages book on [Taxonomy](https://selwynpolit.github.io/d9book/taxonomy) working at this more native level.

<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)

