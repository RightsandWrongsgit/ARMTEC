
# MODULES IMPROVING FIELDS 
( You may want to reference 'Schema.Org' as you architect your data.  There you find standards for all sorts of ways data is typically organized.  Using something along these lines makes it more likely you site will be able to utilize others and more effectively coordinate links.)

## Exclude Title

The rest of the items noted to 'improve fields' are generally to add something.  This one it so take something away.  Drupals general default is to have a title on a node or page you are building.  But, lets say you wanted to make a gallery of images and use a link from that image to go to a full page image with an order form.  If you just wanted to have the images in a gallery without the clutter of titles over them, this module would be a good one.  Or think about being a magazine seller who just shows cover images and you click the one you want to read about what that magazine content, price, frequency, etc. are all about.  It can be a little tricky to set it up just right but go the 'help' and 'configure' options under where you enable the modules in the Administration menu.

`composer require drupal/exclude_node_title`<br>
`drush en exclude_node title`

## Smart Trim module
Drupal has a few different text fields for things like short items or long entry of text.  It also has things called display modes where you can, for example, have a 'teaser' display that highlights content in a list  of say articles you might select from which represent summaries of much more detail if you click on it and see a full view display.  Where Smart Trim comes into play is giving you more control over how a summary section of text might be carved out and how its display might indicate to "click for more".  Do you break at the character count or at whole words, do you put `…` at the end or insert a 'For More' alternative to 'Read More'.  Nice little power tool addition to your site.

`composer require drupal/smart_trim`<br>
`drush en smart_trim`


## Address module

Instead of having to create fields for street numbers, street names, cities, states/provinces, countries, etc. you can use the address module where someone has done all that work for you to use.

`composer require drupal/address`<br>
`drush en address`

## Field Group module

The prior Address module is basically a pre-defined group of fields. You can make your own group of any combination of fields you want using this field group module.  Then you can place the group where you need it.  People often think of that as somewhere in a content type.  However, you can actually even place such a group in a Drupal classic PHP input form.](../modules/forms.md#modify-one)

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

### [Smart Date module](https://www.drupal.org/docs/contributed-modules/smart-date)

[Duration and format improvements & calendar display](https://www.youtube.com/watch?v=md86O7Y7rWU) compared to the basic dates in core.

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

<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)
