
# Links & Modals

## [Linkit module](https://www.drupal.org/project/linkit)

The [Linkit module](https://www.webwash.net/link-content-using-linkit-drupal-8/) claims three main advantages over traditional linking:

1. The user does not have to copy or remember a URL
2. If a URL alias of a link changes, the link still works
3. It provides configurable information about matching links in the autocomplete
 
The good news is it has the same "look and feel" as the core linking.  The autocomplete, the Token support, settings adjustments by profile, and integration with configuration synchronization makes it comfortable to use. 

`composer require drupal/linkit`<br>
`drush en linkit`

## Editor Advanced Link module

The [Editor Advanced Link module](https://www.drupal.org/project/editor_advanced_link) is often used with Linkit because it adds additional controls to the link.  For example, you might use it to direct a link to open in a new window or browser tab.  In addition, you can use it to put CSS classes or IDs on an HTML attribute giving you even more control.  There is [some set up in involved to bring all the capabilities of this module forward to the widget window to turn on all these functions.](https://www.webwash.net/create-links-using-linkit-module-in-drupal/) This includes being able to include access to it in your CKEditor and highlight a test hyperlink in the body of text.

## Entity Embed Links module

[The Entity Embed Links module](../modules/entityref.md#entity-embed-links) may be an alternative for integration with Drupals Media Management.

## Field Group Link module

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


## Modal module

`composer require drupal/modal_page`<br>
`drush en modal_page`


## Modals - Command Line
Selwyn Polit's online Drupal book is also helpful if you are ready to work at the [detailed coding level with modals](https://selwynpolit.github.io/d9book/modals.html).


<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)


