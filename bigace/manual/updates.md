# Updates - Installation of BIGACE Extensions

This topic coves the different methods to install BIGACE extensions.

**Related articles:**


*  A full list of [all available Extensions.](extensions)

*  How to [create a new Extension?](update)

## Step by Step

 1.  Find your favorite extension
 2.  Download it to your computer
 3.  Upload the Extension by using one of the methods "administration" or "FTP" (see below)
 4.  Execute the installation from your admin panel

## Find Extensions

The page [Extensions](extensions) covers a list of available extensions and related resources.

Since BIGACE 2.4, you can also go to your Administration and open the "Systems/Extensions" Panel. Switch to the "Find Extensions" tab and hit the "Search Extensions" button. 
This will sends a SOAP request to the BIGACE Home Server, searching for all known extensions. The result is a list of known extensions, that is displayed to you including download links.

## Download Extensions

Download the Extension from Sourceforge, either using the download link in the administration screen or from the extensions detail page.

## Upload Extension

There are generally two ways of installation a BIGACE extension.

### 1. Using Administration

Open the Administration panel "System/Extensions" and change to the "Upload new Extension" tab.

Open the file browser and select the previous downloaded extension from your computer. Hit the "Upload" button, to send the extension to your BIGACE Web CMS. 
If you want to upload the extension without installation, uncheck the "Upload & Install" box.

After that, it can be found in the "Available Extensions" tab, which holds information about all uploaded extensions.

If you don't see a "{Extension Name} was successful installed" message, you get a screen listing with errors (see Troubleshooting section). 

### 2. With FTP

 1.  Download the ZIP file
 2.  Extract it on your computer (Using Unzip, 7-Zip, WinZIP, WinRAR, WinACE...)
 3.  Upload everything into the /misc/updates/
 4.  Assuming you have the local folder /guestbook/ you have /misc/updates/guestbook/ after uploading
 5.  DELETEME Before __BIGACE 1.9__ updates were stored in /misc/install/update/
 6.  Install it using the first tab of the Extension Administration


## Troubleshooting

Sometimes uploading and installing an extension does not work the way you expect. This is most often caused by file or directory permission. In this case, you get a screen with further details. You can try to fix those permissions automatically, by passing your FTP account data.
BIGACE then connects to your host and tries to repair them. You can also fix them manually and re-install.

In any other case, like an SQL Problem, you see a screen with further details. Please leave a message in our forum, we or the Extensions author will help you as soon as possible. 

Note: You can always re-install each Extension from the "Available Extensions" tab! 
