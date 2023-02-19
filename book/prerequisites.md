# **Prerequisites**

(READY?: You may have this stuff, but if not, do this)

You probably can get some of the immediately following steps running without doing these prerequisites. However, you really will benefit from and eventually need each of these. Easiest to install them right up front.

SOFTWARE TOOLS:

(from your computer's top level directory)

- - npm

![Shape1](RackMultipart20230219-1-dxav6g_html_4df7efbba43fc12e.gif)

_install npm_

- - Yarn

![Shape2](RackMultipart20230219-1-dxav6g_html_58f7639b92cab695.gif)

_Sudo npm install --global yarn_

- - Homebrew

![Shape3](RackMultipart20230219-1-dxav6g_html_bbaed06663676e4.gif)

_bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"_

_/_

_/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall.sh)"_

You may have to do a 'brew link --overwrite git' to simply redo some directories that were not cleared of the prior files and get them updated.

 ![Shape4](RackMultipart20230219-1-dxav6g_html_bfa1a7a68c5ea8c3.gif)

_https://nodejs.org/en/download/_

- - Node.js

- composer (To make sure the parts of Drupal have compatible version pleases use Composer)
 ![Shape5](RackMultipart20230219-1-dxav6g_html_e2d2ae1dd7a0b11d.gif)

_sudo mv composer.phar /usr/local/bin/composer_

```

```

The above command is to install composer globally so it works across all your directories and thus projects. More on installing composer here … _https://getcomposer.org/download/_

- docker Docker is under the containers that both platform.sh uses as a host and Lando for your local development environment. The basic Docker things you need will come automatically with the Platform.sh project recipe/template you initially pull. If you already have Docker installed, you may need to let the version step backward to a prior version since you should use the version from the Platform.sh-Lando recipe.

- ![Shape6](RackMultipart20230219-1-dxav6g_html_bfa1a7a68c5ea8c3.gif)_https://code.visualstudio.com/_VSCode is an IDE (Integrated Development Environment); at least with some extensions.

VSCode is a great iIDE that has view panes that show you your project directory structure and files, show the content/code for files you highlight, and provide a terminal where you can run your command lines (CLI). You can enhance the basic IDE with extensions and some of these can be especially valuable to consider adding now:

Github Pull Request and Issues, provides a GUI alternative to most commands you would have to type

Git History, helps make it easy to compare files and commits to see what was changed

Git Lens-Git Supercharged, **visualize code authorship** at a glance, **seamlessly navigate and explore** Git repositories, **gain valuable insights** via rich visualizations of branches, and powerful comparison commands

Remote – SSH, lets you use any remote machine with a SSH server as your development environment

Docker, makes it easy to build, manage, and deploy containerized applications

Dev Containers, Quickly swap between different, separate development environments and safely make updates without worrying about impacting your local machine

Indent Rainbow, colorizes the indentation in front of your text, alternating four different colors on each step

JSON, adds json support
