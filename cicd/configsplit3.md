
## Where are we heading with configurations in these splits

We have the config/sync directory for the common configuration across all environments.  We have installed Drupal Core so its modules are installed; although not all are enabled.  We can add contributed modules and enable modules anytime we want.  There are some advantages to doing so before we branch our splits in the sense that we don't have to commit, synch, merge Git-GitHub to assure they are in all environments.  So you may want to add others to the table on the next page but here we only note the Core and a configuration related contributed module called structure_sync to provide an example.
The table also shows the four split names that we set up directory homes for configuration yml files to be uniquely deposited.  Under each named split are modules you should consider installing for to be uniquely active in that environment.  Remember that the easiest way to thing about config_split is that is ADDS what you put in it TO THE BASE configuration in 'sync'.
What you need to do is the classic `lando composer require 'drupal/insertmodulename'` for each of the modules to be added to your system just like we did when we installed the config_split module itself.  But DO NOT ENABLE these modules like we previously did!  We are going to take a special approach to doing that only within the split where we want them.


<img src="../cicd/captures/configtable.png"  width="1000">
TABLE KEY:  S = Site Builder,  B = Beginning Developer,   D = Developer

Some of the customizations in the local and develop splits may be fore more advanced developers.  Drupal is built using an Object Oriented Programming language, to a large extent a Symfony framework version of PHP.  You can do stuff at an extremely low level where you are leveraging some unique strengths of how Drupal database structures are organized and OOP programming allows reuse of fundamental function calls to literally 'create' not only your own modules but even core entities below those represented in Content Type which are made up of multiple bundles.  If you are a developer familiar with OOP and PHP you might want to turn on the "D" items in the above table.  The "B" items are for beginning developer and would be something that those who want to glimpse under the hood for a gain in understanding.  The "S" items are for site builders who are mainly oriented toward using all that is core which Drupal itself and the tens of thousands of contributed modules others have already written to assemble their site;  this later group is for the normal humans like you and me to do 99% of anything we really want.




[- Next -]()
