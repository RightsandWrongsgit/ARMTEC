# Hosting
# Others See Your Website

Most people tend to want to build their website on their own computer.  You can work on it without an internet connection and local tends to be faster than passing files back and forth.  If you haven't messed around with any website building before, you might want to try doing what is called a 'static site' just to get use to basic principles.  For example, did you know that the foundation  of any site is to have a file called 'index.something'.  That something might be 'html', or 'php' or 'md', among others.  One of the easiest and least expensive way to get a feel for all this is to just build a static website right here on GitHub; in fact, you are reading this on such a site right now!

## A Free Static Website for Practice
- [Building your site on GitHub pages](https://moezmustafa.medium.com/free-website-hosting-with-github-pages-4ebeedbd8d82){:target="_blank"}
- [Getting Started with Jekyll and GitHub pages](https://www.aleksandrhovhannisyan.com/blog/getting-started-with-jekyll-and-github-pages/){:target="_blank"}
- [Jekyll](https://jekyllrb.com/){:target="_blank"}
- [GitHub Pages Tutorial](https://tomcam.github.io/least-github-pages/){:target="_blank"}
- [Set up a Blog in GitHub Pages](https://aregsar.com/blog/2019/how-to-setup-your-github-pages-blog-structure-in-five-minutes/){:target="_blank"}
- [GitHub Pages Markup Guide](https://www.markdownguide.org/tools/github-pages/){:target="_blank"}
- [GitHub Pages Refresh Cache](https://github.com/orgs/community/discussions/19713){:target="_blank"}

<br>

## Inexpensive Drupal Hosting

Hosting a Drupal site can have a huge range of costs.  Sort of depends on how much you have on the site (storage) and how many visitors you get (traffic).  The other things is what sort of services and support you might expect to get.  While I am a fan of Platform.sh for container based and scalable hosting with basic but not extensive support, you might simply have a smaller scale site you want to minimize costs to host.  [Watch this](https://www.webwash.net/host-drupal-sites-using-siteground/)

<br>

## Static Drupal Hosting

As long as we are covering inexpensive Drupal hosting, here is a quick mention of Static Drupal as another option.  Shortly you will see the Lando container option for working with Drupal on you local machine.  The [Drupal CI/CD Project template](/book/drupalcicd.md) provided on this site uses that Lando option with Platform.sh as the host for a full fledged Drupal site.  Lando is free since it is on your machine.  Platform.sh eventually has a cost.   Another approach is to build your site locally and then [deploy it as a Static site as shown in this video.](https://www.youtube.com/watch?v=IgzmHHGcr1E)  The video gives some very clear situations where you can to use a Static site but please understand you also give up a huge portion of Drupal's advantages.  That said, one way you might use a free or dirt cheap Static hosting combination with Drupal is for your small scale sites.  As you are learning to use Drupal you might come up with any number of ideas for websites for your church, scout troop, charitable event, etc.  And once people find you know how to build websites you will have loads of requests for what are pretty simple sites that offer you practice with Drupal.  But, those non-profit and friend request sites often don't want to pay for hosting.  What you can do is add the [Tome module](https://www.drupal.org/project/tome) to your Drupal base development template and work up a very basic site that you output as Static files in a 'tarball' compressed state.  Those static files get pushed to a free or low priced host.  And one such option is even highly coordinated with its own Drupal module [Tome Netlify.](https://www.drupal.org/project/tome_netlify)   An additional emerging approach is to use an online access to a container build like [GitPod](book/hosting.md#GitPod/DrupalPod) to then [host deploy via Tome and Tome Netlify like presented by those module's developer](https://www.youtube.com/watch?v=KpQ3MyP5g1Q) (you may want to skip to the 22 minute point of the video for the hands on demo).

<br>

## Using Containers to Run your Site
Most people probably stopped here because of an interest is a Content Management System (CMS) site; Drupal being the powerhouse option.  With a CMS, you have the option of constantly updating content with the least effort. In fact, once built, such a site might be fed content updates automatically from other sites on the internet.  Imagine stories from your favorite sources flowing in to update you on topics you feature.  Imagine data flowing in and your site integrating and displaying a unique perspective on it.  From Blogs, to Newspapers, to E-Commerce, to collections of Universities, Museums, Governments, and more are things you might find built with a Drupal CMS.  Your plans don't need to start out so grand; but it is nice to know you have selected a CMS platform with Drupal that can expand as you do.

Containers themselves are NOT the CMS.  Rather, the container is the 'environment' that your applications such as a website run within.  You might think of containers like servers but more because multiple parts can combine.  You might think of them like 'Virtual Machines' and that is halfway accurate in that containers are able to emulate a wide variety of physical hardware set ups; a real advantage in avoiding what are referred to as "Well it ran on my machine errors".  What is really great is that containers are packaged with the code you right so when mounted on any machine, your application will run.  Where that pays dividends is say you want to scale your application to run in mirrored setups across multiple geographies to assure great response speed to widely distributed users.

<br>

### Docker and Docker-Compose Containers
Docker is the foundation behind the most common approach to using containers. Docker and Docker-Compose will be installed for you when you install the local container tool called Lando and you really need to let Lando do that job for you because it assure the versions are properly aligned.  Once it these Docker elements are up and running, it can pay dividends to at least jump into Docker-Composer for a visual perspective on what container(s) are running; and sometimes stopping and removing them at this level is a helpful cleanup if you are doing a container rebuild on your machine (and don't freakout about that, because it typically only takes a few minutes).  All that said, this Docker Tutorial video is two hours long so you won't be blamed it you don't watch it. <br>

- [Docker Tutorial video](https://www.youtube.com/watch?v=1eVy_iWrc20){:target="_blank"}
- [Docker Tutorial video 3hr option](https://www.youtube.com/watch?v=iARL7iFyasE&list=PLVx1qovxj-amqyqHceAhkcsopzi4PFcKc&index=2){:target="_blank"}

<br>

### Running Containers Locally (Lando and alternatives)
Let's get this out of the way.  The focus at ARMTEC for local containers is Lando.  There is an option called DDEV that seems very similar but when you look at documentation references on this site you will have to do the translation if you go that way; it probably isn't a huge effort but just something in the scheme of things that could add frustation.  There is also an option called Docksal but how it compares isn't current knowledge here.  Lets talk about Lando...

<br>

### Running and connecting to Container Hosts for Deployment

- [Lando Platform.sh Demo](https://www.youtube.com/watch?v=ynUYCj147Xw){:target="_blank"}

<br>

## GitPod/DrupalPod

The container approach and Drupal are a fast moving space.  [GitPod](https://www.gitpod.io/) is a container hosting environment that brings up a build in minutes and has been used by the Project Browser initiative in Drupal to quickly demonstrate the progress they are making by allowing people to test drive.  That test drive can be applied to any other module that you might drop in with a 'composer xxxx' command and a 'drush en xxxx' command.  But in our experience the environment expires in 60 minutes.  However, that is without even [signing up for a GitPod account.](https://www.gitpod.io/)  And the addition of a [Chrome or Firefox extention called DrupalPod](https://www.drupaleasy.com/blogs/ultimike/2023/12/using-drupalpod-core-and-contrib-development) with an increasingly integrated environment will make you want to monitor this as an opportunity with your Drupal site plans.

<br>

## Advanced Topic: Kubernetes
We discuss using containers as an approach to deploying a site.  These might be local tools like Lando or DDEV.  They may be hosted containers like Platform.sh or Amazee.io who wrap their environments with tools that make working with them more user friendly.  But 'the big boys' who are replicating mirrored sites around the global are more likely diving into Docker on a native basis and even something called Kubernetes that get to closer to the raw world out there.  You aren't going to start there but understand that Drupal is fully capable of playing in that world and often does.  So when you are read take a look at [Kubernetes via this nice free video series.](https://www.youtube.com/playlist?list=PL6nVblW4NNATO7Zq_RwIBNeKc0Es8jJWV)
<br>
<br>
<br>

[More Chapters on - Information Technology](../chapters.md#information-technology)
