# Comments

The Comments System is an Blogging style [Extension](bigace/extensions), written for BIGACE. Can be used with and without installed [News](bigace/extensions/addon/news) Extension.

__Key features:__


*  Stops spam using Captcha

*  Additional use of the [Akismet](http://akismet.com/) service for spam protection

*  Creating of Comments for unregistered and registered user

*  Administration of new Comments (edit, activate, delete)

*  New Smarty TAGs for tasks like counting and fetching comments or a spam counter

*  A lot of configuration settings to customize for your need

*  Send emails on new postings/moderated comments waiting activation

*  Configurable RSS feed, displaying latest comments

*  Simple to integrate. Just activate the Plugin and include one Smarty template

`<WRAP center round download>`

Get all downloads from:

[Comments detail page](http://www.bigace.de/plugins/detail/27-Comments)

`</WRAP>`

## Installation

 1.  Download (see below) and [install](bigace/manual/updates) the Comments.zip
 2.  Go to [User/Permissions](bigace/manual/grouppermission)
 3.  Assign the comments.* Permissions to your Administrator account and to all required Usergroups (see below)
 4.  Activate the Comments plugin at Extensions -> Administration -> Plugins
 5.  Reload the Administration, you see the new Extension entry "Comments"
 6.  Configure your Comments System if required (see below, default options are pre-configured)
 7.  Open your Content Template and add **{include file='Comments-Listing-Form.tpl'}** where you want Comments and Formular to appear
 8.  Do not forget to activate Akismet, to prevent comment spam! ([read more to know how it works](http://akismet.com/personal/))

## Permissions

__Names:__
 1.  comments.activate
 2.  comments.edit
 3.  comments.delete

__Descriptions:__
 1.  Allows to activate pending Comments
 2.  Allows to edit pending Comments
 3.  Allows to delete pending Comments

## Configuration

**1.)** Configure your Comment System at [System/Configurations](bigace/manual/configurations) (you need the "admin_configurations" Permission to open it).

Go to Package "comments".

__Names:__
 1.  auto.activate.unregistered
 2.  auto.activate.registered
 3.  allow.html
 4.  css.use.internal
 5.  email.required
 6.  email.send.moderator
 7.  email.recipient.moderator
 8.  email.send.posting
 9.  email.recipient.posting
 10.  email.from
 11.  gravatar.enable
 12.  gravatar.size
 13.  rss.latest.template
 14.  akismet.wordpress.api.key
 15.  akismet.auto.activate.positive
 16.  akismet.auto.delete.negative
 17.  use.captcha
 18.  ask.for.homepage (since 1.3)
 19.  rel.nofollow (since 1.3)

__Descriptions:__
 1.  whether logged-in users can post comments directly
 2.  whether anonymous users can post comments directly (only for intranets! Don't use on public websites: SPAMMERS will find you!)
 3.  if TRUE, users will be able to embed `<HTML>` in their postings (again, not a good choice for public websites!)
 4.  default: TRUE - loads the included "Comments" Stylesheet. Looks okay on white pages, meant as example; you should create your own style.
 5.  if you set to false, people do not need to include an email address
 6.  if TRUE, emails are sent for new postings waiting for activation (moderated comments)
 7.  comma separated list of recipients for the "moderated comments" email (example: "foo@bar,foo1@bar1")
 8.  if TRUE, emails are sent for new activated postings (see config keys 1 and 2)
 9.  comma separated list of recipients for the "new posting" email (example: "foo@bar,foo1@bar1")
 10.  the address, used as "FROM" value in above mentioned emails
 11.  default: TRUE - whether [Gravatars](bigace/extensions/gravatar) are shown (TRUE) in your comments or not (FALSE)
 12.  size of the gravatar images
 13.  the template, used for rendering the RSS feed
 14.  the wordpress API key, to activate you akismet account
 15.  if (akismet) positiv marked comments should be activated automatically
 16.  if (akismet) spam marked comments should be deleted or kept for manual control
 17.  indicates if a captcha is used in the comment formular
 18.  whether the homepage input field is shown or not
 19.  whether comments are linked with attribute rel="nofollow" or not

## Smarty TAGs

The Comment System comes with some specialized Smarty TAGs.

Please visit their page for further information:


*  [{comment_counter}](bigace/smarty_tags/comment_counter) - count amount of activated Comments for one Item

*  [{comment_format}](bigace/smarty_tags/comment_format) - ...

*  [{comment_spam}](bigace/smarty_tags/comment_spam) - ...

*  [{comments_latest}](bigace/smarty_tags/comments_latest) - to fetch the latest comments at your site

*  [{comments}](bigace/smarty_tags/comments) - a multipurpose TAG for reading existing and creating new comments

*  [{gravatar}](bigace/smarty_tags/gravatar) - creates the valid URL, used for displaying a Gravatar image

*  [{link_comments_rss}](bigace/smarty_tags/link_comments_rss) - ...

*  [{link_trackback}](bigace/smarty_tags/link_trackback) - ...

## RSS Feed

The Comments Extension commes with an RSS feed, which is linked from the HTML metatags automatically after activating the Comments plugin.
You can also link to it by using [{link_comments_rss}](bigace/smarty_tags/link_comments_rss).

If you want to customize the default values (you __should__ do so to personalize the feed!), you have to edit the Template **Comments-RSS-Latest**. Even better, you could create a Template Copy and assign this new template as your RSS Template at the Comments configuration (see above).

## OPEN TASKS

Edit this list if you have any ideas how to improve the Comment System:

*  [Admin] edit existing comments (at least find them by itemid)

*  [Admin] show eaten-spam counter

