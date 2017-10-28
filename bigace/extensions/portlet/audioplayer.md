# Audio player

This extension supports MP3 playback through Bigace. It can render a [XSPF Web Music Player](http://musicplayer.sourceforge.net)  (a flash-based web application) that uses xspf playlist format to play mp3 songs.

It has two main components:

 1.  a Portlet that plays all MP3 ins the system
 2.  a content parser plugin, which can playback one single MP3 file

`<WRAP center round download>`

Get all downloads from:

[Audio-Player detail page](http://www.bigace.de/plugins/detail/56-Audio+Player)

`</WRAP>`

## Portlet Usage

 1.  Download and install the extension
 2.  Add the Portlet to your page (configure it to your needs)
 3.  Reload the page, you will see the Audio Player
 4.  Upload MP3 files through the administration
 5.  Reload the page, now the Player should load all MP3 files into the Playlist
 6.  Player uses css class "audioplayer"

### Portlet Configurations

 1.  Use slim interface - determines whether to use a slim interface (no playlist)
 2.  Set player width - specifies the width of the player
 3.  Set playlist title - sets the title of a playlist that is displayed in the player
 4.  XSPF playlist URL - you can specify an external XSPF playlist for player

## Content Parser Usage

 1.  Download and install the extension
 2.  Activate the Plugin
 3.  Upload a MP3 file and assign the URL (unique name) "testsong.mp3"
 4.  Edit a page and add the following code to the page: `[mp3]testsong.mp3[/mp3]`
 5.  Save the page and reload it, the player should now be visible
 6.  Player uses css class "mpegplayer"


## Screenshot

{{bigace:extensions:portlet:audioplayer.png|}}

### Links


*  [Forum discussion](http://forum.bigace.de/downloads/audio-player-portlet/)


