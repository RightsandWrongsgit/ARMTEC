
# npm & Node JS

npm is a package manager for JavaScript.  A package manager keeps things coordinated between versions of software components.  You will also be using another package manager called [Composer](https://www.drupal.org/docs/develop/using-composer) but it works to keep versions coordinated in another part of your application that uses ['php'.](https://www.php.net/)

Node JS is the JavaScript run time environment that you will install as well.  Between these two you will have JavaScript available to work with your website application.

## npm/Node JS Install

[Here is the standard way that these are installed.](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)  If you are working with traditional 'metal' servers to host your application that information will guide you.  And, regardless, it will be a good reference document.

## Go Here instead

ARMTEC, Inc. tends to the [Container](https://code.visualstudio.com/docs/devcontainers/containers) approach to hosting web services for consistency across deployment environments.  We aim for a [Lando](https://docs.lando.dev/) local development environment and combine it with a host that runs connected, coordinated containers.  The [Drupal CI/CD Base Project](../book/drupalcicd.md) uses the [Platform.sh service](https://platform.sh/) as the coordinated host.

Since Lando on your local machine is where you are going to do your development, what you want to accomplish is to "inject" the tools you will be needing inside your container.  [Here is how you need to do that in Lando.](https://docs.lando.dev/node/frontend-tooling.html)

If you are going to use the [Bootstrap theme](../theme/bootstrap.md) and leverage the extraordinary capabilities of doing so with the [SASS front-end development option](../theme/bootstrap.md#barrio-wsass), <font color=yellow>[you will want to also include the additional tooling noted for Gulp and potentially YARN](https://docs.lando.dev/node/frontend-tooling.html#making-tooling-available-on-the-cli).</font>

<br>
<br>
<br>

[More about Setting up your basic system](../book/Novice.md#setting-up-your-basic-system)
