# Reading Userdata

[User-data](administration/userattributes) ist the data that each user can edit in the administration, by accessing the own profile and clicking the "Userdata" tab.

Please note, that Bigace makes a difference between user-data and user-settings. The settings are account related information like language and email adress, where user-data is not directly important for Bigace core system. User-data is meant for application developer, who want to read and write user related information.

If you try to access the user-attributes in your code, you have to know, that Bigace does not guarantee to store empty values. If a user leaves a form-field empty, it might or might-not be saved. Accessing it directly here without a proper check could lead to an error, therefor check it for example like that:
`if(!empty($attributes['phone'])) { echo 'Here it is!'; }`

## Coding examples

**Reading all user-attributes:**

	:::php
	// get the user service
	$principalService = ServiceFactory::get()->getPrincipalService();
	// fetch the super-user 
	$user = $principalService->lookupByID(1);
	// fetch all user-attributes
	$attributes = $principalService->getAttributes($user);
	// and display all information
	echo `<h1>`User attributes for: '.$user->getName().' [ID '.$user->getId().']`</h1>`;
	foreach($attributes as $key => $value) {
	    echo `<b>`.$key.`</b>`: '.$value.`<br/>`;
	}


**Reading user-settings:**

	:::php
	// get the user service
	$principalService = ServiceFactory::get()->getPrincipalService();
	// fetch the super-user 
	$user = $principalService->lookupByID(1);
	// display all user-settings
	echo `<h1>`User settings for: '.$user->getName().`</h1>`;
	echo `<b>`ID:`</b>` ' . $user->getID
	echo `<b>`Name:`</b>` ' . $user->getName();
	echo `<b>`Language:`</b>` ' . $user->getLanguageId();
	echo `<b>`Email:`</b>` ' . $user->getEmail();
	echo `<b>`Active:`</b>` ' . ($user->isActive() ? 'YES' : 'NO');


## Read more

*  [bigace:administration:userattributes](administration/userattributes)

TODO add api links
