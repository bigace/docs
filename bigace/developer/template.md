# Templates

This page lists the different options to implement templates in Bigace.

A template can be named "layout" as well. 

## Smarty Templates

Smarty Templates are the default way of using templates in Bigace between version 2.4 and 2.7. In Bigace 3 its supported through an extension.

Find out more about [bigace:developer:smarty](bigace/developer/smarty).

If you don't use Smarty, a hint will appear a in the [bigace:manual:index](bigace/manual/index). That info can be turned off with a configuration entry.

## PHP Templates

Bigace was originally written to use plain PHP files as templates, which were used to render the pages. You had to use the [PHP API](bigace/php_api) to design dynamic areas.

This system is still supported, but deactivated by default, as many end-user do not know how to code PHP.If you are going to use it, you have to deactivate the Smarty engine, see [bigace:manual:configurations](bigace/manual/configurations).

## Zend Layouts

Since Bigace v3 this is the new default way to render your pages.

Read more [.:zendtemplate](./zendtemplate).

