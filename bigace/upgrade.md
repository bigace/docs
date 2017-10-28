# Upgrading BIGACE

Upgrading your CMS to the next version is always a good idea :-)

Please note: If you are going to perform an upgrade before 2.5 (e.g. from 2.3 to 2.4), use the [old upgrade guide](upgrade/old).

The following information match the core upgrades from 2.5 on.

Special instructions for single versions can be found here:

*  [bigace:upgrade:24](upgrade/24)

*  [bigace:upgrade:25](upgrade/25)

Follow the given order (see below), otherwise your CMS might be broken.

# Introduction

Always update from one to another ... you should never ever skip any available update. This might result in critical problems with the Database or even in lost data!

For example: Do NOT update from 2.1 to 2.4, but from 2.1 => 2.2 => 2.3 => 2.4.

Read the instructions for each update exactly. There might be tasks to be executed manual after the upgrade.

# Download

Download the upgrade archive **bigace_update_2.x-2.x.zip** __and__ extract them.

The **bigace_2.X.zip** File contains the following files:

    * bigace_install_2.X.zip
    * install_bigace.php
    * README

# Backup

Creating backups should be a natural task in every IT environment, but I mention it here again for your own good:

**Create a full database and filesystem backup __before__ performing a core upgrade.**

# Step by Step Upgrade

   - Copy **bigace_install_2.X.zip** and **install_bigace.php** to your BIGACE root directory.
         - Execute the **install_bigace.php** script from your browser (it will extract all required files)

                * If anything failed (mostly file permissions problems), fix the shown problem and reload the page (no matter how often)
                * Click the link if you are not redirected automatically
         - If the **install_bigace.php** script does not work (missing zlib or memory problems), you can extract the **bigace_install_2.X.zip** and copy all files manually 
   - Execute the **upgrade.php** script (hit the button until you will be redirected)
   - Follow the instructions on the detail page for your new version

# Modules

All installed Modules must be updated manually. Please have a look at the [Extensions](extensions) detail page, to see if there is an update available.
Some of your modules might require an upgrade, in order to work with your new CMS version.

You can also try to find the Update through the remote Extension search from the Administration.

# Versions


*  Upgrade to 2.7 - **just follow this guide**

*  Upgrade to 2.6 - **just follow this guide**

*  [Upgrade to 2.5](http://www.bigace.de/upgrade-2.5.html) ([screencast](http://www.bigace.de/BIGACE-2.5-Upgrade-Screencast.html))

# Problems?!

If you encounter problems or think the documentation is not clear enough or want to contribute any thoughts about an upgrade, use the [Community Forum](http://forum.bigace.de/) to contact us.
