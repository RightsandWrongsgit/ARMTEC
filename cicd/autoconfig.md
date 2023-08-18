
# Automate Configuration


The primary intent of the Config Suite module plays into our workflow plans too.  We have shown a number of times already how you should expect to do a 'lando drush cex' from your local version of your site to get the changes you have done during development into yml files and then commit/stage/sync them in VSCode to get those into the platform.sh hosted branch you are working from.  If you think about having to 'cex and cim' all the time, you know you will be doing it way to much.  The author of the Config Suite module [points out in a video](https://www.youtube.com/watch?v=02IJGgGPBAw&t=112s) that he got into computing because the logic is that the computer should automate stuff you do all the time.  After you install and enable the Config Suite module and go look for it in the Administration menu by your Configuration Synchronization or Configuration Split options, you will see these simple options:

<img src="../cicd/captures/UUID2.png"  width="450">


Cross-checking our Config Split table, we see that Config Suite is one we will set differently by split. We very much want to automatically export our configuration in the ‘local’ and ‘develop’ environments. So every time we do any updates locally and commit/stage/sync them to hosted ‘develop’ the two are automatically updated. When we merge ‘develop’ into ‘staged’, we are also happy to have ‘staged’ automatically import any configuration files that came along and get them into the active database for that environment; but not so as far as exporting the updated configuration to files. I think we want to use the ‘staged’ testing environment as one where we first run our tests, review them, and make our export a manual step of that workflow approved release; so automatic import ‘on’ but NOT automatic export. Our Config Split table shows automatic import and export ‘on’ in the ‘main’ or production split but we might debate that depending on our workflow preference protocols. You definitely want automatic ‘export’ on in ‘main’ because that environment is what we consider the ultimate source of truth. When we need to go back to the starting point and grab a fresh start, our aim is to use ‘main’ and start branching. So main should have the live environment’s configuration available in yml files and having them automatically exported makes a ton of sense. Since we are doing a manual ‘export’ of ‘staged’ after testing, it should be ok for that to automatically be imported by ‘main’ as we merge ‘staged’ into it and the table is shown that way. However, if you want an additional safety net, you could make ‘main’ automatic export but not import.

A video on the Config Suite module!

- Next -
