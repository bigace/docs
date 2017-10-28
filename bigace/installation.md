# Installation Guide

This Guide is written for all Users who want to install BIGACE on their Webhosts.

You should have a copy of the latest version, otherwise [download BIGACE](http://www.bigace.de/download.html) first.

*For the rest of this Guide, we assume you have installed BIGACE at http:*www.example.com/ in the root directory. Wherever a URL is given in this Guide, replace this example Domain with your actual domain!//

**NOTE:** We have a [screencast](http://www.bigace.de/Screencast-Install-BIGACE-on-your-Webhost.html) that shows the basic steps for installing BIGACE on your webserver.

## Extract the Archive

After downloading the latest Package **bigace_2.x.zip** from Sourceforge, you have to extract the archive to a new folder:

{{bigace:installation:install_files.png|Extracted Files}}

Don't worry if the version you have is different to the one in this guide. While this guide was written using the version 2.4, the same steps will work with newer versions. Also don't worry if some of the file names are a little different in the screen shots. We update the file names in the text more often than we update the screen shots.

## Upload files

Use FTP or a file manager to upload the extracted files **bigace_install_2.x.zip** and **install.php** with to your Webhost:

{{bigace:installation:upload.png|Upload files}}

## Pre-Installation (File extraction)

Now open the page in your Browser: http://www.example.com/install.php.

If you see this picture, your Webserver does not have built-in GZlib support, read [Troubleshooting: Manual extraction and File upload](#manual_extraction_and_file_upload).

{{bigace:installation:no_gzlib.png|No GZ-Lib}}

If you see this screen, you can start extraction:

{{bigace:installation:install-bigace-pre-install.png|Pre-Installer}}

*The path is different at your Host, this is no problem!*

Hit the "**Install**" Button and wait until all files are extracted (this might take some time, be patient). The following screen tells you that extraction was successful:

{{bigace:installation:install-bigace-extracted.png|Extracted Files}}

After extracting the files, read the next chapter [Check your Files](#check_your_files) BEFORE you follow the "**Start Installation**" link in the result window.

## Check your Files

To make sure everything is fine, have a look at your Website with FTP, the extracted structure should look like this:

{{bigace:installation:check_structure.png|Check structure}}

__**Clean-Up:**__

Delete the previously uploaded files:


*  **bigace_install_2.x.zip**

*  **install.php**

Don't skip this, those files could cause trouble if you keep them!

## Install The Database and Website

After you've checked your file structure, click the link in the result page or enter http://www.example.com/install.php in your Browser, you see:

### Screen 1 - Language and Introduction

{{bigace:installation:install_bigace_1.png|}}

Choose your language from the Drop-Down box and hit "Start Installation".






### Screen 3 - Check environment

{{bigace:installation:install-bigace-checkup.png|Checking your environment}}

A checkup will be performed, to see if your environment matches the requirements to run BIGACE. The more red dots you see displayed, the higher the risk that something will be broken (see [Troubleshooting: Checkup shows problems](#checkup_shows_problems)).

Hit the "**Next**" Button, to start Core installation.

 1.  *This screenshot was taken on a experimental development system, on your host the lower red dots should be green!*
 2.  *Whatever comes up here, try to install before you give up. Post your problem in the Forum, we will help you, that's for sure!*



### Screen 4 - Database and Core

In the next Screen, you have to submit your database connection values. BIGACE then tries to connect and install all its tables. 

{{bigace:installation:install-bigace-core.png|}}

Here you can choose some basic settings which you can also change at runtime (i.e. after you've gotten your web site up and running).

IMPORTANT: If you do not understand the meaning of the **Apache MOD-Rewrite** and **Apache .htaccess Feature** leave as is! You might not be able to access your Website if you change the setting without being supported from your Webserver. Read [500 Internal Server error](#internal_server_error) for further information!

*FIXME add infos about the input fields*

### Screen 5 - Core installed

{{bigace:installation:install-bigace-core-success.png|Configured Core System}}

This screen is only for information purposes, skip by hitting "Next".




### Screen 6 - Create Community Website

Now you need to create the first Community. Remember that each web site you run under BIGACE is its own community.

{{bigace:installation:install-bigace-community.png|Install Community}}

For every input field and select box, you get additional infos - as seen on the screenshot.

The following values have to be submitted:


*  **Community Domain** - the Domain where your website will be running. The pre-calculated value should work in most cases. If you are going to change your domain later (for example when installing on a test domain), you can simply add an alias via Administration. Do NOT add a path here, this is ONLY the qualified domain name!

*  **Username** - the user name for your Administrator account 

*  **Email Address** - the email address of your administrator

*  **Password** - password for your administrator account

*  **Password [re-enter]** - verify the above entered password

*  **Mail Server** - if left empty, the PHP default settings will be used (works on most shared-hosting environments)

*  **Default language** - the default language for your Community, can be changed later.

*  **Statistics** - whether BIGACE should log internal statistics.

### Screen 7 - Community success

{{bigace:installation:install-bigace-community-success.png|Community created}}

If everything was OK, you should see this last informational screen. Hit the "**Next**" Button to see your new Website live.


# ABOUT MULTIPLE DOMAINS AND SITES

If you plan on building and managing multiple web sites, you can do this all under one BIGACE installation. This assumes that all your content for these sites is hosted on the same server. 

Each unique web site must be set up as its own BIGACE Community. If you have registered multiple domains for the same web site, you will need to list these in BIGACE as Aliases. For example:

WEB SITE 1 - My Personal Web Site
This web site is served by 3 domains: 
   johnsmith.com, johnsmith.org, and johnsmith.name.
In BIGACE you choose one of these (it doesn't matter which one) as the Community Domain and then set the other domains as aliases. 

WEB SITE 2 - The Acme Business Web Site
This web site is served under 2 domains:
   acme.com and acme.net.
You set this Community up the same way.

Under BIGACE, these two sites form 2 Communities, even though there are 5 domains in use. This assumes that all of these domains are hosted in the same location. 

One last thing: To make this work, you need to set the Domain Pointing at your web host so all the domains for both web sites are pointing at the BIGACE install directory.

# Troubleshooting

If you have problems with the installation, post in the [Installation Help Forum](http://forum.bigace.de/index.php/board,2.0.html).

If you have more information, hints or any advice that might help other Users with the installation, edit this Wiki page or give us the info in our Forum and we will add it here!

## Safe Mode turned on

Uhoh, this is not good... BIGACE has workarounds for this problem, but Safe Mode is not the best solution to solve permission questions on shared-hosting environments! Talk to a qualified Administrator and read [Safe Mode](installation/safe_mode) in between.

## Checkup shows problems

If you encounter red dots during the installation checkup, don't stop it! You might have a problem with one or more features, but most often it is just a configuration that doesn't match the BIGACE idea of a well-configured PHP environment.

These are some well-known problems:


*  Missing "Image Support (including GIF and JPEG)" is no real problem, but the built-in "Thumbnail" function will not work. 

*  Same with the "b2evo" addon, which is used as a built-in captcha solution. It does not work without Image functions.

You should really contact your Web Host about this because PHP without Image support is not up-to-date.


## Manual extraction and File upload

If your PHP version has no GZlib Support, you have to extract and upload the content from the file **bigace_install_2.x.zip** manually.
 
 1.  Extract the archive **bigace_install_2.x.zip**
 2.  Upload all extracted files to your Webhost
 3.  Go on with [Check your Files](#check_your_files) and following

And by the way, you should contact your Web Hosting company and ask for GZlib support!

## Extraction failed with errors

If errors occur during extraction, try to fix them (most often wrong file/folder permissions) and reload the page. The script will try to extract again and give you qualified feedback. You can repeat this, until no more error messages are shown.

Make sure the script can write to the root folder (easiest is to set 777 permissions).


## 500 Internal Server Error

If you installed with activated URL Rewriting (mod_rewrite) you might get a 500 error, saying:

	
	Internal Server Error
	The server encountered an internal error or misconfiguration and was unable to complete your request.
	...


This is often caused by Webserver settings:

 1.  **AllowOverride** for **.htaccess** is turned off
 2.  the **mod_rewrite** module is not loaded in Apache

Please read [URL Rewriting](administration/urlrewriting) carefully.

