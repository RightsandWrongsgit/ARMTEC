# NOVICE: It's 'OK' you haven't memorized this stuff!

### Somethings are pretty basic but if no one every showed you, you might need a quick reference
Most people have enjoyed using their computer via GUI (Graphical User Interface) applications.  Developing your own website, means getting a little  more underneath the covers. It is a little harder than just driving around existing applications on your computer.  You will need to use things like a 'terminal' or 'command line interface' (CLI) on your computer.  This SUPERNOVICE section is provided to give you some guidance in the basics.  We were all there once.  And you know what, we still pop into this very section now and then to get a reminder. 

- [What are Operating Systems and Shells?](operating&shells.md)

- [What is Git and a Git Repository?](gitbasics.md)

- [What Directory, Project Git Branch, User Profile am I in?](WhereAmI.md)

- [Integrated Development Environment (IDE): VSCode](ide.md)

- [Something seems broken, help!](diagnostics.md)

## SETTING UP YOUR BASIC SYSTEM BEFORE YOU GET STARTED
### WITH THE DRUPAL DOCKER CONTAINER 

We overviewed what Operating Systems were and that different computers are involved in how your computer code is being held in different environments.  It is very likely these different computer environments have different operating systems and configuration settings that could impact compatibility.  Recognizing this, something called ["Containers"](https://www.docker.com/resources/what-container/) have been developed.  Think of these as sort of artifical environments that create a standardization for operations and thus compatibility.  There are a few different Container options but Docker is a common one and we are going in that direction to try to simplify things. We are going to sort of accellerate the steps by just making sure you install the following tools.  Most you will recognize from the prior discussions; those you don't you can read about right at the set up location these links take you to.

<small><font color=yellow> NOTE: this is MAC oriented so you might need to do a few different things with Linux or Windows. Although mainly just that Homebrew is a Mac thing and thus you would skip that. The other items generally lead you directly to option choices by OS if it matters:</font></small> <br>

* [Install Homebrew](https://brew.sh/)
* [Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Obtain GitHub account](https://docs.github.com/en/get-started/signing-up-for-github/signing-up-for-a-new-github-account)
* [Establish SSH Key to GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh)
* [Install Visual Studio Code](https://code.visualstudio.com/download)
* [Install Composer](https://www.drupal.org/docs/develop/using-composer)
* [Install Lando](https://docs.lando.dev/getting-started/installation.html)
* Installing Docker ... Let Lando do this as it installs so version align properly

<br>

If you aren't familiar with website development basics, you probably want to jump to the [quick overview of a content management systems approach](infotechoverview.md#content-management-systems).  If you already know about those and Drupal as a preferred option, you might want to go directly to the [Drupal CI/CD Workflow installation with both local and host environments](drupalcicd.md).  Do keep in mind that that CI/CD Workflow is your foundation or core but that you might also benefit from reviewing the [Drupal Modules section](../chapters.md#drupal-modules) that highlights some common additions to the core that can help with your specific website requirements. Of course, that assumes you have really nailed down your requirements; if not, get help in [design finalization here](../book/opensource.md#design-your-site).

<br>
<br>
<br>

[More Chapters on - Information Technology](../chapters.md#information-technology)
