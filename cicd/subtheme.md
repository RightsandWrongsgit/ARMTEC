
# Appendix:
## SubTheme Set Up For Your Site 

#### 1. Create a sub-theme
Under the themes subdirectory add a an additional subdirectory for `name-of-your-sub-theme`. Then under this new subdirectory add your new themes `.info.yml` and `.libraries.yml` files.  It should look basically like this...

`themes \`<br>
	`+ name-of-your-sub-theme \`<br>
	`+ name-of-your-sub-theme.info.yml`<br> 
	`+ name-of-your-sub-theme.libraries.yml`<br>

#### 2. ".info.yml" code
The .info file contains the following code.

`Name: Name-of-your-subtheme`<br> 
`type: theme`<br> 
`description: This is a sub theme of ARMTEC`<br> 
`# Defines the base theme`<br> 
`base theme: armtec`<br> 
`# Defines libraries group in which we can add css/js.`<br> 
`core: 8.x`<br> 
`core_version_requirement: ^8 || ^9`<br> 
`libraries:`<br>  
`- name-of-your-subtheme/global-styling`<br> 
`# Regions`<br> 
`regions:`<br>  
`identity: Site Identity`<br> 
`header: Navigation`<br> 
`featured: Featured`<br> 
`breadcrumb: Breadcrumb`<br> 
`sidebar_first: 'Sidebar first'`<br> 
`content: Content`<br> 
`sidebar_second: 'Sidebar second'`<br> 
`footer_top: 'Footer Top'`<br> 
`footer_bottom  'Footer Bottom'`<br> 

#### 3. ".libraries.yml" code
Include name-of-your-sub-theme.libraries.yml file to add css/js in the global-style group (this is defined above, in the libraries key). Use the following code:
`global-styling:`<br> 
  `version: VERSION`<br> 
    `dependencies:`<br>  
	`- core/jquery`<br> 
  `css:`<br> 
     `base:`<br>  
  `css/style.css:{}`<br> 
  `js:`<br> 
    `js/prod/script.js:{}`<br> 

#### 4. Enable your sub-theme
A. Go to "Appearance" (/admin/appearance) on the main Administration menu of your site.<br>
B. Your sub-theme should be listed under the Uninstalled Themes section<br> 
<sup><sub>If it’s not shown, check that you’ve deployed code to correct branch (dev code for dev site...etc) and cleared the site cache.</sub></sup><br> 
C. Click the Install and set as default option to enable it as the main theme for your site.<br> 



