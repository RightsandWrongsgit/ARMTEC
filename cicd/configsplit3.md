
## Configurations by split

We have the `config/sync` directory for the common configuration across all environments.  Drupal Core modules are installed; although not all are enabled.  We can add contributed modules and enable modules anytime we want.  There are some advantages to doing so before we branch our splits in the sense that we don't have to commit/synch/merge to assure they are in all environments.  Therefore, you may want to add others you know you will use across all environments to the table below.  The table shows the environment_indicator and the structure_sync module as examples; because we know we are going to use them as part of our CI/CD setup.<br>
<br>
The table also shows the four split names that we set up directory homes for configuration files; uniquely for 'main', 'staged', 'develop' and 'local'.  Under each named split are modules you should consider installing for that unique environment.  Remember that the easiest way to think about config_split is that is ADDS what you put in it TO THE BASE configuration in 'sync'.<br>
<br>
What you need to do is the classic `lando composer require 'drupal/insertmodulename'` for each of the modules to be added to your system just like we did when we installed the config_split module itself.  <font color=yellow>But DO NOT ENABLE these modules like we previously did!</font><br>  [We are going to take a special approach to doing that only within the split where we want them.](../cicd/autoconfig.md#automate-the-automatic)

<img src="../cicd/captures/configtable.png"  width="1000">
<sup><sub>TABLE KEY:  S = Site Builder,  B = Beginning Developer,   D = Developer</sub></sup><br>
<br>

<p>To download an Excel file copy of this table of your own that you can edit and add to  <a href="armtec.services/assets/downloads/config_split_table.xml" download>Click here!</a>
[download]({{ site.baseurl }}{% link /assets/downloads/config_split_table.xml %})

<br>
<br>
<br>

Some of the customizations in the 'local' and 'develop' splits may be for more advanced developers.  Drupal is built using an Object Oriented Programming language, to a large extent a [Symfony framework](https://symfony.com/) version of PHP.  You can do stuff at an extremely low level where you are leveraging some unique strengths of how Drupal database structures are organized and OOP programming allows reuse of fundamental function calls to literally 'create' not only your own modules but even core entities below those represented in [Content Types](http://www.drupal.org/docs/8/modules/allow-a-content-type-only-once-only-one/configuring-content-types) made up of multiple bundles.  If you are a developer familiar with OOP and PHP you might want to turn on the "D" items in the above table.  The "B" items are for beginning developer and would be something that those who want to glimpse under the hood to gain in understanding.  The "S" items are for site builders who are mainly oriented toward using all that is core to Drupal itself and the tens of thousands of contributed modules others have already written.  This later group is for the normal humans like you and me to do 99% of anything we really want.<br>

[See what the YML files in configuration do.](/cicd/configsplit4.html)  By understanding their role you can look each up and determine how you might want to split their use.  What you do when you want to split one is to copy the file from the 'config/sync' subdirectory and paste the copy into the directory you want to have some different action take place.  Then open that file in your VSCode editor and review the code it contains.  Since it is YML, a very "English" syntax, it is pretty easy to figure out what you would want to edit to make a change.  Typically just something like changing a TRUE to a FALSE.

<br>
<br>
<br>

[- Next -](../cicd/envindicator.md)
