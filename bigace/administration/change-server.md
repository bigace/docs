# Transfer / Move BIGACE to a new Server

If you move to a new hoster, you need to transfer BIGACE installation and database there.
As BIGACE comes __not__ with a built-in backup system, you need to copy and download the data manually.

## Filesystem backup

You need the complete BIGACE root folder including ALL files and the subfolders.

Good hoster have a solution for filesystem backup, to create ZIP or TAR archives of the directory structure. 
In most cases you might need to download all files with FTP. Just choose your BIGACE folder and get a coffe ;) while downloading.

If you have terminal access like SSH or Windows Remote Desktop you can easily create the archive using zip/tar or any other tool of your choice. If there is no tool available you can ask your provider to create the archive for you.

## Database backup

Using phpMyAdmin will be the solution for most of the people hosting on shared systems. Just select your BIGACE database, switch to Export, select to export:

*  Structure

*  Content

*  all BIGACE tables (using the BIGACE Database Prefix)

*  into a (zipped) file
and GO.

If you have shell access, use mysqlexport or mysqladmin if you have GUI access, what is the best way to transfer mysql data from one machine to another.

If the backup fails, because of too much data, truncate (empty) the "logging" and "session" tables. With activated statistics, you might create a single backup from the "statistics" data, truncate it afterwards and recreate the full backup.

## Reimport Database

Using phpMyAmin, simply create a new database on your new server. Select import and choose the exported file created in the step before. Upload and wait, everything should be fine.

Using a MySQL Tool you can choose between shell with mysqlimport and GUI with mysqladmin.

## Re-upload file structure

Using FTP upload the BIGACE folder into your webroot.

If you have shell access, upload the archive and extract it.

## Reconfigure BIGACE on the new host

After you moved database and filesystem to the new machine, you can now change the BIGACE config, according to your new environment.

 1.  Edit **/system/config/consumer.ini** and replace the old domain with the new one (for example [www.example.com] with [www.mynewhost.com])
 2.  Edit **/system/config/config.system.php** and change the database connecting parameter

## Environment changed

If your new webhost does not support URL Rewriting and you want to turn it off, or you want to activate it because your new hoster supports .htaccess files, please read the [URL Rewriting](bigace/administration/urlrewriting) Guide.

If you now run in a subfolder of your domain, read how to change that in the config file [consumer.ini](bigace/manual/community#consumer.ini).

# SEO

Moving BIGACE to a new host is often connected with a domain change. In this case, think about keeping the old domain and activating a 301 .htaccess redirects to the new site for at least several weeks.

