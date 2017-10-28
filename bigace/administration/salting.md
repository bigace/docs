# Password salting

With BIGACE 2.5 RC2 a method to salt passwords was introduced. The mechanism safely prevents you from:

   * web based dictionary attacks
   * rainbow table attacks

It doesn't matter that the salting algorithm is known, because you define the salt and the salt length by yourself OR the salt is generated during installation.

You can activate it with the following keys in **/system/config/config.system.php**: 

	:::php
	define ('BIGACE_AUTH_SALT', "1276f5a806c981a8eb02b150b879aa");
	define ('BIGACE_SALT_LENGTH', 10);


Please change the salt **1276f5a806c981a8eb02b150b879aa** to a random string of your choice (longer is better).
Replace the salt length **10** with a value between 1 AND 31.

Under Linux you might use something like this to generate a 30 character long salt:

	
	dd if=/dev/urandom count=128 bs=1 2>&1 | md5sum | cut -b-30


Using Password salting is **HIGHLY RECOMMENDED**!

## Upgrade

If you use an older version of BIGACE, you need to update your data **BEFORE** activating password salting!

The following script converts your current passwords to use your configured salting values:

	:::php
	// Please be patient, the script will be made available soon!


 1.  Save this script in your BIGACE root directory.
 2.  This script ONLY works with BIGACE >= 2.5 RC2.
 3.  Do not execute before you added your salting configuration.


