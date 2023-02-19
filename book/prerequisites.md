# Prerequisites

## You may have this stuff, but if not, do this

Some of these aren't mandatory. However, you really will benefit from and eventually need each of these. Easiest to install them right up front.

### SOFTWARE TOOLS: <sub><sup>(run these from your computer's top level directory)</sup></sub>

- npm

    `install npm`


- Yarn

    `Sudo npm install --global yarn`

- Homebrew

   <sub><sup>`bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`</sup></sub>

   <sub><sup>There are times running uninstall and then install clears some issues</sup></sub>
   <sub><sup>`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall.sh)"`</sup></sub>

   <sub><sup>You may have to do a `brew link --overwrite git` to simply redo some directories that were not cleared of the prior files and get them updated.</sup></sub>


- Nodejs

    `https://nodejs.org/en/download/`


- Composer (To make sure the parts of Drupal have compatible version pleases use Composer)

    `sudo mv composer.phar /usr/local/bin/composer`


    The above command is to install composer globally so it works across all your directories and thus projects. [More on installing composer here …](https://getcomposer.org/download/)

- Docker Docker is under the containers that both platform.sh uses as a host and Lando for your local development environment. The basic Docker things you need will come automatically with the Platform.sh project recipe/template you initially pull. If you already have Docker installed, you may need to let the version step backward to a prior version since you should use the version from the Platform.sh-Lando recipe.

- VSCode is an [IDE](book/ide.md) (Integrated Development Environment); use it with at least with some of the extra extensions.

    `https://code.visualstudio.com/` 


    You can enhance the basic IDE with extensions and some of these can be especially valuable to consider adding now -

    - [Github Pull Request and Issues](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github) provides a GUI alternative to most commands you would have to type

    - [Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory) helps make it easy to compare files and commits to see what was changed

    - [Git Lens-Git Supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) visualize code authorship at a glance, seamlessly navigate and explore Git repositories, gain valuable insights via rich visualizations of branches, and powerful comparison commands

    - [Remote – SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh) lets you use any remote machine with a SSH server as your development environment

    - [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker) makes it easy to build, manage, and deploy containerized applications

    - [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) Quickly swap between different, separate development environments and safely make updates without worrying about impacting your local machine

    - [Indent Rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow) colorizes the indentation in front of your text, alternating four different colors on each step

    - [JSON](https://marketplace.visualstudio.com/items?itemName=ZainChen.json) adds json support
    
    - [Market Place of Extensions](https://marketplace.visualstudio.com/search?target=VSCode&category=Extension%20Packs&sortBy=Installs)
