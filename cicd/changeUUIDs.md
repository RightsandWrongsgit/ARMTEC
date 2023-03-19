
# Appendix: Changing the UUIDs
## So your new site can use the 'base' configuration you cloned

The basic approach for dealing with UUIDs is shown as the use of the Config Suite module.  That module includes the php code to basically ignore the UUIDs.  If that module does not maintain its Drupal version updates or you simply prefer to align rather than ignore the UUIDs, here are how you can approach it.

### REMOVE UUIDs
To manually remove all of the UUID and default_config_hash lines from your config files so that they don't conflict with those of a new site this can be done quite easily on the command line like so: 

<font color=red>For Linux</font><br>
`find /path/to/PROFILE_NAME/config/sync/ -type f -exec sed -i -e '/^uuid: /d' {} \;`<br>
`find /path/to/PROFILE_NAME/config/sync/ -type f -exec sed -i -e '/_core:/,+1d' {} \;`

<font color=red>For Mac OSX</font><br>
`find /path/to/PROFILE_NAME/config/sync/ -type f -exec sed -i '' '/^uuid: /d' {} \;`<br>
`find /path/to/PROFILE_NAME/config/sync/ -type f -exec sed -i '' '/_core:/{N;d;}' {} \;`

<font color=yellow size=small>* NOTE: may need to modify the path to where your own config files are located; e.g. /config/sync</font>

Give some thought to stepping up to a batch process with automatic backup's as the best way to go at this.  Rather than specifying your path like above, you actually go into the involved subdirectory and run these commands.  I like this option not only for the extra safety of having the backup (bak) files but because those same files can actually be used as an edit-to-new opportunity.

### REMOVE LOTS OF UUID's FROM MANY 'YML' FILES
Stripping the uuid line out via a manual process which can be a pain because there can be a lot of files involved. You can use sed to delete lines in a text file that contain a specific string.  Translate that into the fact that yaml or yml files are essentially text files and that the "UUID: lkafjdl;fjaldjflkajdlkfjsalkjf" is on its own line where you can just find the key "UUID:" part of the key:value pair and delete the whole line. 

[To automate this](https://gist.github.com/DavMorr/c3a5b73820778e2fb213cdd9d614f27a), run the following sed command in the directory containing the yml/yaml files:<br>
`sed -i.bak '/^uuid: /d' ./*`

The `i.bak` argument will create a backup of the affected file. This is 'sweet' because when satisfied with the results, you can safely get rid of the .bak files with: 
`rm *.bak`

Additional references from a...<br>
- [Wizard](https://drupalcommands.com/console/config/config-export/)<br>
- [Czar](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/sed.1.html)<br>
- [Maes·tro](https://stackoverflow.com/questions/5410757/delete-lines-in-a-text-file-that-contain-a-specific-string)


### GET AND SET UUIDs
What I mean by the edit-to-new opportunity is that instead of eliminating UUIDs you can align them with some manual effort.  You could do this just once, say for the system.site UUID as shown here with the drush command approach:

`drush cget system.site uuid` (gets uuid)<br> 
`drush cset system.site uuid` (sets uuid) 

<font color=yellow size=small>NOTE:  If you get "The import failed due to the following reasons: Entities exist of type <em class="placeholder">Shortcut link</em> and <em c lass="placeholder">Shortcut set</em> <em class="placeholder">Default</em>."</font>  <font size=small>These entities need to be deleted before importing; try:</font> `drush -y entity:delete shortcut_set` before your `drush -y cim`

More here - https://drupal.stackexchange.com/questions/150481/how-can-i-import-the-configuration-on-a-different-site
Fuller article outlining process in a context. 
https://enzo.weknowinc.com/articles/2014/08/27/understanding-configuration-management-in-drupal-8


Alternatively, you could combine approaches where you run the batch approach, do the drush cget process to get the UUID from the new site you are going to import into, copy that UUID into your clipboard, and then go replace the UUIDs in all those bak files.  After you have the bak files updated, remove there no UUID counter-parts and rename the bak files to their original names.  Now all your UUID containing files will contain the new sites values.  And you can do this in not just the /config/sync subdirectory but also the /config/main, /config/staged, /config/develop, and /config/local subdirectories if any of them contain files with UUIDs.  If you are just now setting up a newly cloned site, you probably won't have any or many.  But if you are doing this to a site you have installed a bunch of stuff and configured your site with lots of updates, you might generate several bak files to manually edit in each of these subdirectories. 

[Article on editing UUIDs](https://www.hashbangcode.com/article/drupal-8-configuration-originates-different-site)




[- Next -]
