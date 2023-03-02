
## Appendix:
# CSS & JS Advanced Aggregation 

We earlier showed how to turn off 'css' and 'js' aggregation in the 'local' and 'develop' machine-environments that we establshed in our splits.  We set some syntax in the `settings.local.php` file to a FALSE condition for both.  Where that puts us is not aggregating in those two environments were we would work with our front-end code but allow it to aggregate in the 'staged' and 'main' (Production) sites.  So in these later too, we gain the standard performance advantage of doing aggregation.  There are ways to goose the performance further and this involves the use of installing the advanced aggregation module.

`lando composer require 'drupal/advagg'`

`lando drush en advagg`

For an overview of [setting this module](https://www.volacci.com/drupal-seo-guide/advanced-cssjs-aggregation-module)


<ul class="pager"> <!--this is the style of the button-->
<li><a href="../cicd/envsettings.md#Disable CSS and JS Aggregation>Back to Summary</a></li> <!--This button takes me to the table of contents-->
<!-- <li><a href="#render-document">Next</a></li> <!--This button takes me to the previous page-->
</ul>

