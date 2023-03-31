
# MODULES IMPROVING FIELDS 
( You may want to reference 'Schema.Org' as you architect your data.  There you find standards for all sorts of ways data is typically organized.  Using something along these lines makes it more likely you site will be able to utilize others and more effectively coordinate links.)

## Address module

Instead of having to create fields for street numbers, street names, cities, states/provinces, countries, etc. you can use the address module where someone has done all that work for you to use.

`composer require drupal/address`<br>
`drush en address`

Address is basically a pre-defined group of fields. You can make your own group with the next module.

## Field Group module

`composer require drupal/field_group`<br>
`drush en field_group`

## Popup Field Group

Same sort of deal using the field group but presenting it as a pop up.

`composer require drupal/popup_field_group`<br>
`drush en popup_field_group`

## Field Group Background Image

Sort of a cool way to present your field group.

`composer require'drupal/field_group_background_image`<br>
`drush en field_group_background_image`

## Field Group Link

So you can have the whole group you established set up to allow a link.

`Composer require drupal/field_group_link`<br>
`drush en field_group_link`

## Linked Field module

Just linking an individual field.

`composer require drupal/linked_field`<br>
`drush en linked_field`

## Iframe module

Control how you open a linked site; as a frame within yours or as a separate browser tab.

`composer require drupal/iframe`<br>
`drush en iframe`

[How to 'Bypass an iframe blocked website link'](https://mail.google.com/mail/u/1/#inbox/FMfcgxwGBmxNzFRfMwvpmxJtqZLGmhQV)

## Token

The [token](../modules/development.md#token) module isn't exactly a field addition in the sense of the others in this section.  However, it sort of is used with the same line of thinking in some of the things you will do with it.  It may be one of the most powerful modules in Drupal because it exposes all the underlying parts such that you can grab and use them; not just in additionally displaying them but also in applying logic with them like filtering views, combining them, etc.

`composer require drupal/token`<br>
`drush en token`

## Field Block module

The [field as block module](https://www.youtube.com/watch?v=Q-F0ZFcfYps) probably is NOT necessary since you can create not only custom blocks but even custom block types right out of Core via Structure/Blocklayout.  However, the special use case is if you are trying to pull something out of the standard presentation of one of your content nodes, display it in another region like a sidebar, but retain the contextual relationship with the base entity you might want to add this module:

`composer require drupal/fieldblock`<br>
`drush en fieldblock`

## Country State City

Make it easy for your users to pull the city, state, and country portion of an address from a pre-populated list of almost a million and a half cities.

`composer require drupal/country_state_city`<br>
`drush en country_state_city`

## Telephone Validation

As handy as an address is, a telephone is as well.  You just want to make sure they are valid and this module gives that warning to users if they mistakenly use one which isn't valid.

`composer require drupal/telephone_validation`<br>
`drush en telephone_validation`

## Some important calendar modules

### Smart Date module

Duration and format improvements & calendar display to core dates.

`composer require drupal/smart_date`<br>
`drush en smart_date`

### Smart date starter kit

`composer require drupal/smart_date_starter_kit`<br>
`drush en smart_date_starter_kit`

### Smart date calendar kit

`composer require drupal/smart_date_calendar_kit`<br>
`drush en smart_date_calendar_kit`

### Office Hours module

Called the Office Hours module, it can be used to indicate when the entities to be associated with each airport stop are available.  When setting this up, make sure it is very user friendly because we want the end-user contributors to populate it as part of the page input.

`composer require drupal/office_hours`<br>
`drush en office_hours`

## Field Permissions module

You can set role permissions from the admin section of Core.  But you can move that further with field level permissions.  And also see under [Taxonomy](../modules/taxonomy.md) using taxonomy term associations to set tight permissions on various entities.

`composer require drupal/field_permissions`<br>
`drush en field_permissions`


