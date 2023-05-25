
# Content Type

Drupal has lots of basic parts.  Things like an 'Appearance' interface for setting up a theme, a 'Permissions' interface for setting up what type of user can do what on a website, a 'WYSIYG editor' that you can type in or insert plain text, HTML code, etc., an 'Extend' capability for a GUI to turn on and off modules, and much more.  One of the real meat and potatoes parts of Drupal are 'Content Types'.  At install,  two content types are already set up to get you started on a basic website; those are Basic Page and Article.  Here you can [see their similarities and differences; plus see how you might add others.](https://www.youtube.com/watch?v=MZu12T6493w)

## Managing Content

Websites are made up of many different things.  You have the front-page, perhaps sets of article pages for news, sports, financial, social, and an about or contact us page.   Before you actually get to the process of building your website you should make sure you have it designed.  That can range from a pencil and paper set of drawings, to using presentation or drawing tools, to wireframes, and even using [layout tools meant to really nail down all aspects of design.](../chapters.md#layout)

Your website mockup will logically show the type of things to appear on any given page; or the content.  And that content is in need of a home; which is commonly a 'field'.   A page might have a field for a "title", a "sub-title", a main "body" or "story", an "address", a "phone number", an "email address", the "name of a business", and about anything else you can think of.

How are does your layout mockup get translated to a content type and fields?  That process is how you [manage fields and content in Drupal.](https://www.webwash.net/courses/managing-fields-and-content-types-in-drupal/)  At its most basic level, you take each page of your mockup and write in a 'field name' for what it represents.  After you do that for each page you set them all out with the intent to sort them.  But instead of sorting them this time for a workflow sequence, you are aiming to see which pages share the same 'field names'; and fundamentally you have groups that might represent different content types.  There is a good possibility that only the stacks that have several pages in them are their own content type.  Could be that you are ok with the same fields for a news article and a financial article; could be that they differ mainly from the sports or social article because the later have more date/time/event information fields they need.   Look through the various 'one-off' pages to see if they need a separate content type or not; the key question is likely if it might change frequently.  If it is likely to change and be updated frequently by a content editor you might make it a separate content type; perhaps the menu for your restaurant which changes seasonal or with price updates.  The ones that aren't going to change much are candidates to simply use the 'Basic' content type.


## Add Content Type

If the design process you went through finds you need more than an article and basic page content type, you will need to create the additional ones you need.  The process is pretty simple.  Lets assume you find you need a vendor content type and a recipe content type; [here is how to create a new content type.](https://www.youtube.com/watch?v=vyvqiaaGM1k)

## Add Fields

[Adding fields to a content type](https://www.youtube.com/watch?v=CZpfR9WbVcQ) is even easier.  Again, you are referencing your website design mockup; remember you wrote down field names next to each item on each page before you did the sort exercise.  So now all you need to do is select the content type for the page (pile of pages) you want to work on and go through the step of adding each of those fields to it.  You might give thought to picking the content type which shares many fields in common with other content types because once you have created the fields, they can be grabbed from a list of fields already established and associated with any content type where they need to appear.

## A little Techie

Many websites can be built by just using the content types you set up.  However, sometimes there is something a little unusual about what you need which might result in you having to run a little deeper.  The real detailed, details will be presented on a separate section of this documentation.  But even novice site builders can benefit from a little understanding about what these 'content types' and their 'fields' represent in Drupal jargon.

The 'content types' that came with the install and the ones you create as outlined above are each considered unique 'bundles' of something called a 'node'.   A 'node' is one type of a 'content entity'; careful there, a 'content type' is a subset of a 'content entity'.  So a 'content entity' is something bigger in concept.  Well if that is the case, then there must be some other 'content entities' and we want to know what the heck they are…

Content entities besides 'node' might be 'comment', or 'block' or 'user' or even 'file' and 'taxonomy_term'.  Interestingly you can also [add your own 'content entity' in Drupal using something called Drupal Console](https://www.youtube.com/watch?v=leodwoFUm54) or, if you aren't ready to jump into 'code' level stuff, you can also [create your own 'content entity' with a module called the Entity Construction Kit (ECK)](https://www.youtube.com/watch?v=9eDyAWE5WHw)

Since we are already a little way into the deep end, we might also note that in addition to entities that are 'content entity type' there are also others which are 'configuration entity type'.  While a little old, one of the [clearest explanations of some of these field, node, type, bundle, entity things is from a video that Drupalize.me presents](https://www.youtube.com/watch?v=coephBu07Ks)

[There is more about entities on our own site](../book/archandentities.md)


<br>
<br>
<br>

[Learn more... Drupal Basics](../chapters.md#drupal-basics)
