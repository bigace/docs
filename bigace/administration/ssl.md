# SSL

 
SSL is a way to secure data between your browser and the server. Using SSL it is (almost) impossible to read the data that is sent to you or the way-back to the server. This is especially important, when you log-in to Bigace. If you do not use SSL your password is sent through the Internet un-encrypted.

`<WRAP center round tip 60%>`
Therefor it is HIGHLY RECOMMENDED to activate SSL support for Bigace, to make sure administrative data is ALWAYS encrypted.
`</WRAP>`

If you do not encrypt data, attackers yould able to read your passwords and other secure data using methods like [packet sniffing](http://en.wikipedia.org/wiki/Packet_analyzer) or [man-in-the-middle attack](http://en.wikipedia.org/wiki/Man-in-the-middle_attack).

*Since: SSL Support is available since BIGACE 2.5 RC2.*
## Activate SSL

You can activate SSL in the file **/system/config/config.system.php** by adding the following line:

	:::php
	define ('BIGACE_USE_SSL', true);


## Customize HTTPS address

If you want to use a different SSL address than the one that Bigace automatically uses, you can add the following line to **/system/config/config.system.php**:

	:::php
	define ('BIGACE_URL_HTTPS', 'https://'. $_SERVER['HTTP_HOST'] . '/');


This needs to point to your SSL activated server or SSL proxy. If you have your own SSL certificate, you normally do not need to add/customize BIGACE_URL_HTTPS. 
Lets say, your hosting-company offers a free SSL proxy and you want to use it, you could change BIGACE_URL_HTTPS to match th proxy address.



