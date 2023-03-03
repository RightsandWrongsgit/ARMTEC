
# Appendix:
## Adding php xdebug

A number of things were done to make the local Lando deployment of your 'develop' container more appropriate for the development work you expect to do for a CI/CD workflow to better your site over time.  These were things like turning off annoying cache disruptions, halting js & css aggregation, stopping the site hardening you definitely want in production but not while you are trying to work on changes, etc.  These types of changes to your 'develop' environment make your site building efforts easier.  This would include configuration work, twig_debugging and other front-end type work on js & css theme efforts that will get most people the vast majority of what they need to be productive.  However, we probably shouldn't be putting on a "developer" hat that some of the more hardcore Drupal experts will bring.  They may be working on their own modules or at least patches to modules or tweaking modules to their own unique needs as a code level; not for sissies stuff.  To do that kind for work, one more step might logically be taken and that is to turn on php xdebug in the 'develop' environment.  

As good as that sounds, there is a reason that it isn't simply on all the time and that is it can slow things to a drag.  Therefore, we really would like to have it sit in the ready but turn it on and off on an as needed basis while working.  Being able to use `lando xdebug-on` to enable Xdebug and `lando xdebug-off` to disable Xdebug is the aim.  Adding the following to your `.lando.yml` file should do that:

`name: example-xdebug`<br>
`recipe: drupal9`<br>

`config:`<br>
  `webroot: .`<br>
  `# Xdebug is off by default. We use the tooling below to turn it on as needed.`<br>
  `xdebug: false`<br>

`services:`<br>
  `appserver:`<br>
    `overrides:`<br>
      `environment:`<br>
        `XDEBUG_MODE: 'debug'`<br>

`tooling:`<br>
  `xdebug-on:`<br>
    `service: appserver`<br>
    `description: Enable Xdebug.`<br>
    `user: root`<br>
    `cmd:`<br>
      `- docker-php-ext-enable xdebug && kill -USR2 $(pgrep -o php-fpm) || /etc/init.d/apache2 reload`<br>
      `- tput setaf 2 && echo "Xdebug On" && tput sgr 0 && echo`<br>

  `xdebug-off:`<br>
    `service: appserver`<br>
    `description: Disable Xdebug.`<br>
    `user: root`<br>
    `cmd:`<br>
      `- rm /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini && kill -USR2 $(pgrep -o php-fpm) || /etc/init.d/apache2 reload`<br>
      `- tput setaf 1 && echo "Xdebug Off" && tput sgr 0 && echo`<br>



You can also [make a 'json' file that will allow triggering](https://github.com/AaronFeledy/lando-examples/tree/master/xdebug) with VSCode.


You also want to make sure your [browser has its xdebug extention](https://chrome.google.com/webstore/detail/xdebug-chrome-extension/oiofkammbajfehgpleginfomeppgnglk).


<ul class="pager"> <!--this is the style of the button-->
<li><a href="../cicd/envsettings.html#also-point-to-my-developmentservicesyml">Back to Summary</a></li> <!--This button takes me to the table of contents-->
<!-- <li><a href="#render-document">Next</a></li> <!--This button takes me to the previous page-->
</ul>
