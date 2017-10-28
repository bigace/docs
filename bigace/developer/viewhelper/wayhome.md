# wayHome()

The **wayHome** ViewHelper returns an array of items, from the current page up to the toplevel page.

This can be useful for example to:

*  display a breadcrumb menu

*  find out in which level you are

*  collapse the current menu in your navigation and display its children

-> Since BIGACE 3.0

## Attributes


*  **$item** - (__required__, Item|array)
    The $item to fetch the way-home for, most often this will be the current menu.

*  **$showHidden** - (optional, boolean)
    Whether hiddden files should be included in the way-home. This is useful if you want to display a breadcrumb where you leave-out hidden pages.

## Example

This example shows to load and display a simple breadcrumb menu for the current page.

	:::php
	<?php
	$breadcrumbs = $this->wayHome($this->MENU, true);
	$amount = count($breadcrumbs);
	
	if($amount > 0)
	{
	    ?>
	    `<ul id="breadcrumbs">`
	    <?php 
	        $i = 0;
	        foreach ($breadcrumbs as $id => $item) { 
		        echo '<li';
		        if($i == 0) echo ' class="first"';
		        if($i == $amount-1) echo ' class="last"';
		        echo '><a href="'.$this->link($item).'">'.$item->getName().'</a></li>';
		        $i++;
	        }
	    ?>
	    `</ul>`
	    <?php
	}
	?>


## See also


*  [ViewHelper wayHome() PHPDoc](http://api.bigace-cms.com/latest/Bigace_Zend/View_Helper/Bigace_Zend_View_Helper_WayHome.html)
