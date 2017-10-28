# FCKeditor

The FCKeditor is the BIGACE default editor. and shipped wiht each installation package.

The currently shipped version of the FCKeditor can be found in the [Credits](bigace/manual/credits) section of your BIGACE Administration.

Some useful Internet links for further information and help with the FCKeditor:


*  [FCKEditor Homepage](http://www.fckeditor.net/)

*  [Users Guide](http://docs.fckeditor.net/FCKeditor_2.x/Users_Guide)

See the [FCKeditor Extensions](bigace/extensions/editor/fckeditor) page for more information.

## Editor HTML Templates

The FCKeditor allows to add HTML Snippets (here called: Templates) to give easy access to these templates from within the editor. When you click the template icon in the toolbar, a popup opens, which holds one or more entries. Double click one of these entries and the template is inserted in the Editor.

By un-/checking the checkbox at the pages bottom "Replace actual contents", you select whether the current content is replaced or the templates HTML code is appended to the current content.

You can define these Templates in a simple XML file, located at /public/cid{CID}/editor/templates.xml where [{CID} needs to be replaced by your Community ID](bigace/cid_cid).
If you use only one community this will be most likely **/public/cid1/editor/templates.xml**.
