---
layout: post
title: "Customizing Your Octopress Blog"
date: 2015-06-12 16:51:24 -0400
comments: true
categories: ["Flatiron School", "Octopress", "Blog", "Tutorial"]
---
##Installing a New Theme
When Octopress is first installed, the theme is rather bland.  Luckily, it isn't difficult to change this.  There are a decent amount of Octopress themes available, allowing for customization of the overall feel of your blog.  To find an Octopress theme, check out imathis's <a href="https://github.com/imathis/octopress/wiki/3rd-Party-Octopress-Themes" target = _blank>compilation</a>.  Once you pick out a theme, follow the theme's documentation in order to install it.  For the majority of themes, installation will follow the following template: 
``` sh
cd octopress
git submodule add git://github.com/CREATORS-USERNAME/THEME-NAME.git .themes/THEME-NAME
rake install['THEME-NAME']
rake generate
```
The GitHub url is the HTTPS clone URL, which can be found on the right hand side of GitHub.

##Adding Custom CSS 
One of the best ways to set your blog apart is to add custom CSS.  Navigate to your `octopress` folder. Once there, `ls` should reveal a `sass` folder.  Navigate into that folder, and then into the `custom` folder.  Next, find `_styles.css`.  Open this file in your text editor.  This is where you can put your custom CSS.  A basic CSS tutorial can be found <a href="http://www.w3schools.com/css/" target = _blank>here</a>.  If you're having trouble figuring out how to style a particular element, many browsers implement Inspect Element, which is great for determining the html used for that particular element. 

##Changing the Default Colors
You can take your styling further by changing the default colors used by the theme.  This is done in a similar manner as adding custom CSS.  In the same folder where `_styles.css` was found (`/octopress/sass/custom/`), you will find `_colors.css`.  Open this file using your text editor.  The file should be documented, explaining where to change the colors.  Finding the perfect color is easy with <a href="http://www.w3schools.com/tags/ref_colorpicker.asp" target = _blank>w3schools HTML Color Picker</a>.

##Setting Up Layouts
Layouts are basically templates for your posts.  This makes it easy for you to have different designs, without having to manually set them up each time.  To add or modify layouts, navigate to your `octopress` folder.  Next, find and navigate to the `source` folder.  There you should find a `_layouts` folder with some predefined layouts.  You can modify any of the existing, or create your own by adding the html file to the `_layouts` folder.  Start off each layout with: 
``` html
---
layout: LAYOUT_NAME
---
```
From there, add your custom code.  You can use the previously made layouts as a reference. 

##Setting a Custom Favicon 
Changing the favicon is simple. Go back to the `source` folder (`/octopress/source/`).  There you will see `favicon.ico` or a similarly named .ico file.  Replace this file with your favicon, but make sure to keep the name of the file the same.  If you don't have a favicon yet, you can create one using a <a href="http://www.favicon.cc/" target=_blank>favicon generator</a>, make one from an image using a <a href="http://tools.dynamicdrive.com/favicon/" target=_blank>converter</a>, or find one using a <a href="http://www.freefavicon.com/freefavicons/objects/" target=_blank>favicon library</a>. 