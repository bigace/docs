# Community Configuration

As Bigace is a multi-site CMS, it can handle independent websites in one installation, where a Community is one of these independent websites. 

You get a list of all communities that your installation handles at the community admin panel.

For each Community you see:

    * the **domain**, the community is mapped to
    * all **alias domains** for this community
    * the [maintenance](maintenance) state
    * whether it is the system **default community** or not

# What are Communites?

Communities are client websites. With one BIGACE installation you can handle as many websites as you want. 
Websites here does NOT mean pages, but complete self-sufficient systems.

Each community has its own data pool, which is separated in database and filesystem. It is not possible for an author using Editor and/or Administration to fetch data from another community than his own one.

Other names for Community are *Consumer* (till version 2.0) or *Mandant* in German. 

# Community INI File

Community settings are stored in the file **/system/config/consumer.ini**. If you want to change the communities main domain (what is currently not possible with the web interface), you might edit this file manually and change it there.

# Alias Domain

A community can be mapped to unlimited domains. At installation time, you enter the intial domain, but when time passes, you might need to add a second or third domain alias.

Now, lets make an short exmaple: Your Community "Intranet" can be accessed at "intranet.example.com" (http://intranet.example.com/). If you know want to make it accessible at the URL "http://cms.example.com/", you have to add an Alias Domain "cms.example.com".

**Note:** Please make sure NOT to enter neither the protocol nor the directory when creating a new alias domain! Only enter the complete hostname (without protocol and path).

## Default Community


Sollte Ihre Installation über andere Domains erreichbar sein als über die Community gebundenen, so wird versucht eine Standard Community zu laden.

Eine Standard Community dient also dazu, Ihren Besucher nicht eine Fehlermeldung zu präsentieren, sondern ihnen trotz der "fehlerhaften" URL nutzvolle Inhalte zu bieten.

Nehmen wir an, Sie haben zwei Community mit je einem Alias:

    * intranet.example.com
          o cms.example.com

    * internet.example.com
          o www.example.com

Wenn Sie nun wollen, das alle Domains die nicht registriert sind (z.B. example.com) auf Ihre Internet Community geleitet werden “www.example.com”, müssen Sie nur “internet.example.com” mit einem Klick zur Standard Community machen. 

## consumer.ini

This is a simple example configuration and shows all possible configurations (please be careful when you edit this file!):

	
	[www.example.de]
	id = 1
	language = "de"
	
	[www.example.com]
	id = 1
	language = "en"
	
	[www.example.org]
	id = 0
	
	[*]
	id = 0


If any domain maps to your BIGACE configuration, which is not mentioned here, the default community [*] will be used with the ID 0.
The **language** flag will overwrite the **community/default.language** setting, which can be applied in the administration panel. Therefor www.example.de uses German (de), www.example.com uses English (en) and www.example.org uses the dynamic setting from **community/default.language**.

As you can see, www.example.de and www.example.com map to the same Community (ID 1). With this in mind, you could build a multi-language site, which shows different contents on different domains.

The next example is a bit more complex and needs your ability to create symlinks on your server. Lets say you want integrate BIGACE into your current website, only within a special folder structure, then you could create a folder structure like this:

	
	/var/www/
	      |
	      + bigace/ (your bigace installation)
	      |
	      + html/ (your website structure)
	          |
	          + cms/ (the directory holding the symlinks)
	             |
	             + sports/ (symlink to /var/www/bigace/)
	             |
	             + technic/ (symlink to /var/www/bigace/)


Now you are able to create one (and one alias) or two communities within your existing website!

This could be the **consumer.ini**:

	
	[www.example.de/cms/sports/]
	id = 1
	path = "cms/sports/"
	
	[www.example.de/cms/technic/]
	id = 2
	path = "cms/technic/"
	
	[*]
	id = 1


Using such a configuration, you have to make sure, that your config.system.php has the following setting:

	:::php
	define ('BIGACE_DIR_PATH', '');


Not clear? Questions? Please ask in the forum, the configuration capabilities are quite powerful.
