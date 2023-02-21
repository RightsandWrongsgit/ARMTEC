# Starting the Project on Platform.sh 

## Short-cut approach:

<sub><sup>NOTE: You may want to review the Regular Approach section before you run the "Short-cut approach" so you know what it is doing behind the scenes.  And if you are going to do other projects or migrate an existing project to Platform.sh having this process understanding is helpful.</sup></sub>


<sub><sup>A) Go over to this repository on GitHub and you will find the Platform.sh template for Drupal 9 `https://github.com/platformsh-templates/drupal9</sup></sub>
	
<sub><sup>B) Click on the button at the top of the repository that looks like this -></sup></sub><img src="../cicd/captures/deployonplatformbutton.png"  width="200" height="40">	

<sub><sup>C) Follow the on-line instructions to bring up the hosted Drupal site</sup></sub>	
	
<sub><sup>D) Back to the Github template site and follow the [Drupal: using Lando section](https://github.com/platformsh-templates/drupal9#:~:text=Drupal%3A using Lando-,Note,-%3A)</sup></sub>
	
<sub><sup>E) In the "Migrate" section in the Github template for a totally new site follow the [Getting started instructions](https://github.com/platformsh-templates/drupal9#getting-started-1)</sup></sub>
	

## Regular approach: 

You should have gone to Platform.sh, signed up for an account and installed their command line interface (CLI) tool. If not, jump back to the end of the Prerequisites and follow those instructions.

A) From the Platform.sh CLI enter: `platform create`

This will prompt you for-→ 
				– a project title
				– your hosting region (e.g. us-2.platform.sh)		
				– the plan size (use 'Development' until you want to go live)
				– Number of Environments (default 3)
				– Amount of Storage (default 5 Gig)
				– Confirm "Y" to continue

B) A 'Project ID' will be assigned and shown.  Copy and save it somewhere safe.

		If you forgot and missed it, just type this –> `platform project:list`

C) At the CLI enter:
   `platform environment:init <Project ID> -e main https://github.com/platformsh-templates/drupal9`

	(NOTE: you can replace 'drupal9' with whatever other template version is available from this source)

This is now building your project on the platform.sh host.  <sub><sup>(What is going on in this step is that the system is looking at the platform.app.yaml file in that template's project root and the routes.yaml and services.yaml file that that template has in a next level down subdirectory called .platform to create a host system environment your project is running in.  Eventually you might edit these files to tweak your environment to improve performance.  But to start out the template being pulled has all you need.)</sup></sub>

D) At the CLI, now enter:   `platform url -p <Project ID>`

A new browser window will open where you see an install screen for the Drupal9 application. Should look something like this:

<img src="../cicd/captures/drupalinstall1.png"  width="450">

<sub><sup>From that Drupal screen, setting up your Drupal site is pretty much like all the tutorials out there on Drupal. And, it is pretty much follow the prompts and answer the questions.  The exception is that the "Set up database" step just sort of flies by automatically because the Platform.sh container recipes are doing it for you.</sup></sub>

