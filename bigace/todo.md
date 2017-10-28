# TODO

This is an unsorted list of ideas... none of them MUST ever be created or done, but some of them should LOL


## USER MANUAL

FIXME Following points must be fixed to complete the manual migration:


*  [Object permissions (Read/Write/Delete)](bigace/manual/objectrights)  (translate to english)

*  [Menu Administration](bigace/manual/menutree)  (add content - only page skeleton exists)

*  [Menu Workflow](bigace/manual/menuworkflow) (translate to english)

*  [Feedback](bigace/manual/feedback) (translate to english)

*  [Categories](bigace/manual/categoryAdmin) (add content - translate to english)

*  [Configurations](bigace/manual/configurations) (add latest configuration types)

*  [Community Administration](bigace/manual/community) (partially translate to english)

*  [Updates](bigace/manual/updates) (translate to english)

Find a good link place for [bigace:faq](bigace/faq).

Merge the Glossary from the old Docbook User Manuals ?!

*  [English](http://bigace.sourceforge.net/manual/en/) Version

*  [German](http://bigace.sourceforge.net/manual/de/) Version

## Wiki


*  [Add Smarty Tags detail Pages](bigace/smarty_tags)

*  Complete attribute list on [{breadcrumb}](bigace/smarty_tags/breadcrumb)

## Website/ Docu


*  Edit Requirements and add recommended PHP Modules

*  Neuen Admin Header auch für PHP Doc benutzen!


*  Convert existing Logo to be used in IE with alpha channel rendering bug

*  Create new Logo 

*  use new logo everywhere

## Development

### MODUL-ADMIN


*  einbauen in menü admin 

*  übersetzung aus applications.properties in allen modulen nutzen

*  link in ApplicationLinks einbauen
### SMARTY


*  Alle Nutzungen von Design X ersetzen durch Design Y

### EDITOR


*  Wym Editor: [http://sourceforge.net/projects/wym-editor](http://sourceforge.net/projects/wym-editor)

*  List of Editors: [http://www.geniisoft.com/showcase.nsf/WebEditors](http://www.geniisoft.com/showcase.nsf/WebEditors)

### CORE


*  FIXME use same parameter in smarty tag and "show content" modul + administration links

*  GroupRight->checkistrue wegen admin check auf global user überarbeiten

*  Alle SQL Stellen mit [0] suchen und mit für array_fetch_assoc umbauen!! wegen adodb!

*  (nicht) durchsuchbar: flag setzen um seiten aus der suche auszublenden

*  `<del>`nur noch 4 gruppen im standard: anonymous, editor, designer, administrator`</del>`

*  DELETEME fright plugins löschen, fright "edit_frights" und "group_frights" ersetzen, übersetzungen entfernen...

### ADMINISTRATION


*  Neues admin plugin => dateirechte kontrollieren!!

*  zusätzlich check settings aus installer in admin übernehmen um zu sehen was nicht klappen könnte

*  file_check funktion in admin environment mit fehler anzeige

*  permissions: open/edit mit verlinkungs anzeige

## Installation


*  `<del>`safe_mode off im installer precheck!`</del>` als "recommended" eingeordnet
