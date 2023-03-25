
# Taxonomy
Content of any depth needs a way to be presented to users filtered convenient to their interests.  Thus content can be marked or 'tagged' with terms which can then act as filters to find and view what the users wants.  Drupal out of the box supports 'Tags' as a sort of free form classification of terms you can associate with other content.  But more often you will want to create a structured taxonomy (frequently more than one category of terms) to associate with content to aid in finding the precise interests of the user.  For that were leverage a number of Taxonomy modules.  Taxonomy itself is an out of the box Core capability, just make sure it is enabled.  

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






[Drupal.Org does a detailed job of showing how to set up a taxonomy](https://www.drupal.org/docs/user_guide/en/structure-taxonomy-setup.html)
