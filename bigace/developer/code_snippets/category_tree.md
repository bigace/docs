# Categories

To read the children of the Category with ID X, you would do something like:

	:::php
	import('classes.category.CategoryTreeWalker');
	$catWalker = new CategoryTreeWalker(X);
	$a = $catWalker->count();
	for($i=0; $i<$a; $i++) {
	  $category = $catWalker->next();
	  echo 'Category Name: "' . $category->getName() . '" and ID: "'.$category->getID().'"`<br/>`;
	}


The returned Objects are Objects of the type 'classes.category.Category'.
