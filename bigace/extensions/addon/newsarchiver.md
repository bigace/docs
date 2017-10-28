# News Archiver

The News Archiver is an extension for the [News System](bigace/extensions/addon/news).

The News Archiver is able to find news older than a configured age. These news will be moved to an archive, where they are still existing, viewable, but they do not show up in the active News list.
Activate the News Archiver if you have a lot of News or if you do not want to display old news on your website.

To de-/activate the News Archiver, you have to change its in the Administration at "System/Cron Jobs".


`<WRAP center round alert 60%>`

**CAUTION**
This extension is not stable **and** it will **not** work with newer versions of Bigace and the News extension. Please contact us in the Forum first before using!
`</WRAP>`

`<WRAP center round download 60%>`
Grab your download for Bigace 2.4 from the:\\
[Experimental Package](http://www.bigace.de/plugins/detail/182-Experimental) 
`</WRAP>`


Its key features are (currently):


*  Moving old News to News Archive

*  News Archive is managed in Years and Months


## Installation

 1.  Download (see below) and [install](bigace/manual/updates) the News Archiver
 2.  Configure your News Archiver (see below)
 3.  Activate the News Archiver [AutoJob](bigace/manual/autojobs)

## Configuration

**1.)** Create the Menu page "News Archive" (where old News will be archived to).

**2.)** Configure your News System at [System/Configurations](bigace/manual/configurations) (you need the "admin_configurations" Permission to open it).

Go to Package "news".

__Names:__
 1.  archive.id
 2.  archive.min.age.days
 3.  archive.min.age.month
 4.  template.archive.month
 5.  template.archive.year

__Descriptions:__
 1.  Menu ID, where archived News will be automatically moved below.
 2.  The amount of days, until the News entry will be moved to the Archive, counted from creation (added to the month setting).
 3.  The amount of month, until the News entry will be moved to the Archive, counted from creation (added to the days setting).
 4.  Template Name, which is assigned to each automatically created monthly archive.
 5.  Template Name, which is assigned to each automatically created year archive.

