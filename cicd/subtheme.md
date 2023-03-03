
# Appendix:
## SubTheme Set Up For Your Site 

#### 1. Create a sub-theme
Under the themes subdirectory add a an additional subdirectory for `name-of-your-sub-theme`. Then under this new subdirectory add your new themes `.info.yml` and `.libraries.yml` files.  It should look basically like this...

    themes \
         + name-of-your-sub-theme \
            + name-of-your-sub-theme.info.yml
            + name-of-your-sub-theme.libraries.yml

#### 2. ".info.yml" code
The .info file contains the following code.

    name: Name-of-your-subtheme 
    type: theme 
    description: This is a sub theme of Stable 
    # Defines the base theme 
    base theme: stable 
    # Defines libraries group in which we can add css/js. 
    core_version_requirement: ^8 || ^9 || ^10 
    libraries:  
      - name-of-your-subtheme/global-styling
    # Regions
    regions: 
      identity: Site Identity 
      header: Navigation 
      featured: Featured 
      breadcrumb: Breadcrumb 
      sidebar_first: 'Sidebar first' 
      content: Content
      sidebar_second: 'Sidebar second' 
      footer_top: 'Footer Top' 
      footer_bottom  'Footer Bottom'

#### 3. ".libraries.yml" code
Include `name-of-your-sub-theme.libraries.yml` file to add css/js in the global-style group. Use the following code...

    global-styling: 
      version: VERSION
        dependencies: 
	  - core/jquery 
      css: 
        base:  
      css/style.css:{}
      js: 
        js/prod/script.js:{} 

#### 4. Enable your sub-theme
A. Go to "Appearance" (/admin/appearance) on the main Administration menu of your site.<br>
B. Your sub-theme should be listed under the Uninstalled Themes section<br> 
<sup><sub>If it’s not shown, check that you’ve deployed code to correct branch (dev code for dev site...etc) and cleared the site cache.</sub></sup><br> 
C. Click the Install and set as default option to enable it as the main theme for your site.<br> 


[More on Subtheming](https://www.drupal.org/node/2165673)
