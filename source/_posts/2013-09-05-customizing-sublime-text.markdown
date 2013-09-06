---
layout: post
title: "Customizing Sublime Text"
date: 2013-09-05 15:47
comments: true
categories: Technical
author: Cheri Allen
---

###What Sublime Text is:
***
Sublime Text is a cross platform text editor, excellent for code, markup, and prose. It's free to try and fun to customize. You can customize it in several ways: the color scheme, the UI aspects, key bindings, and a variety of preferences. 
 <!-- more -->
###How to get it:
***
- Download from [http://www.sublimetext.com/](http://www.sublimetext.com/).
- [Installation instructions vary](http://docs.sublimetext.info/en/latest/getting_started/install.html) according to your OS.
- You can try out the full version for as long as you'd like before you buy, but it's "nagware"- will remind you often to purchase a license. 
- Unlimited commercial licenses cost $70 currently. Purchase one [here](https://www.sublimetext.com/buy).  
- When you enter a purchased license key (under Help -> Enter Key), no more nagging!


###Cool customization:
***
Get [Package Control](https://sublime.wbond.net/) to manage plugins. It makes adding new themes, color schemes, and more super easy.  
 
  1. Install Package Control via the [instructions](https://sublime.wbond.net/installation).
  2. In Sublime, press Cmd+Shift+P and type "install package". Hit enter or click on the suggested choice, "Package Control: Install Package".
  3. Oh wow, that's all the packages available, sorted and searchable by name. That's not actually super helpful if you don't know what you're looking for. I'd start by [browsing](https://sublime.wbond.net/browse) some popular packages, or [searching](https://sublime.wbond.net/search) for something specific, on the Package Control website. There you can see full descriptions, links to Github repos, and more.
  4. Once you find what you want, do Cmd+Shift+P and "install package" again, then search for the one you want.
  5. When you select a package, it'll download and install for you- easy! 

####Appearance 
Color schemes effect the text area: font colors and syntax highlighting. Sublime comes loaded with a few schemes, you can make your own, you can download and install them manually, or you can use Package Control to find and install them.

  1. View available schemes and change your active one: SublimeText2 -> Preferences -> Color Schemes
  2. Creating your own scheme is complicated and outside the scope of this post. 
  3. Download and install a scheme manually: 
    - Find a cool scheme [here](http://colorsublime.com/) or elsewhere. 
    - Download one you like. You should get a .tmTheme file. 
    - Open SublimeText2 -> Preferences -> Browse Packages... 
    - Paste your downloaded .tmTheme file into the "Color Scheme - Default" folder.
    - The new scheme will now appear in SublimeText2 -> Preferences -> Color Schemes -> Color Scheme- Default menu. 
  4. Use Package Control to install a scheme:
    - [Search for color schemes](https://sublime.wbond.net/search/color%20scheme) on the Package Control site. 
    - View the available ones, checkout screenshots, and pick some favorites.
    - Follow the Package Control instructions above to find and install the ones you like into your Sublime Text. 
    - See available schemes and change the active one in the SublimeText2 -> Preferences -> Color Schemes menu.

Themes generally effect the user interface of Sublime, in addition to the appearance, though it's not a hard and fast definition. They may change menu configurations, what information is desplayed around the text area, or add features. The [Soda Theme](https://github.com/buymeasoda/soda-theme/) (both light and dark versions) are very popular choices. You can install themes in much the same ways as color schemes. 

  1. View your active theme:
    - Open SublimeText2 -> Preferences -> Default
    - Find the line that says "theme": "SuperBasicTheme.sublime-theme"
    - Whatever SuperBasicTheme actually says is the theme that is in effect currently.
  2. Creating your own theme is complicated and outside the scope of this post. 
  3. Download and install a theme manually: 
    - Find a cool theme on [Github](https://github.com/search?q=sublime+theme&nwo=buymeasoda%2Fsoda-theme&search_target=global&ref=cmdform) or elsewhere. 
    - Download one you like. You should get a directory (unzip if it comes as a zipped file). 
    - Open SublimeText2 -> Preferences -> Browse Packages... 
    - Paste your downloaded directory into the "Packages" folder.
    - To activate new theme, you'll need to add/edit a line in your SublimeText2 -> Preferences -> User file. It will be "theme": "CoolNewTheme.sublime-theme" where CoolNewTheme is replaced with the actual name of your cool new theme. There should be activation instructions from wherever you download from that will give you the correct name.
  4. Use Package Control to install a scheme:
    - [Search for themes](https://sublime.wbond.net/search/theme) on the Package Control site. 
    - View the available ones, check out screenshots, and pick a keeper.
    - Follow the Package Control instructions at the beginning of this section to find and install the ones you like into your Sublime Text. 
    - To activate new theme, you'll need to add/edit a line in your SublimeText2 -> Preferences -> User file. It will be "theme": "CoolNewTheme.sublime-theme" where CoolNewTheme is replaced with the actual name of your cool new theme. There should be activation instructions from wherever you download from that will give you the correct name. 

####Settings 
There are two Settings files: Default (global) and User. Settings in the User file will override the Defaults if they conflict. Normally, people edit the User one and leave the Default as is, as a reference for things that can be changed. Your color scheme and theme will be listed in the Settings files, but there are other ways to change them than through these files (see below). 

Open SublimeText2 -> Preferences -> [Defaut or User]
 
Some popular preferences to add or change are: 

  - "save_on_focus_lost": true
  Automatically saves the file you're editing when you leave it.
  - "wordWrap": true
  Word wrap set to always be on. **
  - "highlight_line": true
  Highlights the line your cursor is in
  - "line_padding_bottom": 1
  Gives each line a bit of padding underneath it, making for easier to read text

####Key Bindings
There are also two Key Binding files: Defaut (global) and User. Again, the User file will override the Default, so it's recommended that you leave the Default as a reference and only edit the User. As you add new values to the User file, you'll see the keyboard hints in the dropdown menu reflect your changes. Cool! 


###Resources:
[Unofficial Sublime Documentation](http://docs.sublimetext.info/en/latest/)<br>
[Great list of resources](http://thecrumb.com/wiki/sublime)<br>
[Info about settings](http://www.sublimetext.com/docs/2/settings.html)