# Updating the FCKeditor

This page describes how to configure and update the FCKeditor.


## Updating

If you do not want to wait for the next BIGACE release (where the newest Editor will be shipped with) you can manually update the Editor in your Installation. It is quite simple and no system files need to be touched at all!

 1.  Download the latest version
 2.  Delete all files and directorys from **/addon/fckeditor/**
 3.  Extract all files from the download archive to **/addon/fckeditor/**
 4.  If you like, remove unused files like the test directory

If the new version brings improvements, that require new configuration settings, you should NOT edit the editors configuration file, but add those entrys in the BIGACE configuration for the FCKeditor...

## Configuration File

The FCKeditor specific configurations are saved in the file **/system/editor/fckeditor/javascript.php**.

If you want to add new settings or edit the existing configuration, scroll down to the end of the file and search backward through the javascript entrys.


## Dynamic configurations

**Toolbar:** You can (Community-wide) change which toolbar is used by the FCKeditor. Therefor edit the [Configuration](bigace/manual/configurations) entry **editor** -> **fckeditor.toolbar**.

Possible values are:

*  **full** (default - for all available buttons) 

*  ... FIXME ... add all config names


