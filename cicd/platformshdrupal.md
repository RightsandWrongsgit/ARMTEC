
Regular approach: Starting the Project on Platform.sh - 

Alternatively, after you can go to Platform.sh & signing up for an account, install their command line tool with the following command and then do the sequence of steps noted.

A) Install the Platform.sh command line tool: 


B) On the Platform.sh CLI enter: 

This will prompt you for-→   – a project title
	   – your hosting region (e.g. us-2.platform.sh)		
– the plan size (use 'Development' until you want to go live)
– Number of Environments (default 3)
– Amount of Storage (default 5 Gig)
– Confirm "Y" to continue

C) A 'Project ID' will be assigned and shown.  Copy and save it somewhere safe.

If you forgot and missed it, just type this –>

D) At the CLI enter:


	(NOTE: you can replace 'drupal9' with whatever other version or template is at that Github template source)

This is now building your project on the platform.sh host.  (What is going on in this step is that the system is looking at the platform.app.yaml file in that template's project root and the routes.yaml and services.yaml file that that template has in a next level down subdirectory called .platform to create a host system environment your project is running in.  Eventually you might edit these files to tweak your environment to improve performance.  But to start out the template being pulled has all you need.)

E) At the CLI, now enter:

A new browser window will open where you see an install screen for the Drupal9 application. Should look something like this:

<img src="ARMTEC/cicd/captures/drupalinstall1.png"  width="600" height="300">
