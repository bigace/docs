# LDAP Authenticator

The LDAP Authenticator is a pluggable authentication system, that gives you the opportunity to authenticate BIGACE at your LDAP. It is not meant for being a "Single sign on" (SSO) solution, but for administrator to have only one place to store user information.
You company employees are now able to login at BIGACE with their company wide username and password.

This Authenticator was developed during my [university](http://www.fh-brs.de/) course "Cross platform authentication systems". Thanks to [Volker Lingens](http://www.volkerlingens.de/) who gave me the chance to develop it as semester project.


`<WRAP center round download>`

Get all downloads from:

[LDAP detail page](http://www.bigace.de/plugins/detail/35-LDAP)

`</WRAP>`

## Features


*  Authenticate against LDAP

*  Configuration via config file and Database configs

*  Separate configs to use different LDAP trees for each community

*  Default group for every user

*  Group mapping between LDAP and BIGACE, for ACL support

*  Group memberships will be verified at every login

*  Authenticate against local user base if LDAP fails (not recommended for prod systems)

## Configuration

The following configurations are available in the package "ldap":

 | Config name        | Default value | Description                                                                                                                                                                              | 
 | -----------        | ------------- | -----------                                                                                                                                                                              | 
 | objectclass        | person        | The schema class to be used for querying user information                                                                                                                                | 
 | account_suffix     |               | Suffix to append to the username search string                                                                                                                                           | 
 | account_prefix     | cn=           | Prefix to prepend to the username search string. Attribute that uniquely identifies the person. The "person" schema for example uses cn=                                                 | 
 | base_dn            |               | The base tree of your LDAP queries                                                                                                                                                       | 
 | domain_controllers | localhost     | Array of possible host controller. Leave as is if you are unsure.                                                                                                                        | 
 | username           |               | Administrator username, used for initiating connection                                                                                                                                   | 
 | password           |               | Administrator password                                                                                                                                                                   | 
 | use_ssl            | true          | Wheter to use ldaps:// for login or plain text                                                                                                                                           | 
 | protocal_version   | 3             | The LDAP version to speak (nowadays 3 should be commonly used).                                                                                                                          | 
 | auth_local         | false         | Use true ONLY(!) for testing purpose. If you activate this, your user might be able to login at Bigace, even if they are deactivated in your LDAP (if you didn't delete them in bigace)! | 
 | default_groups     | array("0")    | Array of BIGACE Group IDs, which will be assigned to new created users                                                                                                                   | 
 | group_attribute    | gidNumber     | Name of the attribute to be used for group matchings. This string is only  used if the parameter group_mappings is set.                                                                  | 
 | group_mappings     | array()       | Mapping between LDAP and BIGACE Group IDs                                                                                                                                                | 

## Installation

 1.  Download and install the Extension 
 2.  Configure your settings, using the config file "**/system/config/ldap.php**" (it contains a lot of documentation!)
 3.  Edit the configuration file "**/system/config/services.ini**" and set the value:

`<code>`[services]
...
authenticator = classes.authentication.LDAPAuthenticator
...`</code>`

## Open tasks

Here are some ideas for future updates:


*  Set user attribute after creation => "ldap user"

*  If user logs in and fails against ldap, check if user exists locally and if, check "ldap user" attribute. Finally, if this is set, delete user.


