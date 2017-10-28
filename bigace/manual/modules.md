# Modules

In the modul administration, you see all modules, which are installed for your community, with their names and a short description.

Modules can be de-/activated by hitting the State icon. If you deactivate a modul, it is no longer choosable in the Menu administration, but pages that already use this modul, will still work as expected. You might use this function to disallow further usage of a modul (like the Guestbook that might only be used once within your website).

{{:bigace:manual:module-admin.jpg|Module administration}}

Since [BIGACE 2.6](http://www.bigace.de/BIGACE-2.6.html) you can further edit existing modules directly in the browser by clicking their name.

You can even create new modules, by entering a new name into the text field and saving with the disk icon.

## What is a module?

Modules are the part of your pages, that render the content area. This will be most often the "Display Content" Module, that simply renders the pages content. 

But modules might also be any thinkable PHP script, that replaces or extends the pages content to make your website more dynamic and interactive.

Each modul can be assigned to as many menus as you want to. Some of them use their own Admin panel plugin, which will be displayed within the Admin Menu **Extension** (Guestbook for example comes shipped with its own Admin Plugin).
Others might need to be configured per page, then you see a "Configure Modul" link when displaying the page (you might need to assign a [Group permission](manual/grouppermission) to your user before you see the link).

## Display Modules in Pages

Many user asked in the forum how to display a module, when they first installed Bigace. This article is a quick How-To, which addresses the question "How to install and display a module in my website?".

### Download

First step is to download a module from the [Plugin repository](http://www.bigace.de/plugins/).

### Install

New modules can be installed with the [Extension Administration](manual/updates).

### Assign module to page

Change to the [menu administration](manual/menuattributes) and edit the page where the module should appear.

Now choose the preferred module from the "module drop-down".

{{:bigace:manual:module-in-menu.jpg|Choose module for your page}}

After you saved the page, please reload it in your browser. 

### Configure module

If the module doesn't need any configuration or they are optional, the module will display directly after a page reload. 

Some modules need configurations before they will work. In that case a link will appear, which opens a Pop-Up with configuration settings:

{{:bigace:manual:module-config.jpg|Module configurations}}

After you configured and saved, you can reload the page and enjoy the module :D

