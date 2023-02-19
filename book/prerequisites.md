[]{#section0001.xhtml}

[Prerequisites]{.span0}

[(]{.span1}[READY?:]{.span1}[ ]{.span1}[You may have this stuff, but
]{.span1}[ ]{.span1}[if not, do this)]{.span1}

 

[Y]{.span2}[ou probably ]{.span3}[can]{.span2}[ get some of the
immediately following steps running without ]{.span3}[doing
]{.span3}[these ]{.span3}[prerequisites.]{.span3}[
]{.span3}[ ]{.span3}[However, you really will benefit from and
eventually need each of these. ]{.span3}[ ]{.span3}[Easiest to]{.span2}[
install ]{.span3}[them]{.span3}[ ]{.span3}[right up front.]{.span3}

 

[SOFTWARE TOOLS]{.span4}[: ]{.span3}

[(from your computer\'s top level directory)]{.span5}

[- ]{.span6}[npm]{.span6}

::: frame0
[install npm]{.span7}
:::

[                ]{.span6}[                ]{.span6}

 

[                ]{.span8}[- Yarn]{.span8}

::: frame1
[Sudo npm install \--global yarn]{.span9}
:::

[                ]{.span10}[                ]{.span10}

 

[                ]{.span11}[- Homebrew]{.span11}

::: frame2
[bin/bash -c \"\$(curl -fsSL
https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)\"]{.span9}
:::

[                ]{.span12}[                ]{.span12}[/]{.span13}

[                ]{.span11}

[                ]{.span14}[                ]{.span14}[/bin/bash -c
\"\$(curl -fsSL
https://raw.githubusercontent.com/Homebrew/install/master/uninstall.sh)\"]{.span14}

[                ]{.span15}[                ]{.span15}[
]{.span15}[ ]{.span15}[You may have to do a 'brew link \--overwrite git'
to simply redo some directories that were not cleared of
]{.span16}[                ]{.span16}[                ]{.span16}[
]{.span16}[ ]{.span16}[the prior files and get them updated.]{.span16}

 

::: frame3
[https://nodejs.org/en/download/]{.span7}
:::

[                ]{.span11}[- Node.js]{.span11}

[                ]{.span11}[                ]{.span11}

[composer ]{.span3}[ ]{.span3}[(To make sure the parts of Drupal have
compatible version pleases use Composer)]{.span3}

::: frame4
[sudo mv composer.phar /usr/local/bin/composer]{.span7}
:::

 

[The above command is to install composer globally so it works across
all your directories and thus projects. ]{.span17}[ ]{.span17}[More on
installing composer here ...
]{.span17}[ ]{.span17}[https://getcomposer.org/download/]{.span18}

[docker ]{.span3}[ ]{.span3}[Docker is under the containers that both
platform.sh uses as a host and Lando for your local development
environment. ]{.span17}[ ]{.span17}[The basic Docker things you need
will come automatically with the Platform.sh project recipe/template you
initially pull. ]{.span17}[If you already have Docker installed, you may
need to let the version step backward to a prior version since you
should use the version from the Platform.sh-Lando recipe.]{.span17}[
]{.span17}

::: frame3
[https://code.visualstudio.com/]{.span7}
:::

[ ]{.span19}[VSCode ]{.span19}[ ]{.span19}[is an IDE (Integrated
Development Environment); at least ]{.span19}[with]{.span2}[ some
extensions.]{.span19}

 

[VSCode is a great iIDE that has view panes that show you your project
directory structure and files, show the content/code for files you
highlight, and provide a terminal where you can run your command lines
(CLI). ]{.span20}[ ]{.span20}[You can enhance the basic IDE with
extensions and some of these can be especially valuable to consider
adding now:]{.span20}

[Github Pull Request and Issues]{.span21}[, provides a GUI alternative
to most commands you would have to type ]{.span20}

[Git History]{.span21}[, helps make it easy to compare files and commits
to see what was changed]{.span20}

[Git Lens-Git Supercharged]{.span21}[, ]{.span22}[visualize code
authorship ]{.span23}[at a glance, ]{.span23}[seamlessly navigate and
explore ]{.span23}[Git repositories, ]{.span23}[gain valuable insights
]{.span23}[via rich visualizations ]{.span23}[of branches,
]{.span23}[and powerful comparison commands]{.span23}

[Remote -- SSH]{.span24}[, ]{.span23}[lets you use any remote machine
with a SSH server as your development environment]{.span23}

[Docker]{.span24}[, ]{.span23}[makes it easy to build, manage, and
deploy containerized applications]{.span23}

[Dev Containers]{.span24}[, ]{.span23}[Quickly swap between different,
separate development environments and safely make updates without
worrying about impacting your local machine]{.span23}

[I]{.span24}[ndent Rainbow]{.span24}[, ]{.span23}[colorizes the
indentation in front of your text, alternating four different colors on
each step]{.span23}

[JSON]{.span24}[, ]{.span23}[adds json support]{.span23}
