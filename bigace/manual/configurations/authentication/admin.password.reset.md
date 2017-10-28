# admin.password.reset

Package: **[.](.)**

Decides whether a [bigace:manual:superuser](bigace/manual/superuser) can reset his password in the default login-process.
This is a **security risk**, as users might be able to see or guess the username and activate the password process/reset the Admins password.

If you change this setting to TRUE, even Admins can use the "Forgot password" function. Otherwise (FALSE) only normal user can use that function.


*  Default: ''FALSE''

## See also


*  [Configuring Bigace](bigace/manual/configurations)


