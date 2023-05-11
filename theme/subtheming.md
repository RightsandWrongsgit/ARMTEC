
# Sub-theming

One of the key things to understand is that you are pretty unlikely to start out by writing TWIG templates yourself.  Rather, you are most likely to install an existing Drupal theme which has a bunch of TWIG templates that define it.  If you are just making a real basic website you can probably use the [Olivero theme](../theme/olivero.md) and perhaps ignore this TWIG and Subtheming stuff.   But if you are going after a more unique, customized website, give serious thought to the [Bootstrap theme options](../theme/bootstrap.md)  Then what you are probably going to want to do is to create a sub-theme from one of these already available themes and just edit those parts of it you want to customize. Here is [how to set up your sub-theme](https://www.drupal.org/docs/theming-drupal/creating-sub-themes#:~:text=Sub%2Dthemes%20are%20just%20like,organized%20however%20you%20see%20fit.)

The highlights of what need to be done are:
  -  Under the 'themes' sub-directory, create an additional sub-directory with whatever you want to call your theme (e.g. 'mytheme')
  -  In that my-theme sub-directory make a file called 'my-theme.info.yml' and another called 'my-theme.libraries.yml'

That 'my-theme.info.yml' is basically going to tell your system what parent theme it is referencing, what 'regions' your website contains (likely all or a subset of the parent's), and the libraries location and file sames (typically the css and js file locations and components). The contents of that file are simple, as are most yml or yaml files.  The key thing when ever you edit one of these file is to know that the indents are TWO SPACES (so don't 'tab').  As you work on your site, you might need to jump back into that file to update this library information if you start adding extra css and js files beyond the main style sheet.  It has been [standard practice in Drupal to separate your css into 'base', 'components', and 'layout'](https://www.drupal.org/docs/develop/theming-drupal/adding-assets-css-js-to-a-drupal-theme-via-librariesyml). Although keep your eye on the [single directory components iniative](https://www.drupal.org/docs/develop/theming-drupal/using-single-directory-components) for possible changes. 


<br>
<br>
<br>

[Learn More - CMS Front-end](../chapters.md#front-end)
