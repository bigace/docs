# codeEditor()

The **codeEditor** ViewHelper turns a normal TextArea into a Code editor with Syntax highlighting.

The ViewHelper uses [CodeMirror](http://codemirror.net/) but only ships a subset of all available Highlighting Parser. If you need different Highlighter please download CodeMirror and copy the parser to **/public/system/codemirror/contrib/**.

If Javascript is disabled the user will see a normal textarea. Please note, that the ViewHelper itself only returns a `<script>` TAG. 

It implements a Fluent-Interface and makes use of the magic toString() method.

-> Since BIGACE 3.0

Further infos at the [ViewHelper codeEditor() PHPDoc](http://api.bigace-cms.com/latest/Bigace_Zend/View_Helper/Bigace_Zend_View_Helper_CodeEditor.html).

## Attributes


*  **$name** - (__required__, string)
    The $name defines ...

*  **$value** - (__required__, string)
    The $value defines ...

*  **$attr** - (optional, array)
    The $attr defines ... 

## Example

Usage in your View is really simple. You can pass the code type as key in the constructor $attr array. We assume that the variable $editorContent holds the PHP code that you want to edit:

	:::php
	<?php
	  echo `<textarea name="foo">`.$editorContent.`</textarea>`;
	  echo $this->codeEditor('foo', $editorContent, array('highlighther' => 'php'));
	?>

or you set it after initialization:

	:::php
	<?php
	  echo `<textarea name="foo">`.$editorContent.`</textarea>`;
	  echo $this->codeEditor('foo', $editorContent)->setHighlighter('php');
	?>

 
Where $name is the name of the editor form element, and $editorContent is the Code to edit.

