
# MODULES INVOLVING MEDIA & ITS USE

The most current versions of Drupal have upgraded Core to much more fully handle Media.  Go into your Administration/Extend option and check to see if the Media and Media Library modules have been enabled.  If not, do so.

What this upgrade to Drupal Core has done is put support in place to link a piece of media into another content type of node.  Node is pretty much what you are working with when you use the article and basic page content types that were already present when you did your initial install. If you think of a typical website, it is extremely common that you would have a page or node of writing and a picture associated with it; fundamentally a node with one type of media, an image.  Media is broader than that in Drupal in that it also would include things like video, audio, and [a bunch of other social media type things from what they term media providers](https://www.drupal.org/node/2860796); that link taking you to Drupal's project site for a current, but techie looking, list.


(These are the basics, more alternatives under details) -

Focal Point Module (for basic image handling improvements; see section detail for more advanced):
composer require drupal/focal_point
drush en focal_point

Image_link_attributes Module (field format settings like css via GUI):
composer require image_link_attributes
drush en image_link_attributes

Fitvids Module (for responsive themed videos):
composer require fitvids
drush en fitvids

Media Directories module:
composer require drupal/media_directories
drush en media_directories


<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)



