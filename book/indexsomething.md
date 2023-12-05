

# Browser & Index.something


Browsers on your computer are something like [Safari](https://www.apple.com/safari/), [Chrome](https://www.google.com/chrome/browser-tools/), [FireFox](https://www.mozilla.org/en-US/firefox/), [Opera](https://www.opera.com/browsers), the [Tor](https://www.torproject.org/) Privacy Browser [Onion](https://onionbrowser.com/) and others.  Browsers have built in 'smarts'.  They know how to run code for things on the [Front-end](../theme/frontoverview.md) like HTML, JavaScript, CSS, etc.  

## Index File

The first file a browser looks for at the start is an 'index' file.  Most people are familiar with that being an index.html file that is styled like this:

<br>

<img src="images/media/indexhtml.png" width="400" height="350" alt="index.html file example">
  
<br>
        
This [example from "FreeCodeCamp" is explained in detail on their site.](https://www.freecodecamp.org/news/html-starter-template-a-basic-html5-boilerplate-for-index-html/) Generally think of the first line of an index file like this telling the browser what language to talk.  Then the stuff between <head> and </head> are behind the scenes instructions and calls to supporting links that your site might need; and sometimes the list is way, way more extensive than the above example.  The stuff between `<body>` and `</body>` is really the working part of your website that people see; or at least the parts between `<main>` and `</main>` in the example.  Why is that `<script>` stuff in the `<body>` area then if it isn't showing directly?  Think of it because JS or JavaScript is actually very involved in unique display aspects of your site, especially where interaction or actions are displayed.

## Other Index

[While Index.html is most commonly used, extensions other than 'html' can also follow. ]( https://en.wikipedia.org/wiki/Web_server_directory_index)  If index.cgi or  index.pl is found, PERL is the language expected.  With index.php the language is php. If your system were to find multiple index.something files there is an order the webserver searches for an index file:

`index.html index.cgi index.pl index.php index.xhtml index.htm`

These other index.something files are often called when a website has more depth to it and the [front-end ](../theme/frontoverview.md)  speaks to a back-end server-side component.  Since Drupal's [CMS](../book/cms.md) is built upon a 'php' framework, a [quick peek at index.php may be worth understanding.](https://www.youtube.com/watch?v=0YMt5JdvOmc)

If you happen to know HTML already, you will find it interesting that you can mix it with 'php' to quickly add some dynamic updates to your work.  An example of [building several parts of a website with HTML and having index.php make key calls to it is worth understanding.](https://www.makeuseof.com/tag/build-simple-php-website/) For a more [in depth review of mixing HTML and php you might find this summary tutorial session valuable.](https://code.tutsplus.com/tutorials/how-to-use-php-in-html-code--cms-34378)

## Index to Settings.PHP to ...

The Content Management System [(CMS)] Drupal, is developed using Symfony as a PHP backend or server-side language.  PHP is an [Object Oriented language.](https://en.wikipedia.org/wiki/Object-oriented_programming) Understanding how a "Request" through a user action is basically 'traffic directed' to the right point via a controller where arguments are applied to produce a response(s) can be very helpful in understanding your options in working with Drupal.

<img src="../book/images/drupalworkflow.png"  width="600">

<br>

[How Drupal works under the hood](https://www.youtube.com/watch?v=CIxYGqY8nPs&t=2177s) with that workflow gives you an understanding of what you have in your index.php, settings.php, and application code logic application in moodules.  What is really interesting is how what is output by Drupal can be worked upon by a more than one approach to formating a response.  The video points out that "Headless Drupal" might more properly consider multi-headed Drupal where you take the same basic Drupal generated output to feed standard Drupal content [TWIG templates,](../theme/twig.md) independent JavaScript, and CSV or PDF to serve multiple valuable output for your users.


<br>
<br>
<br>

[More Chapters on - Information Technology](../chapters.md#information-technology)




