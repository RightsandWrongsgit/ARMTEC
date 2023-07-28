
# Smart Trim Module

Drupal core already contains a basic text trim capability.  What that means is that you might have a bunch of articles on various subjects that you have tagged or associated with [taxomony terms](../modules/taxonomy.md) and want to present to users as a summary highlights list.  You create a [view](../modules/views.md) of that list where you only want to present the title and several lines from the start of each article to users to skim and select which they want to "Read More" about.  Getting to that summary text is trimming.

The trim capability in Drupal core is pretty basic.  What if you wanted to trim by 'word count' instead of 'character count' so the summary text users see don't have partial words?  What if you want to say "Full Article Here" instead of "Read More" as the prompt to open the full article?  These are a bunch of other more powerful feature options can be added by installing the Smart Trim Module.

## The Module

The [Smart Trim module](https://www.drupal.org/project/smart_trim) installs in the usual way with [composer](../book/Novice.html#setting-up-your-basic-system) and is enabled with [drush.](/modules/development.md#drush)

`composer require drupal/smart_trim`<br>
`drush en smart_trim`

## Using Smart Trim

One of the real wizards of getting the most out of Drupal through sharing summary video's on important contributed modules is [Ivan Zugec who runs a company called WebWash](https://www.webwash.net/) and he does a nice job of further explaining [Smart Trim](https://www.webwash.net/trim-text-fields-summaries-smart-trim-in-drupal/)

# In Other Words Module

List formating is another type of edit customization that you might need.  Instead of thinking about carving a text field into slices that display it more optimally, there are times when you have a set of items that make up a list which you want presentation control over.  An example of this might be having a number of authors associated with some published content.  Do you dump them in a stack, on a line, do you put commas between them, include the word 'and' between the next to the last and the last one, etc?  There is whole range of list presentation control with [this extra module that brings more natureal display of lists.](https://agaric.coop/blog/display-lists-naturally-other-words-module-drupal)

You want the control of the [In Other Words Module.](https://www.drupal.org/project/inotherwords)



<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)
