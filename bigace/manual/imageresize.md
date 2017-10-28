# Resizing images

BIGACE has basic capabilities in image resizing.

This is currently neither a full featured image manipulation script nor a integrated application.

But if you want to resize an uploaded image without the need of:

*  downloading the image

*  starting Gimp/Photoshop

*  resizing it

*  exporting it  to the proper format

*  upload it again ...

there is a simple solution: BIGACE supports image resizing via URL parameter.

Lets assume, you uploaded an large image with the size of 1280px width and want to resize this to 350px, to use it in your website.

## Step 1: Select image

 
Select the desired image in your editor dialog:

{{bigace:manual:original-image.png|Original image with too large dimensions}}

You see the size is too large. 


## Step 2: Append parameter to reduce size

By adding the URL parameter **w=350** (or **resizeWidth=350**) you achieve, that BIGACE renders your image with that new size, where the width is given by your parameter and the height is automatically calculated:

{{bigace:manual:resized-image.png|Resized image}}

After you appended that parameter, click into the next input field, so the editor recognizes the changes.
Then click that "reload" icon, so the editor fetches the new size and displays the image with proper dimensions.

## How to append the URL Parameter

If you use URL Rewriting, your URL could look like this:
 1.  http://www.example.com/bigace/image/1/image.jpg OR
 2.  http://www.example.com/image.jpg

Then you append the parameter with a ? as delimiter:

 1.  http://www.example.com/bigace/image/1/image.jpg?w=350 OR
 2.  http://www.example.com/image.jpg?w=350

If you do not use URL rewriting, you URL will look like this:
 1.  http://www.example.com/public/index.php?cmd=image&id=1

Then you append the resize parameter, using the & as delimiter:

 1.  http://www.example.com/public/index.php?cmd=image&id=1&w=350

## Available parameter for image resizing

The following parameter exist:


*  **resizeWidth** - (or **w** since v2.5) the new width in pixel

*  **resizeHeight** - (or **h** since v2.5) the new height in pixel

*  **crop** - (or **c** since v2.5) whether the image is only resized or cropped, a boolean value "true" or "false"

If you only append one parameter of **w** and **h**, the other one is calculated. This will fit in most situations. You can also append both parameter, but you might want to activate cropping by appending **c=true** if you do not keep the aspect ratio of the image.



