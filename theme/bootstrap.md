
# Bootstrap Theme

[The Bootstrap framework](https://getbootstrap.com/) is a highly capable website front-end toolkit.  It is [responsive](https://www.youtube.com/watch?v=srvUrASNj0s) so your website will look good on a computer, a tablet, a phone, etc.  It is also well integrated with CSS via a call from the 'head' and with JavaScipt (JS) from a similar script call.  The Flexbox capability allows the creative use of a grid style which provides interesting layout throughout your web pages; though do leverage [Semantic Design principles](https://www.semrush.com/blog/semantic-html5-guide/) as you manage your design deployment.  Another great factor that draws one to Bootstrap is its inclusion of [many prebuilt components](https://getbootstrap.com/docs/5.0/components/accordion/).


## Bootstrap Barrio

Bootstrap is so commonly used with Drupal that tens of thousands of site report using it via the [Bootstrap Barrio](https://www.drupal.org/project/bootstrap_barrio) theme.  What this offers over the basic Bootstrap is that someone has written loads of [TWIG templates](../theme/twig.md) to jumpstart your own site.  Think of this as having things like off the shelf components for stuff like cards already available to use directly in Drupal.  Since Barrio is built upon Bootstrap you can also go native if you need something beyond what has been pre-built. It is so good that you many major government agencies use it and this [video on how one adopted it will convince you to head this way](https://www.youtube.com/watch?v=oAZ6-eADtKY)

Another thing that makes Bootstrap Barrio's popularity an advantage is there are [good videos on how to install and use it](https://www.youtube.com/watch?v=D5A_aFdlWEs); don't be thrown off that the Bootstrap version has been updated since this video as all that is covered is still accurate.  You also have probably heard about Drupal's own ['Layout Builder' module](https://www.specbee.com/blogs/layout-builder-in-drupal-9-complete-guide#:~:text=Scroll%20to%20the%20bottom%20and,of%20the%20view%20modes%20present.) that offers some nice drag and drop site building support.  The good news is that [Layout Builder and Bootstrap can play nice together as demonstrated in this video on using Bootstrap's card component in it](https://www.youtube.com/watch?v=iwJW18NA_S4).

## Install Bootstrap Barrio

[Bootstrap Barrio installation](https://www.drupal.org/project/bootstrap_barrio) has enough features and options plus frequent updates you are best off folling the modules' specific instructions on the Drupal.org site.  Once you have that in place you will want to create your custom [subtheme](subtheming.md) to run under it and a [super simple overview of installing a Bootstrap Barrio subtheme via a script makes is easy.](https://www.youtube.com/watch?v=6paPMGxPu4g)

## Extras/modules

If you decide to use the Bootstrap theme (or it's Barrio deployment) you may want to at the following contributed modules to enhance its utility even further.

### Views Bootstrap 

This module has unique install instructions depending on the version of Bootstrap you are using in theming. Views is one of the most powerful features of Drupal so having bootstrap features integrated with it is great.   Go to the Drupal.org site for the right version install instructions to [match your Bootstrap and Drupal versions](https://www.drupal.org/project/views_bootstrap).


### Bootstrap Layout Builder

First try using native Layout Builder after you have Bootstrap installed and set as default.  Then consider adding this views bootstrap module to get some potential additional functionality around accordion, carousel, etc.  Bootstrap Layout Builder uses different configuration settings for the grid layout choices, gutters, container widths, etc.  You can jump start the utility of its combination with Bootstrap by using this module.  See how using the [GUI interface in modern Drupal to do much of your front-end work, is enhanced by using this module with the Bootstrap theme.](https://www.youtube.com/watch?v=sMbiqSMiZ6Y)

`composer require drupal/bootstrap_layout_builder`<br>
`drush en bootstrap_layout_builder`

### Bootstrap Block Styles

The Block Styles Module adds a styles selector at the end of the block configuration form.  Included styles support Bootstrap Styles on submodule for (modal, Dropdown, card, and collapse). The assumption is that a dependency on the Styles API will install it at the same time.

`composer require drupal/block_styles`<br>
`drush en block_styles`

### Bootstrap Styles

This underlies the Bootstrap Layout Builder's styles plugins. 

`composer require drupal/bootstrap_styles`<br>
`drush en bootstrap_styles`

### Bootstrap Layout Builder Library

This is key to [saving reusable layout sections and whole templates within Bootstrap Layout builder's GUI interface](https://www.youtube.com/watch?v=-dhI5-Fs4qk) so you can speed development by grabbing stuff from a library you build up specific to your site.  Learn more about how this library add-on module allows for sharing templates and discussion of establishing a repository of templates](https://www.youtube.com/watch?v=E68DxSLcCd0) you might benefit from others work efforts. 

`composer require drupal/section_library`<br>
`drush en section_library`

### Bootstrap external link

This module provides a Pop up Modal warning of an external link leaving site.

`composer require drupal/bootstrap_external_link_popup`<br>
`drush en bootstrap_external_link_popup`

### Bootstrap SASS
[Bootstrap SASS](https://www.drupal.org/project/bootstrap_sass) provides the SASS approach to CSS compiling within Bootstrap.  It is typically listed as an option on the [Bootstrap Barrio theme overview.](https://www.drupal.org/project/bootstrap_barrio) Confirm that it isn't already installed via some sort of a dependency with the basic theme.  If you need to add the SASS Start Kit separately it is installed like a normal theme with composer.

`composer require drupal/bootstrap_sass`<br>
`drush en bootstrap_sass`

### Bootstrap Local

You probably don't need this module.  Normally the 'head' of your website pages will tell the page to look for the bootstrap library on the web.  There are times when having that bootstrap library locally can be useful.  For example, if you have an existing theme on your site and are replacing it with bootstrap you may prefer to do all your work locally; say in a Lando or other local Docker container instance of your website and put it through your normal [CI/CD workflow (e.g. GitOps).](../book/drupalcicd.md)  If you want to load the bootstrap library locally you use this module; otherwise you set up the CDN approach.

`composer require drupal/bootstrap_library`<br>
`drush en bootstrap_library`



<br>
<br>
<br>

[Learn More - CMS Front-end](../chapters.md#front-end)

