# Service configuration

File ''/application/bigace/configs/services.php''

FIXME add content 

Default content:

	:::php
	return array (
	    'captcha'       => array(
	        'class'     => 'Zend_Captcha_Figlet',
	        'arguments' => array(
	            array(
	                'wordLen' => 4,
	                'timeout' => 300,
	            )
	        )
	    ),
	    'principal'     => array(
	        'class'     => 'Bigace_Principal_Default_Service'
	    ),
	    'authenticator' => array(
	        'class'     => 'Bigace_Auth_Default'
	    ),
	    'widget'        => array(
	        'class'     => 'Bigace_Widget_DefaultService'
	    ),
	    'logger'        => array(
	        'type'      => 'classes.logger.DBLogger',
	        'arguments' => array('system'),
	        'methods'   => array(
	                        'setLogLevel' => array(E_ALL | E_STRICT),
	        )
	    ),
	    'view'          => array(
	        'class'     => 'Bigace_View_Zend'
	    ),
	);


