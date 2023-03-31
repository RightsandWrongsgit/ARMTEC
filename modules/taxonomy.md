
# USING TAXONOMY
### Basic unstructured 'Tagging' and Simple Taxonomy are in Core.

Content of any depth needs a way to be presented to users filtered conveniently to their interests.  Thus content can be marked or 'tagged' with terms which can then act as filters to find and view what the users wants.  Drupal, out of the box, supports 'Tags' as a sort of "free form" classification of terms you can associate with content.

More often you will want to create a structured taxonomy to associate with content to aid in finding the precise interests of the user.  For that were leverage a number of Taxonomy modules.  The Taxonomy module itself is an out of the box Core capability, just make sure it is enabled. [Drupal.Org does a detailed job of showing how to set up a taxonomy](https://www.drupal.org/docs/user_guide/en/structure-taxonomy-setup.html).

Just like the biological application of the classification concept of taxonomy, Drupal allows you to have levels or a hierarchy.  But if you were to try to do the domain, kingdom, phylum, class, order, family, genus, and species level of depth it is pretty complex for a user to work with.  Often, it is better to use several taxonomies.  An example might be to use Resturant Cuisine, Resturant Style, Resturant Meal Occassions, Dietary Accomodations, and Resturant Features rather than trying to fold all that into some sort of complex hierarchical uni-taxonomy.

## Taxonomy Manager
To help with those hiearchical levels you do want to use.

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

<font color=yellow>You will note the video is for an old D7 version but the logic is the same for the current version.  Note you may need to allow 'beta' level modules in your composer.json to install to use the current version.</font>


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
`drush en entity_reference_tree`

# User Presentation 

## Facets module
To give the user the power to leverage taxonomies beyond a search box you might want to use facets.  Thing of these as the boxes you see on the left of the large shopping sites where you chose your size, color, price, etc. preferences.

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
To display taxonomy terms to a site visitor is through menus, try this module.

`composer require drupal/taxonomy_menu`<br>
`drush en taxonomy_menu`


# Taxonomy w/ Other Modules

[Taxonomy works in valuable ways](https://www.youtube.com/watch?v=5A3y0N_1Ufk) with the [Token Module](../modules/development.md#token-module).

## Permissions by Term module
You can also leverage the powerful [Permissions by Term](https://www.youtube.com/watch?v=dYNcfa0ALj0) module to tightly control what entities are seen by specific users; content entities and even menu entities:

`composer require drupal/permissions_by_term`<br>
`drush en permissions_by_term`

