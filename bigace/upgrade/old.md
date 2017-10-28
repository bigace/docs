# Upgrading BIGACE up to 2.4

Moving your CMS to the next Version is always a good idea :-)

The following information match all [core upgrades](http://www.bigace.de/bigace/smarty/25_len/index.html) before 2.4! Please read the instructions for each update carefully, there are often further information about manual tasks to execute.

Please follow the correct order (see below), otherwise your BIGACE CMS might be broken.

# Introduction

Always update from one to another ... you should never ever skip any available update. This might result in critical problems with the Database or even in lost data!

For example: Do NOT update from 1.8 to 2.0, but from 1.8 - 1.8.1 - 1.8.2 - 1.8.3 - 2.0!

**Read carefully**:
You HAVE TO read the instructions for each update exactly. There might be special tasks to execute manually after installing the new version.

# Download

Download both, the latest **bigace_2.X.zip** and the **bigace_update_2.x-2.X.zip** archives __and__ extract them.

The **bigace_2.X.zip** File contains the following files:

    * bigace_install_2.X.zip
    * install_bigace.php
    * README *(not required for upgrading)*

The **bigace_update_2.x-2.X.zip** File contains the file:

    * upgrade.php

# Backup

Create backups of the following files:

    * /system/config/config.system.php
    * /system/config/consumer.ini

**Always create a full (Database and Filesystem) backup before performing the Core Updates!**



# Step by Step Upgrade

   - Copy the files **bigace_install_2.X.zip**, **install_bigace.php** and **upgrade.php** to your BIGACE working directory.
         - Open and execute the **install_bigace.php** script in your Browser (it will extract all required files)

                * If anything failed (mostly file permissions problems), fix the shown problem and reload the page (no matter how often)
                * After extraction DO NOT follow the installation process(!)
         - If the **install_bigace.php** script does not work (missing zlib or memory problems), you can extract the **bigace_install_2.X.zip** and copy all files manually 
   - Re-Insert the backup'ed files from "Backup" into your new system
   - Open and execute the **upgrade.php** script (hit the button until you will be redirected)
   - NOW: Follow the instructions on the detail page for your new Version ([2.3](http://www.bigace.de/bigace/smarty/50/index.php), [2.4](http://www.bigace.de/bigace/smarty/55/index.php))

# Modules

All installed Modules must be updated manually. Please have a look at the [Extensions](extensions) detail page, to see if there is an update available.
Some of your modules might require an upgrade, in order to work with your new CMS version.

You can also try to find the Update through the remote Extension search from your Administration!


# Problems?!

If you have any problems or the documentation is not clear or you want to contribute any thoughts to an Update, use the [Community Forum](http://forum.bigace.de/)!


