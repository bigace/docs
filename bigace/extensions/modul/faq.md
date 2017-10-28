# FAQ

The **Frequently Asked Questions** module supports multiple categories with unlimited entries.

###### > Since BIGACE 2.5

The output is fully customizable, cause the module uses a smarty template for rendering. Please have a look on the available Smarty TAGs.


`<WRAP center round download>`

Get all downloads from:

[FAQ detail page](http://www.bigace.de/plugins/detail/30-FAQ)

`</WRAP>`

## Usage

Install and then apply the "FAQ" module to a page of your choice.

Open it and you should see the default entry, that comes with each installation. You can now choose a different section or even a different Template.

If you want to be able to show a different section, depending on a URL Parameter, you can set the "Section GET Parameter". Lets assume you added "section" there, then you can call the page with the GET parameter **http://www.foo.de/faq.html?section=2** and display the section 2 instead of the configured section.

## Permissions

The FAQ module comes with a set of permissions, you need to assign to the user groups that are going to administrate the FAQ content:
 1.  faq.configure
 2.  faq.add.entry
 3.  faq.edit.entry

What the permissions do:
 1.  Lets you configure the page settings of the applied FAQ module
 2.  Lets you add new sections and entries
 3.  Allows to edit and delete entries

## Smarty TAGs


*  [{faq_entries}](bigace/smarty_tags/faq_entries)

*  [{faq_latest}](bigace/smarty_tags/faq_latest)

*  [{faq_section}](bigace/smarty_tags/faq_section)

*  [{faq_sections}](bigace/smarty_tags/faq_sections)

## Screenshots

Start screen with listing of FAQ sections and the amount of entries for each section:

{{bigace:extensions:modul:faq-1.jpg}}

After choosing the categors **Test**, two (or one if you have no permission to create entries) new tabs open:

{{bigace:extensions:modul:faq-2.jpg}}

If you have the permission to create entries, this is the tab where you add one:

{{bigace:extensions:modul:faq-3.jpg}}

## Migration from Version 1.0 to Version 1.1

With the Version 1.1 for BIGACE 2.5, the Database layout changed. The both versions are not compatible! Assuming, that you do not have any data in the tables "cms_generic_entries", "cms_generic_mappings" and "cms_generic_sections" you can use the following SQL for the migration:

	:::sql
	INSERT INTO cms_generic_entries SELECT * FROM cms_faq_entries;
	INSERT INTO cms_generic_mappings SELECT * FROM cms_faq_mappings;
	INSERT INTO cms_generic_sections SELECT id, cid, "faq", name FROM cms_faq_sections;


If you did not use the default database prefix "cms_" replace it in the SQL Statements with your prefix!

