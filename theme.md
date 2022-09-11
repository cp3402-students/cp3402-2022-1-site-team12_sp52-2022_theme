# Theme development overview
Although WordPress has provided many beautiful theme, sometimes we need a customized theme which can fulfill our specific needs. Check out the deployment.md for local development procedure. The theme that group 12 created is named "Baizonn". The information about the theme, the theme development process and the crucial changes from its starter theme are stated below

## Editor: 
To customize the theme, we used [Visual Studio (VS)](https://code.visualstudio.com/) to code and review. VS is easy to use and friendly with user. Besides that, VS community also support some amazing extension which can help us to connect, collab and review code together.

Our theme used lasted version of [underscores](https://underscores.me/) template. Therefore, to compile SCSS to CSS, we installed `node_modules` and type `npm run compile:css` in the terminal. To build the CSS quickly and automatically we use Visual Studio extension [Live Sass Compiler](https://marketplace.visualstudio.com/items?itemName=glenn2223.live-sass)


## Theme origin:

Baizonn theme was generated using [underscores](https://underscores.me/). To save time to custom the theme, we added _sassify!_ options in advanced Options. Sassify provided a codebase SCSS which can compile to CSS, so we can customise the theme quickly and easily to understand.

## Theme structures overview:

In initial, the main folder `baizonn` has some sub-folders `inc` `js` `languages` `sass` `template-parts` and some `php` files. These folder, sub-folder and php-files make the greate structure, which are important to edit theme. 

### Style sheet:

- **baizonn** (main folder)
  - **sass** (sub-folder)
    - **abstract** (sub-folder): This folder contains some scss files which rule some global varibles. 
    - **base** (sub-folder): This folder contains elements (sub-folder) which rule elements in site such as button, lists and links. It also contains typography which rule the decoration of text such as color, font and size.
    - **components** (sub-folder): This folder contains some sub-folder as `comments`, `content` and `navigation`. It rules the contents, which appears the our site.
    - **generic** (sub-folder): This folder rule the properties of many tags in the initial.
    - **layout** (sub-folder): This folder contain some scss files, which rule the area of each content such as `header`, `footer` and `sidebar`.
    - **plugins** (sub-folder): This folder contain the plugins SCSS file. It can be used to customize the element in the plugins.
    - **site** (sub-folder): This folder rule the site UI for all specific elements by `id` or `class`.  
    - **utilities** (sub-folder): This folder improve the User Experience. We skiped it.



### inc folder:
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

### template files:
Underscore defines many template file such as archive.php, comments.php, footer.php,... When user create a post or another component in the wordpress, the theme will go through these file to find a proper template. 
- **comments.php**: we made small changes on this file to for the syntax the post will display when there are some comments.
- **footer.php**: this defines the site footer template. We added social widget slot to our custom footer, modify structure of theme footer, assign css classes to the footer components.
- **functions.php**: we define php functions for this site in this script. Then we can use hooks such as add_action to add function to WordPress script. We have add functions to add new navigations to wp site and create functions to control the image size which can help our site to save resources.
- **header.php**: this defines the site header template. We added the header logo and site branding.
- **screenshot.png**: this is not a tempalte, but this is the avatar for our customized theme
- **single-nosidebar.php**: when people does not like sidebar and comments in the post, they can use this template instead. This is a customized template that remove sidebar and comments.
- **single.php**: is template for post. This template usually gets template part from content.php. However, we changed to get template part from content-single.php which is customized version of content.php for our theme post.
- **template-fullwidth.php**: when people want a fullwidth page, they switch to template instead. This is a customized template for fullwidth pages.

## Theme Features:
When designing a theme, you are not limited about the what features the theme will have. We made the decision to maintain a minimalistic approach, and there is some important features of the theme.

### Full-width layout:
When our users do not want to have a page or a post with side bar, we have created two layout templates including template-fullwidth.php and single-nosidebar.php . The user can easily change the template using the post editor on wp-admin.

### Right-sidebar layout:
We also maintain a template which display sidebar for pages and posts. We added some stylesheet for sidebar, comment, and widgets that can be appear on sidebar.

### Header and footer for Baizonn:
We made changes on header and footer template, and add some default css styles to footer and header.

### Responsive images for the WordPress site:
We have improve the default responsive images feature of WordPress in functions.php. By define some conditional state for imaage size, image tag, and post thumb nail, the WordPress can display responsive images which can save the site resources.

### Customize CMS:
In dashboard of wp-admin, the user can customize some theme feature in Theme/Customize. We added new settings in Color tab where the user can change the footer and header background colors, or interative link color. We also add some JavaScripts code that can make these changes instantly on the site so the user can preview the pages.

### SASS:

**SASS** (syntactically awesome style sheets) is a preprocessor scripting language that is interpreted or compiled into Cascading Style Sheets (CSS). SASS help our save time because we can store things like colors, font stacks, or any CSS value, which we believe we'll want to reuse. Sass uses the `$` symbol to make something a variable. For example, when we need to reuse the border color, we just declare `$color__border: #eee;` in `_colors.scss` file and `border-bottom: 1px solid $color__border;` in `_navigation.scss` file.

## Design Decisions:

In design decisions, our team will list down important factors in our own custom theme that make significant changes on our website content. Hence, the factors will included location and decision of their modification on. 

Structure:
  Query
   Our theme applied grid composition under structure for the query content.
   To modify block query content in flex position, we add elements in _structure.scss:
    $query__small: 600px;
    $query__medium: 900px;

Site:
  In _site.scss, we modify some specific content in order to create a clear look for user such as header, footer and form. These are the basics yet important to most web content. It's our aim to allow users to have a clear view in our website even if it's only basic details.
  
  Header
   In _header.scss, we ensure that the logo will always be on the left side. Meanwhile, menu bar will stand on the right to make more space for our content. Hence, the modify will become user-friendly and easy to approach:
   .menu-main-menu-container {
    float: right;
  }
  
  Footer
    All contents in footer will be separate in order under column of 3: logo - menu - social contact. This modify is added on _footer.scss:
    .site-footer > nav {
      width:25%;
      ul {
          list-style-type: none;
          margin:0;
          padding:0;
      }
  
Typographhy:
  Colour
   Considering the main colour of the logo is blue and dark green. We follow these basic colours to keep the content being simmplified and easy to read. Hence, the contrast is not too high between these colour patterns.
   These variables of colours are being modified in _color.scss:
      $color__background-button
      $color__text-screen
      $color__link-hover
      $color__headings-primary
  
  Font
    For Baizonn website, we apply font Lekton from Google Fonts are our main fonts for the whole content. This font tend to be user-friendly and fairly look from users experience.
    
    These variables of fonts are being modified in _typography.scss:
        $font__main
        $font__code
        $font__pre
        $font__sans


