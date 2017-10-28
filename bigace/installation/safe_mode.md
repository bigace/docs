# PHPs Safe Mode

The PHP Safe Mode is - well I do not like this rough tongue, but yeah it is - a pain in the ass LOL. It is used quite often in shared-hosting environments to "secure" the website environment... let me say: There are better ways to do that!

And no, I am not an Administrator and have to fight with file permissions for hundreds of users, its just what I guess is the best.

## Troubleshooting

If you can not manage to install BIGACE with activated Safe Mode, try the following:

 1.  Create a subdirectory and copy the installation files there with the same user, the scripts UID must be the same as the directory owner!
 2.  Use PHP4 instead of PHP5 (some difference in behaviour were lately posted at the Forum).
 3.  From the pre-installer, you have to install to a subdirectory again. The script fixes the UID problem by creating directory and files again.
