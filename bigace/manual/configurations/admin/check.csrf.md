# check.csrf

Package: **[.](.)**

*Check for Cross-Site-Request-Forgery attacks*

This is an important security related setting, defining the amount of time (in seconds) that a user can wait before he is not allowed to POST data to the administration after his last admin action.

Each time the user reloads the administration, an internal value (last visit) is resetted to the current time.
If the user POSTs data to the administration (and before the value is resetted) a check is performed between that internal value, the current time and this configuration setting. If the configuration is higher than the difference of current time and the internal value, the POST is accepted. If the check fails, you see an error screen.


*  Type: int

*  Default: ''1800'' (30 minutes)

## See also


*  [Configuring Bigace](manual/configurations)

*  [bigace:manual:67108867](manual/67108867)

## External links

*  [Wikipedia CSRF](http://en.wikipedia.org/wiki/Cross-site_request_forgery)
