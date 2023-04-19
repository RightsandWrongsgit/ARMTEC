
# Set up Mapping

## Detailed Example 
The several integratable tools for placing a map in your site are [demonstrated with more detailed specific example](../modules/mapinnodes.md).  This example shows how to establish a node for a resturant content type with information about its address, phone number, website, meal occassions, dining style, features, and cuisine.  As you then populate the content of your site with all your recommended resturants the mapping modules grab the address for each and provide a map along with the other information.

There are a few additional mapping tools that you may want to consider beyond the nearly dozen used in the detailed example.  These are:

## Address Map Link
That mapping in the detailed resturant example a little 'overkill'.  You just want to put a map on your simple site.  A basic approach to having a map on your site is the Address Map Link Module in combination with the Address Module.  For most basic sites that want to simply put an address on a page(s) that a user can click to take them to a map, this relatively simple module should do the trick.  If you have a more complex mapping need look further under Multiple Mapping Modules.

`composer require drupal/address_map_link`<br>
`drush en address_map_link`


## Smart IP
Tapping ito the users the log-in location the 'SmartIP Module' can bring geographic information in a general sense that might be leveraged to related proximity to other geocoded information in your site.  This can pull the most locally related information to the forefront to user presentation.

`composer require drupal/smart_ip`<br>
`drush en smart_ip`


## Smart Content module
Geocoding the user location can also be combined with the smart content module to localized content experience to users; perhaps their local airport or airports within their specific region.  This would be for anonymous users and then potentially enhanced with the menu token approach for logged in user personalization.  The smart content module works directly with layout builder integration where smart blocks are Decision Blocks.  This module can also be used for things like A/B testing of content as we move forward.

`composer require drupal/smart_content`<br>
`drush en drupal/smart_content`


## Weather module
Pushing the limits a little, but in a broad sense weather is reported in a geographic map area.  So one of the most basic things we want to do with the current location is to set the initially displayed weather.

`composer require drupal/weather-weather`
`drush en weather-weather`



<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)

