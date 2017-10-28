# YouTube

YouTube is a [Plugins](plugins) Module, which replaces a code within a rendered page with a YouTube video.

Its easy to use: You enter a code like this into your page:

	
	[youtube]bkOe7VOmynA[/youtube]

and it will be replaced with the YouTube video that has the ID "bkOe7VOmynA".

The output is configurable by some configuration settings, as you can read below.

Please note, that the code can be written both in a pages content AND also in your template. It doesn't matter, because the parser (which replaces the code) is always triggered after the complete page was rendered! 

Please note that the Plugins uses the new embeding iframe-code.


`<WRAP center round download>`

Get all downloads from:

[YouTube detail page](http://www.bigace.de/plugins/detail/55-YouTube)

`</WRAP>`

## Downloads


*  [Version 1.1](http://sourceforge.net/projects/bigace/files/2_Extensions/YouTube/YouTube_1.1.zip/download) for BIGACE 2.7.5 (28 April 2011)

*  [Version 1.0](http://sourceforge.net/projects/bigace/files/2_Extensions/YouTube/YouTube_1.0.zip/download) for BIGACE 2.7.5 (12 November 2010)

## How to use

1. Download, install and __activate__ the Plugin.

2. Lets say you want to include this video into your website:

{{:bigace:extensions:screenshot_003.png|}}

Then you need the YouTube Video-ID which can be found in the URL (as shown in the screenshot). In this example it would be the **juHMvf5eNYQ**.

Now open the page editor and put the following code into your content:
`[youtube]juHMvf5eNYQ[/youtube]`

Please note, that you do not have to switch to the source-code view, you can paste it into the WYSIWYG view!

3. After you saved, reload the page and the video should appear.

## Configurations

Please switch to [bigace:manual:configurations](manual/configurations) and choose the package "youtube".


*  **title** - Title of the IFrame

*  **class** - CSS class of the IFrame (if you want to customize the look)

*  **width** - Width of the IFrame (should be adjusted to your template)

*  **height** - Height of the IFrame (should be adjusted to your template)

