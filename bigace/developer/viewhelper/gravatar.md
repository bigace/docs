# gravatar()

The **gravatar** ViewHelper returns the URL to a Gravatar.

If you want to know more about Gravatars, please visit the official [Gravatar website](http://gravatar.com/).

-> Since BIGACE 3.0

Further infos at the [ViewHelper gravatar() PHPDoc](http://api.bigace-cms.com/latest/Bigace_Zend/View_Helper/Bigace_Zend_View_Helper_Gravatar.html).

## Attributes


*  **$email** - (__required__, string)
    The Email to get the Gravatar for.

*  **$default** - (__required__, string)
    The fallback image, if no Gravatar exists.

*  **$rating** - (optional, string)
    The maximum rated image that might be displayed (see Gravatar website for more infos)

*  **$size** - (optional, integer)
    The size of the image.
    
## Example

This example shows to ...

	:::php
	<?php
	  $email = "test@example.com";
	  $size  = 48;
	  $url   = $this->gravatar($email, "http://www.example.com/fallback.jpg", "G", $size);
	  
	  echo `<img src="'.$url.'" alt="Gravatar for '.$email.'" border="0" width="'.$size.'" />`;
	?>


