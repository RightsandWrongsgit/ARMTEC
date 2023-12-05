
# Drupal Basics

Drupal is a [Content Management System (CMS)](../book/cms.md).  More sites are done in WordPress CMS but it is possible that Drupal may serve more pages because it is more commonly used on powerhouse websites of governments, universities, major businesses, etc.  If you are building for the future, go with Drupal.  Even if your plans now are small scale, Drupal gives you the better path to grow.  Through use the the CI/CD Workflow](../cicd/cicdoverview) provided elsewhere on this site you have the technical path forward to grow your site incrementally.

Besides the CI/CD Workflow important to securing version management of your site, what makes Drupal super for a growth path is all the [Modules](../modules/modulesoverview.md) you can add to it; like tens of thousands.  With the number of Drupal developers worldwide using this [open source](../book/opensource.md) platform, the range of what is available to you free of charge is phenomenal.   Shown on this website are just a handful of the more important modules that you might want to consider while building and then while maintaining your own site.  The [Drupal organization maintains the master list of contributed modules](https://drupal.org), sort of to see all of them.  The "sort of" point is that you can also [write your own modules.](https://github.com/PacktPublishing/Drupal-10-Module-Development-Fourth-Edition) Crazy as that sounds, don't forget you might [just take an existing contributed module that is close to what you are wanting and edit a copy to make it your own](https://www.youtube.com/watch?v=MXCK4XPF6E0), doing exactly what you want.

All that is getting way ahead of ourselves.  If you don't know much about using Drupal you want [the basics from a good tutorial.](https://supporthost.com/drupal-tutorial/) If you prefer [Drupal Video instruction on building a basic site](https://www.youtube.com/watch?v=8-LHnfQmnZ8) this workshop from a fall 2022 Drupal Association conference will be of interest; they actually build a site in like under two hours.  I prefer the [Platform.sh](http://platform.sh) hosting option used in our CI/CD Base Project but those with deeper pockets might use the provider they did in this video who is also very reputable.  After you skim these, you may want to go try Drupal via a [test drive here.](https://www.gitpod.io/docs/introduction/getting-started/quickstart/drupal)

If we assume you found all that to your liking, then turn to our [CI/CD Drupal Base Project](../book/drupalcicd.md) to get rolling with your own first project.  This workflow uses Lando and Platform.sh as local-host connected [containers.](https://code.visualstudio.com/docs/devcontainers/containers) One of the key [benefits of a containerization approach](https://www.mendix.com/blog/benefits-of-containerization/) is the simplicity of building, destroying, and rebuilding a Drupal website.  Don't worry, that workflow set up provided does this in a way that stores your work, lets you backtrack to recover from 'mess ups', and makes learning itself also an iterative process.

## Learning Sources

Besides this site itself, there are a [ton of resources to learn more about Drupal.](https://www.thedroptimes.com/learn-drupal)  Never one to reinvent the wheel checkout a solid list from [Selwyn Polit's Site.](https://selwynpolit.github.io/d9book/learn)  One he may have overlooked that is real strong is called [WebWash from Ivan Zugec](https://www.webwash.net/) over in Australia; he reviews things with real practical 'how to' depth.  [DrupalShip](https://www.drupalship.org/build/when-to-use-drupal) might be one of the better overview of the basics summaries for its scope, clarity, and honest presentation while some of the others take you later to the depth you might need on specific objectives for your own website.  When I was first learning Drupal one of my favorites was the [Code Karate Kid and his 'another daily dose of Drupal' videos;](https://www.youtube.com/@codekaratetutorials) these are somewhat dated at this point but many modules he reviews have current versions worth checking out.  I love how brief they are and wish the new Drupal [Project Browser aimed at a better way to find valuable contributed modules](https://www.drupal.org/project/project_browser) would require or at least encourage module developers to provide these type of brief video overviews.  Perhaps this is your [Open Source Contribution Opportunity.](../book/opensource.md)

### Bridging to Code

Drupal serves the relative novice with many of the features included in its Core installation.  It benefits from adding of the [Layout Builder](../modules/layoutbuilder.md) GUI interface approach and its folding in of much enhanced [Media Management.](../modules/media.md)  Next level enhancements come with its many [contributed modules easily installed by site builders.](../modules/modulesoverview.md)  Understanding the basic [architecture and entities](../book/archandentities.md) moves you closer to being able to try some initial code level developer type efforts.

You might now try to look at the many [slices of solutions provided by a mix of either examples of how to use some modules OR of brief code block examples that you can give a try yourself.](https://www.codimth.com/category/web/drupal)

<br>
<br>
<br>

[Learn More... Drupal Basics](../chapters.md#drupal-basics)

