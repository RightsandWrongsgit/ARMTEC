
# Taxonomy
Content of any depth needs a way to be presented to users filtered conveniently to their interests.  Thus content can be marked or 'tagged' with terms which can then act as filters to find and view what the users wants.  Drupal, out of the box, supports 'Tags' as a sort of "free form" classification of terms you can associate with content.

More often you will want to create a structured taxonomy to associate with content to aid in finding the precise interests of the user.  For that were leverage a number of Taxonomy modules.  The Taxonomy module itself is an out of the box Core capability, just make sure it is enabled.



Taxonomy Manager will help you deal with hierarchical levels.
composer require 'drupal/taxonomy_manager:^2.0'

Importing Taxonomy terms from a CSV file or backup is done with this module but watch that it is only Alpha so you may need to adjust your composer rules to install it. 
composer require 'drupal/term_csv_export_import:^3.0@alpha'


Working with the presentation of the taxonomies is added with widgets that can be installed and give you control of relationships in things like views.  These two are candidates so test if the first one is actually better than the second (which is what testing to this point has been done on).
composer require 'drupal/term_reference_tree:^1.0'

composer require 'drupal/entity_reference_tree:^2.0'


You can also leverage the powerful 'permissions by term' module to tightly control what entities are seem by specific users; content entities and even menu entities:
composer require 'drupal/permissions_by_term:^3.1'
https://www.youtube.com/watch?v=dYNcfa0ALj0


- MODULES INVOLVING TAXONOMY & ITS USE -
(Basic unstructured 'Tagging' and Simple Taxonomy are in Core.)



Taxonomy Manager module (will help you deal with hierarchical levels):
composer require drupal/taxonomy_manager
drush en taxonomy_manager

Import Taxonomy terms module (from a CSV file or backup is done with this module):
Watch where it is in terms of development to see if it meets your minimum stability requirements.   Also, make sure you are aware that the taxonomy_manage module above already has some level of file import capability.
composer require drupal/term_csv_export_import
drush en term_csv_export_import

Easier selection of taxonomies and terms Widgets modules (CHOOSE ONE):
Working with the presentation of the taxonomies to give you control of relationships in things like views.  
composer require drupal/term_reference_tree
drush en term_reference_tree
OR
The entity reference tree widget module supports the standard 'composer install approach', while taking care of setting up some of the underlying jS capabilities that other modules require you to go in and do manually; so this is a simpler approach.
composer require drupal/entity_reference_tree
drush en entity_reference_tree


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
