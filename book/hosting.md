# Hosting: Let Others See Your Website

Most people tend to want to build their website on their own computer.  You can work on it without an internet connection and local tends to be faster than passing files back and forth.  If you haven't messed around with any website building before, you might want to try doing what is called a 'static site' just to get use to basic principles.  For example, did you know that the foundation  of any site is to have a file called 'index.something'.  That something might be 'html', or 'php' or 'md', among others.  One of the easiest and least expensive way to get a feel for all this is to just build a static website right here on GitHub; in fact, you are reading this on such a site right now!

## A Free Static Website for Practice
- [Building your site on GitHub pages](https://moezmustafa.medium.com/free-website-hosting-with-github-pages-4ebeedbd8d82){:target="_blank"}
- [Getting Started with Jekyll and GitHub pages](https://www.aleksandrhovhannisyan.com/blog/getting-started-with-jekyll-and-github-pages/){:target="_blank"}
- [Jekyll](https://jekyllrb.com/){:target="_blank"}
- [GitHub Pages Tutorial](https://tomcam.github.io/least-github-pages/){:target="_blank"}
- [Set up a Blog in GitHub Pages](https://aregsar.com/blog/2019/how-to-setup-your-github-pages-blog-structure-in-five-minutes/){:target="_blank"}
- [GitHub Pages Markup Guide](https://www.markdownguide.org/tools/github-pages/){:target="_blank"}

## Using Containers to Run your Site
Most people probably stopped here because of an interest is a Content Management System (CMS) site; Drupal being the powerhouse option.  With a CMS, you have the option of constantly updating content with the least effort. In fact, once built, such a site might be fed content updates automatically from other sites on the internet.  Imagine stories from your favorite sources flowing in to update you on topics you feature.  Imagine data flowing in and your site integrating and displaying a unique perspective on it.  From Blogs, to Newspapers, to E-Commerce, to collections of Universities, Museums, Governments, and more are things you might find built with a Drupal CMS.  Your plans don't need to start out so grand; but it is nice to know you have selected a CMS platform with Drupal that can expand as you do.

Containers themselves are NOT the CMS.  Rather, the container is the 'environment' that your applications such as a website run within.  You might think of containers like servers but more because multiple parts can combine.  You might think of them like 'Virtual Machines' and that is halfway accurate in that containers are able to emulate a wide variety of physical hardware set ups; a real advantage in avoiding what are referred to as "Well it ran on my machine errors".  What is really great is that containers are packaged with the code you right so when mounted on any machine, your application will run.  Where that pays dividends is say you want to scale your application to run in mirrored setups across multiple geographies to assure great response speed to widely distributed users.

### Docker and Docker-Compose Containers
Docker is the foundation behind the most common approach to using containers. Docker and Docker-Compose will be installed for you when you install the local container tool called Lando and you really need to let Lando do that job for you because it assure the versions are properly aligned.  Once it these Docker elements are up and running, it can pay dividends to at least jump into Docker-Composer for a visual perspective on what container(s) are running; and sometimes stopping and removing them at this level is a helpful cleanup if you are doing a container rebuild on your machine (and don't freakout about that, because it typically only takes a few minutes).  All that said, this Docker Tutorial video is two hours long so you won't be blamed it you don't watch it. 

- [Docker Tutorial video](https://www.youtube.com/watch?v=1eVy_iWrc20){:target="_blank"}
- [Docker Tutorial video 3hr option](https://www.youtube.com/watch?v=iARL7iFyasE&list=PLVx1qovxj-amqyqHceAhkcsopzi4PFcKc&index=2){:target="_blank"}


### Running Containers Locally (Lando and alternatives)
Let's get this out of the way.  The focus at ARMTEC for local containers is Lando.  There is an option called DDEV that seems very similar but when you look at documentation references on this site you will have to do the translation if you go that way; it probably isn't a huge effort but just something in the scheme of things that could add frustation.  There is also an option called Docksal but how it compares isn't current knowledge here.  Lets talk about Lando...



### Running and connecting to Container Hosts for Deployment

- [Lando Platform.sh Demo](https://www.youtube.com/watch?v=ynUYCj147Xw){:target="_blank"}
