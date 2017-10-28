# widgets()

The **widgets** ViewHelper fetches [bigace:manual:widgets](manual/widgets) for a given Item.

-> Since BIGACE 3.0

## Attributes


*  **$item** - (__required__, Bigace_Item)
    The $item to fetch Widgets for.

*  **$name** - (optional, String)
    The $name of the Widget column. (Default: null -> ignore if you are using only one column).

Returns an array of Widget obbjects, see API.
    
## Example

This example shows to load and display widgets in a normal (one column) [layout](developer/zendtemplate).

	:::php
	<?php 
	/*
	Widgets: sidebar

	*/
	
	  $widgets = $this->widgets($this->MENU);
	  foreach($widgets as $widget) {
	    echo `<h2>` . $widget->getTitle() . `</h2>`;
	    echo $widget->getHtml();
	  }
	?>



This example shows support for multiple widget columns.

	:::php
	<?php 
	/*
	Widgets: left,right

	*/
	
	  echo `<div id="left">`;
	  $widgets = $this->widgets($this->MENU, 'left');
	  foreach($widgets as $widget) {
	    echo `<h2>` . $widget->getTitle() . `</h2>`;
	    echo $widget->getHtml();
	  }
	  echo `</div>`;
	
	  echo `<div id="right">`;
	  $widgets = $this->widgets($this->MENU, 'right');
	  foreach($widgets as $widget) {
	    echo `<h2>` . $widget->getTitle() . `</h2>`;
	    echo $widget->getHtml();
	  }
	  echo `</div>`;
	?>  


## See also


*  [bigace:manual:widgets](manual/widgets) - what are widgets

*  [bigace:developer:zendtemplate](developer/zendtemplate) - enable widgets in your template

*  [Widget API](http://dev.bigace.org/api/latest/Bigace_Widget/Bigace_Widget.html)

*  [ViewHelper widgets() API](http://dev.bigace.org/api/latest/Bigace_Zend/View_Helper/Bigace_Zend_View_Helper_Widgets.html)

