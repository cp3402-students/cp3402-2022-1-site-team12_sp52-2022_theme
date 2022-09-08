# Theme development overview
Although WordPress has provided many beautiful theme, sometimes we need a customized theme which can fulfill our specific needs. Check out the deployment.md for local development procedure. The theme that group 12 created is named "Baizonn". The information about the theme, the theme development process and the crucial changes from its starter theme are stated below

## Theme origin

Tuan viet ho cai luoi qua

## Theme structures overview

### Style sheet
Viết về cái strcuture của sass

### inc folder
The inc folder is the place for all PHP functions of the theme. The functions.php just includes all these files. The functions are – if possible and sensible – grouped into various files. We have defined some custom functions in this folder for Baizonn Theme.

- **customizer.php**: This file defines some functions that define some setting options on the customize feature in the WordPress. In this file we added som color options for footer and header background, as well the  interative link color

- **template-function.php**: this defines functions for template file. I have added a block of code to assign body element with "has-sidebar" class when the page using default template, and "no-sidebar" class when the page using fullwidth or no-sidebar template.

- **template-tags.php**: this function is used to generate and display information dynamically. I have changed they way the post meta text.

### js folder : 
This includes the JavaScript code for the theme

-**customizer.js**: defines the js function to update the site accordingly when a user modifies settings in theme customize. We have added function to change the background color of footer, header as preview for user in theme customize.

### template-parts: 
This folder defines template structure that can be used by other template. 
- **content-single.php**: We added content-single.php that can be inheritaget by post (or single.php). We use content-single.php to define the structure of a post like what we want, and assign some css classes to some part of a page.

### template filess
Underscore defines many template file such as archive.php, comments.php, footer.php,... When user create a post or another component in the wordpress, the theme will go through these file to find a proper template. 
- **comments.php**: we made small changes on this file to for the syntax the post will display when there are some comments.
- **footer.php**: this defines the site footer template. We added social widget slot to our custom footer, modify structure of theme footer, assign css classes to the footer components.
- **functions.php**: we define php functions for this site in this script. Then we can use hooks such as add_action to add function to WordPress script. We have add functions to add new navigations to wp site and create functions to control the image size which can help our site to save resources.
- **header.php**: this defines the site header template. We added the header logo and site branding.
- **screenshot.png**: this is not a tempalte, but this is the avatar for our customized theme
- **single-nosidebar.php**: when people does not like sidebar and comments in the post, they can use this template instead. This is a customized template that remove sidebar and comments.
- **single.php**: is template for post. This template usually gets template part from content.php. However, we changed to get template part from content-single.php which is customized version of content.php for our theme post.
- **template-fullwidth.php**: when people want a fullwidth page, they switch to template instead. This is a customized template for fullwidth pages.

## Theme Features
When designing a theme, you are not limited about the what features the theme will have. We made the decision to maintain a minimalistic approach, and there is some important features of the theme.

### Full-width layout
When our users do not want to have a page or a post with side bar, we have created two layout templates including template-fullwidth.php and single-nosidebar.php . The user can easily change the template using the post editor on wp-admin.

### Right-sidebar layout.
We also maintain a template which display sidebar for pages and posts. We added some stylesheet for sidebar, comment, and widgets that can be appear on sidebar.

### Header and footer for Baizonn
We made changes on header and footer template, and add some default css styles to footer and header.

### responsive images for the WordPress site.
We have improve the default responsive images feature of WordPress in functions.php. By define some conditional state for imaage size, image tag, and post thumb nail, the WordPress can display responsive images which can save the site resources.

### Customize CMS
In dashboard of wp-admin, the user can customize some theme feature in Theme/Customize. We added new settings in Color tab where the user can change the footer and header background colors, or interative link color. We also add some JavaScripts code that can make these changes instantly on the site so the user can preview the pages.

### SASS

(Tuan oi viet ve cach minh scss cai, huhu)

## Design Decisions

Tuan hoac Han viet ho nhe  viet theo 2 cai links nay ne:
https://github.com/cp3402-students/cp3402-2022-1-site-team02/blob/main/theme.md  

https://github.com/cp3402-students/cp3402-2022-1-site-team01/blob/main/theme.md

Nói chung là chỗ này viết về font mình chọn là gì, mình muốn cái web nhìn ra sao, màu chọn là gì, các variables cho màu là gì, chọn màu từ đâu.

Cái goal khi chọn cái design này là gì. 
For example:
- keep to the colour and typography scheme. Our colour scheme is a deep red on black and our primary font is Futura. We want the site to look modern but have a mature and slightly romantic feel to it.
- Consider the target audience - we are trying to appeal to generally an older audience, so make sure text is easily readable, contrast is not too high, easy to understand and easy on the eyes.
- Consider the goals of the site - the purpose of the Jazz Townsville website is to draw users to sign up to the club and to provide information about the club and upcoming events. Our goal is to have 100 new members sign up via our online form by the end of 2022. In order for your work on the site to be effective in helping the Club, please keep the goal and purpose in mind.