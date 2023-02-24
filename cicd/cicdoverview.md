
# How is the overall CI/CD Drupal workflow put together?

The intent of the Platform.sh continuous integration and deployment with Lando repository is to use it as a 'grab and go' starting point.  The README on the repository itself aims to provide the instructions for quickly using it.  However, as versions change, as you might be looking to start from a Windows or Linux machine rather than a Mac, as you prefer to consider DDEV or Docksal instead of Lando, you may need to know the underlying details so you can make any adaptions.  The process behind the underpinnings of the repository and the code modification, starting modules additions, etc. are outlined in detail in this GitHub pages hosted companion site.

1) [Prerequisites](../cicd/prerequisites.md) provides a setup to assure your computer has the base tools to make things work.

2) Platform.sh is a foundation to a lot of how this will work well for you.  That host does a pretty good job of making set up simply and providing good documentation.  So three different levels of getting you started with this step are provided.  The [Short-cut](../cicd/platformshdrupal.md#Short-cut-approach:) assumes you are an old hand at working with web stuff.  The [Regular](../cicd/platformshdrupal.md#Regular-approach:) offers basic guidance and might even be a good reminder source.  The [Step by Step](../cicd/platformshdrupal.md#Step-by-Step) is a cookbook with screen shots and detailed guidance.  Any of these methods will get a Drupal website working on your host.  <font color=red>The most important key with any is that the 'branch' you have on the host is named 'main'.</font>

3) [VSCode set to work on your local copy](vscodedrupallocal.md) The easiest way to work with the your website is on your local machine.  So we set up our VSCode [IDE](../book/ide.md) to make local work easy.  VSCode provides a view into the directory structure, individual files you pop into, and a terminal from which to run commands.  It also has Git and GitHub repository connections plus some other goodies outlined in the extensions recommended as part of the prerequisites. 

4) 




[- Next -](../cicd/prerequisites.md)
