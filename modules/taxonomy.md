
# MODULES INVOLVING TAXONOMY
### Basic unstructured 'Tagging' and Simple Taxonomy are in Core.

Content of any depth needs a way to be presented to users filtered conveniently to their interests.  Thus content can be marked or 'tagged' with terms which can then act as filters to find and view what the users wants.  Drupal, out of the box, supports 'Tags' as a sort of "free form" classification of terms you can associate with content.

More often you will want to create a structured taxonomy to associate with content to aid in finding the precise interests of the user.  For that were leverage a number of Taxonomy modules.  The Taxonomy module itself is an out of the box Core capability, just make sure it is enabled.

Just like the biological application of the classification concept of taxonomy, Drupal allows you to have levels or a hierarchy.  But if you were to try to do the domain, kingdom, phylum, class, order, family, genus, and species level of depth it is pretty complex for a user to work with.  Often, it is better to use several taxonomies.  An example might be to use Resturant Cuisine, Resturant Style, Resturant Meal Occassions, Dietary Accomodations, and Resturant Features rather than trying to fold all that into some sort of complex hierarchical uni-taxonomy.

## Taxonomy Manager
To help with those hiearchical levels you do want to use.

`composer require drupal/taxonomy_manager`<br>
`drush en taxonomy_manager`


## Term CSV Export/Import Module
Often you will have some source file with a list of classification terms you can use as a taxonomy.  Or, you might find it easiest to organize taxonomy terms by looking at them in a spreadsheet; which you can then export as a CSV file.  Importing Taxonomy terms from a CSV file or backup is done with this module.

Watch where this module stand in terms of development to see if it meets your minimum stability requirements.   Also, make sure you are aware that the previously noted taxonomy_manage module already has some level of file import capability.

`composer require drupal/term_csv_export_import`<br>
`drush en term_csv_export_import`


## Getting Them 'In' 
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




You can also leverage the powerful 'permissions by term' module to tightly control what entities are seem by specific users; content entities and even menu entities:
composer require 'drupal/permissions_by_term:^3.1'
https://www.youtube.com/watch?v=dYNcfa0ALj0






Permissions by Term module (Controlling the 'Who' can do what with your taxonomy terms): 
composer require drupal/permissions_by_term
drush en permissions_by_term

Facets module (Giving the User the power to leverage taxonomies beyond a search box): 
composer require drupal/facets
drush en facets

Core Views Facets module (If you want to use Facets within Views):
composer require drupal/core_views_facets
drush en core_views_facets

Facet Block module (multiple search facets combination blocks; e.g. multiple taxonomies filter):
 composer require drupal/facets_block
drush en facets_block

Taxonomy Menu module (display taxonomy terms to a site visitor is through menus):
composer require drupal/taxonomy_menu
drush en taxonomy_menu




[Drupal.Org does a detailed job of showing how to set up a taxonomy](https://www.drupal.org/docs/user_guide/en/structure-taxonomy-setup.html)
