# Editor

The Editor provides a simple way of editing a page like you are used from Office software.

The default editor of Bigace is the CKEditor, which will be automatically used when editing a page.

## CKEditor

The CKEditor has its own manual, please refer to their websites for more information:

*  [http://docs.cksource.com/FCKeditor_2.x/Users_Guide](http://docs.cksource.com/FCKeditor_2.x/Users_Guide)

*  [http://docs.cksource.com/CKEditor_3.x/Accessibility](http://docs.cksource.com/CKEditor_3.x/Accessibility) 

## Plaintext editor

The Plaintext editor is an enhanced sourcecode editor, especially designed for HTML experts.
It is powered by the [markItUp! editor](http://www.bigace.de/markitup-as-stylesheet-template-editor.html).

## Default editor

The default editor is just a fallback when nothing else works. Its simply the HTML sourcecode in a textarea.

# Configurations

## Default editor

You might change the default editor by changing the [configuration](configurations) **editor/default.editor**.

## HTML source code

There might be situations where you don't want your user to access the source code of a page. In this case, you can change the [permission](permissions) **editor.sourcecode**.

## HTML source code

You can change the toolbar of the CKEditor (only for the instance used for page editing) by changing the [configuration](configurations) **editor/fckeditor.toolbar** to one of the following values:

*  minimum

*  simple

*  full
The default toolbar is **full** to give you the best editing experience.

