


Set up Mapping Tools:

A separate document has been created to show how each of these modules are configured and integrated with an API to provide multiple paid and fee mapping sources to provide maps in your application; this includes a video link to a very good but slow paced presentation of an application being built as each module is turned on to demonstrate its specific contribution to the total.  A key is the inclusion of the "Address module" noted in the field's section which is turned into a latitude and longitude for proximity coordination of your adjacent entities if you aim to 'route' or feature multiple entities in geographic proximity.

NOTE: Load and enable these in this order because of cross dependencies.
composer require 'drupal/geocoder:^3.20'

composer require 'drupal/geofield:^1.22'

composer require 'drupal/leaflet:^2.1'

composer require 'drupal/leaflet_more_maps:^2.1'

lando drush en geocoder

lando drush en geocoder_address

lando drush en leaflet

lando drush en geocoder_geofield

lando drush en leaflet_markercluster

lando drush en leaflet_more_maps 

lando drush en leaflet_views


NOTE: When configuring the mapping set up, you will be establishing API calls to various mapping providers (discussed more in the Mapping documentation).  Your composer.json file will then be populated with something like:
"geocoder-php/arcgis-online-provider": "^4.1",
"geocoder-php/bing-maps-provider": "^4.1",
"geocoder-php/google-maps-provider": "^4.5",
"geocoder-php/mapbox-provider": "^1.1",
"geocoder-php/open-cage-provider": "^4.4",
"geocoder-php/yandex-provider": "^4.3",



In addition to using the geographic capability above to tie airport associated entities through their address to proximate their availability to pilots, we want to tap the log-in location of the user to leverage that.  The base tool for that is the 'SmartIP Module'. But anticipate substantial additional set up beyond just the install as described on the Drupal.org site for this contrib module.

composer require 'drupal/smart_ip:^4.1'

One of the most basic things we want to use the current location is to set the initially displayed METAR weather for its module:
composer require 'drupal/weather-weather:^1.0'

Need to check for a Drupal 9 version, but it may also be possible to anchor the maps design to the user location starting point.
https://www.drupal.org/project/ip_geoloc

It can also be combined with the smart content module so I can provide a localized content experience to users; perhaps their local airport or airports within their specific region.  This would be for anonymous users and then enhanced with the menu token approach (see menu section) for logged in user personalization.  The smart content module works directly with layout builder integration where smart blocks are Decision Blocks.  This module can also be used for things like A/B testing of content as we move forward.
composer require 'drupal/smart_content:^3.0'


Set up Mapping:
Address Map Link Module:
A basic approach to having a map on your site is the Address Map Link Module in combination with the Address Module discussed earlier.  For most basic sites that want to simply put an address on a page(s) that a user can click to take them to a map, this relatively simple module should do the trick.  If you have a more complex mapping need look further under Multiple Mapping Modules.

composer require drupal/address_map_link
drush en address_map_link












Multiple Mapping Modules:
A separate document has been created to show how each of these modules are configured and integrated with an API to provide multiple paid and fee mapping sources to provide maps in your application; this includes a video link to a very good but slow paced presentation of an application being built as each module is turned on to demonstrate its specific contribution to the total.  A key is the inclusion of the "Address module" noted earlier which is turned into a latitude and longitude for proximity coordination of your adjacent entities if you aim to 'route' or feature multiple entities in geographic proximity.

NOTE: Load and enable these in this order because of cross dependencies.
composer require 'drupal/geocoder:^3.20'
composer require 'drupal/geofield:^1.22'
composer require 'drupal/leaflet:^2.1'
composer require 'drupal/leaflet_more_maps:^2.1'

drush en geocoder
drush en geocoder_address
drush en leaflet
drush en geocoder_geofield
drush en leaflet_markercluster
drush en leaflet_more_maps 
drush en leaflet_views

NOTE: When configuring the mapping set up, you will be establishing API calls to various mapping providers (discussed more in the Mapping documentation).  Your composer.json file will then be populated with something like:
"geocoder-php/arcgis-online-provider": "^4.1",
"geocoder-php/bing-maps-provider": "^4.1",
"geocoder-php/google-maps-provider": "^4.5",
"geocoder-php/mapbox-provider": "^1.1",
"geocoder-php/open-cage-provider": "^4.4",
"geocoder-php/yandex-provider": "^4.3",



User Location (to relate to the maps or other geographic functions):
In addition to using the geographic capability above, we can obtain the log-in location of the user with the 'SmartIP Module'. But anticipate substantial additional set up beyond just installing this module as further described on the Drupal.org site for this module. Also, coordinate your mapping source API decision between the node mapping display from address discussed above with what you use here.

composer require 'drupal/smart_ip:^4.1'
drush en smart_ip






























Smart Content Module:
Geocoding the user location can also be combined with the smart content module to localized content experience to users; perhaps their local airport or airports within their specific region.  This would be for anonymous users and then enhanced with the menu token approach (see menu section) for logged in user personalization.  The smart content module works directly with layout builder integration where smart blocks are Decision Blocks.  This module can also be used for things like A/B testing of content as we move forward.

composer require 'drupal/smart_content'
drush en drupal/smart_content



















