=== Draft List ===
Contributors: dartiss
Donate link: https://artiss.blog/donate
Tags: draft, list, scheduled, SEO, widget
Requires at least: 4.6
Tested up to: 6.6
Requires PHP: 7.4
Stable tag: 2.6
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html
README revision: 1.0

WordPress plugin to manage and promote your unpublished content.

== Description ==

**If you're upgrading from a previous release of Draft List (i.e. pre version 2.5) please check out the FAQ - a number of changes have been made in this release that you need to be aware of**

Draft List allows you to both manage your draft and scheduled posts more easily but also to promote them by showing them on your site via shortcode or widget - use it to show your visitors what's "coming soon" or as a great SEO tool.

How easy is it display a list of draft posts? Here's an example of how you could use it in a post or page...

`[drafts limit=5 type=post order=ma scheduled=no template='{{ul}}{{[draft}} {{icon}}']`

This would display a list of up to 5 draft posts in ascending modified date sequence, with an icon displayed to the right of each if the draft is scheduled.

Key features include...

* Both widgets and shortcodes are available for you to show off your up-coming content
* Output is highly configurable - create your own look by using a template, identify scheduled posts with an icon, sequence the results in various ways and even narrow down the results to a specific timeframe
* Click on any of the drafts posts listed to edit them
* A meta box in the editor screen allows you to omit individual posts from any list outputs
* Tested up to PHP 8.2
* Fully complies with WordPress coding standards
* Compliant with the stronger [WordPress VIP](https://wpvip.com/) coding standards, as well as compatibility with their platform
* Community plugin - visit the [Github page](https://github.com/dartiss/draft-list "Github") to get involved with the latest code development, request enhancements and report issues

Iconography is courtesy of the very talented [Janki Rathod](https://www.fiverr.com/jankirathore).

== Shortcode Parameters ==

The following shortcode parameters are valid...

* **cache=** : How long to cache the output for, in hours. Defaults to half an hour. Set to `No` to not cache at all. Whenever you save a post any cache will be cleared to ensure that any lists are updated.
* **date=** : The format of any dates output. This uses the PHP date formatting system - [read here](http://uk3.php.net/manual/en/function.date.php "date") for the formatting codes. Defaults to `F j, Y, g:i a`.
* **folder=** : The scheduled icon will be, by default, the one in the plugin folder named `scheduled.png`. However, use this parameter to specify a folder within your theme that you'd prefer the icon to be fetched from.
* **limit=** : The maximum number of draft items to display. The default is 0, which is unlimited.
* **order=** : This is the sequence that you'd like to order the results in. It consists of 2 codes - the first is either `t`, `m` or `c` to represent the title, modified date or created date and the second is `a` or `d` for ascending or descending. Therefore `order=td` will display the results in descending title sequence. The default is descending modified date.
* **pending=** : True or false, where to include pending posts in the result. By default, pending posts will not be included.
* **scheduled=** : True or false, where to include scheduled posts in the result. By default, scheduled posts will be included.
* **template=** : This is the template which formats the output. See the section below on * *Templates** for further information.
* **type=** : This allows you to limit the results to either `post` or `page`. The default is both.
* **words=** : The minimum number of words that must be present in the draft for it to be included. Defaults to 0.

To restrict the posts to a particular timeframe you can use the following 2 parameters. You simply state, in words, how long ago the posts must be dated for e.g. "2 days", "3 months", etc.

* **created=** : his reflects how long ago the post/page must have been created for it to be listed. For example `6 months` would only list drafts that were created in the last 6 months.
* **modified=** : This reflects how long ago the post/page must have been modified last for it to be listed. For example `6 months` would only list drafts that have been modified in the last 6 months.

== Templates ==

The template parameter allows you to format the output by allowing you to specify how each line of output will display. A number of tags can be added, and you can mix these with HTML. The available tags are as follows...

* **{{ul}}** - Specifies this is an un-ordered list (i.e. bullet point output). This MUST be specified at the beginning of the template if it is to be used.
* **{{ol}}** - Specifies this is an ordered list (i.e. number output). This MUST be specified at the beginning of the template if it is to be used.
* **{{icon}}** - This is the icon that indicates a scheduled post.
* **{{draft}}** - This is the post detail and is the only **REQUIRED** tag.
* **{{author}}** - This is the name of the post author.
* **{{author+link}}** - This is the name of the post author with, where available, a link to their URL.
* **{{words}}** - The number of words in the draft post.
* **{{chars}}** - The number of characters (exc. spaces) in the post.
* **{{chars+space}}** - The number of characters (inc. spaces) in the post.
* **{{created}}** - The date/time the post was created.
* **{{modified}}** - The date/time the post was last modified.
* **{{category}}** - Shows the first category assigned to the post.
* **{{categories}}** - Shows all categories assigned to the post, comma separated.

If {{ul}} or {{ol}} are specified then all the appropriate list tags will be added to the output. If neither are used then it's assumed that line output will be controlled by yourself.

== Omitting Posts/Pages from Results ==

If you wish to omit a page or post from the list then you can do this in 3 ways...

1. By giving the post a title beginning with an exclamation mark. You can then remove this before publishing the post.
2. The post and page editor has a meta box, where you can select to hide the page/post.
3. You can add a custom field to a page/post with a name of 'draft_hide' and a value of 'Yes'

== Edit Link ==

If the current user can edit the draft item being listed then it will be linked to the appropriate edit page. The user then simply needs to click on the draft item to edit it.

There are separate permissions for post and page editing, so an editor with just one permission may find that they can only edit some of the draft items.

Drafts that don't have a title will not be shown on the list UNLESS the current user has edit privileges for the draft - in this case a title of [No Title] will be shown.

== Using a Widget ==

Sidebar widgets can be easily added. In Administration simply click on the `Widgets` option under the `Appearance` menu. `Draft Posts` will be one of the listed widgets. Drag it to the appropriate sidebar on the right hand side and then choose your options.

Save the result and that's it! You can use unlimited widgets, so you can add different lists to different sidebars.

== Installation ==

This plugin can be found and installed via the Plugin menu within WP Admin (Plugins -> Add New). Alternatively, it can be downloaded from WordPress.org and installed manually...

1. Upload the entire unzipped plugin folder to your `wp-content/plugins/` directory, either from WP Admin (Plugins -> Add New), your favorite FTP client or any other file manager
2. Activate the plugin through the 'Plugins' menu in WP Admin (Plugins -> Installed Plugins)

== Frequently Asked Questions ==

= I've upgraded from a version before 2.5 and I hear things have changed. What's happening? =

From version 2.5, 2 features have been removed...

1. Caching has gone. This release has had some massive performance improvements which means it was no longer needed. It, more often than not, caused issues and many people have native caching on their site anyway.
2. The draft menus options have been removed. I've moved that functionality off to another plugin named [Draft Links](https://wordpress.org/plugins/draft-links/). If you want the menu links back, please install that. Why have they been removed? For a start, some people were installing this plugin JUST for that functionality, so it made sense for me to separate it. Additionally, the next FAQ answer is part of this too...

== Screenshots ==

1. An example output of draft posts

== Changelog ==

I use semantic versioning, with the first release being 1.0.

= 2.6 =
* Enhancements: Numerous code quality improvements. So many, this is a major release bump as so much of the code has changed. No new features, though

= 2.5.2 =
* Bug: I wasn't setting an initial value for $code. My bad. Now resolved. Thanks to Wiktor Jędrzejczak for spotting that.
* Enhancement: I've made a number of changes to ensure the plugin abides by PHPCS standards for both WordPress and WordPress VIP. Secure and Performant are my middle names. They're not really. I don't actually have so, theoretically, I could use these.
* Enhancement: For the default clock icon, I'm now using a built-in Dashicon SVG. However, you can override for your own image in the usual way.

= 2.5.1 =
* Bug: Fixed a bug (an extra comma) that impacts users on a particular version of PHP

= 2.5 =
* Enhancement: Total re-write of the post retrieval code
* Enhancement: Brought code up to PHPCS coding standards - hardly a line has been untouched
* Maintenance: Removed the menu changes (links to draft posts)
* Maintenance: Removed Caching
* Maintenance: Rename, concatenation and general shuffle around of the various plugin files
* Maintenance: Updates to the various plugin meta
* Bug: Resolved inconsistencies between `pending` and `scheduled` parameters, where one accepting boolean and yes/no and, well, the other didn't
* Bug: Fixed issue where default values were not being loaded when a widget was being displayed without settings being changed
* Bug: Fixed a bunch of existing bugs, including various widget issues

= 2.4 =
* Enhancement: New option to include pending posts in lists
* Enhancement: New option to limit the posts listed to those with a minimum number of words
* Enhancement: Now using a time constant for the caching
* Enhancement: Added Github links to the plugin meta
* Enhancement: Double braces are the new template standard!
* Enhancement: Renamed 'Your Drafts' to the more appropriate 'My Drafts'
* Maintenance: Added selective refresh support to the widget
* Bug: Fixed an `undefined constant` warning
* Bug: Improved the padding around the draft count in the admin menu

= 2.3.3 =

* Maintenance: The README has had a re-write and the image assets have been replaced. Shiny!
* Maintenance: Minimum WordPress requirement for this plugin is now 4.6, which means various version checks and language files have now been removed. New!
* Maintenance: My site moved some time ago but links in the plugin and the README were still directed to the old one. Changed!
* Maintenance: The shortcake code is called whether in admin or frontend because, well, it makes no difference. Plum!
* Bug: Corrected spelling mistake. Sad trombone!

= 2.3.2 =
* Maintenance: Updated branding, inc. adding donation links

= 2.3.1 =
* Enhancement: Draft pages shortcuts only appear if the user can edit pages
* Enhancement: Only show the user's drafts if it's different to the total number (otherwise, if a site has only one author, they will get two links when only one is required)

= 2.3 =
* Enhancement: Quick links added to admin menu for any draft posts. Will show links for both all drafts and drafts for the current user
* Maintenance: Updated branding
* Maintenance: Removed unnecessary `-adl` prefix from file names
* Maintenance: Stopped hardcoding the plugin folder name in includes. Naughty boy
* Maintenance: Replaced `wp_plugin_url` with the nicerer `plugins_url`
* Maintenance: Replaced the deprecated `attribute_escape` with `esc_attr` in the widget code
* Maintenance: Merged the widget code so it's all in one handy file
* Maintenance: Sanitized the data being sloshed about by the meta box option
* Maintenance: Updated the clock icon to a material design version

= 2.2.6 =
* Maintenance: Added a domain path
* Maintenance: Removed deprecated functionality
* Bug: Fixed the categories tag
* Bug: Solved a PHP bug

= 2.2.5 =
* Maintenance: Added a text domain

= 2.2.4 =
* Bug: I've just noticed that if you use the editor box to hide the post from draft list you can't switch it back off again. Untick the box, save and it's ticked again. Doh. Why did nobody notice this before? It's now fixed though.

= 2.2.3 =
* Maintenance: Resolved widget issues with version 4.3 of WordPress

= 2.2.2 =
* Maintenance: Updated support forum link

= 2.2.1 =
* Bug: Removed some debug output

= 2.2 =
* Maintenance: Updated clock icon
* Enhancement: Added `category` and `categories` template tags

= 2.1 =
* Maintenance: Moved default scheduled icon to its own folder
* Enhancement: Added internationalization

= 2.0.2 =
* Maintenance: Removed dashboard widget

= 2.0.1 =
* Bug: Fix caching problem that prevents edit links from working correctly

= 2.0 =
* Maintenance: Renamed plugin and brought program coding standards up-to-date
* Enhancement: Added new template system, allowing better control over output
* Enhancement: Option to display modified and/or created date
* Enhancement: Option to display word and/or character count
* Enhancement: Draft posts/pages with no title are no longer displayed
* Enhancement: Can now sort output by date created as well as the date modified
* Enhancement: Meta box added to editor to allow post/page to be excluded from list
* Enhancement: Output is now cached (and cache times are adjustable)
* Enhancement: User can now limit time period over which drafts will be displayed
* Enhancement: Added validation of the passed parameters
* Enhancement: New widget option added
* Enhancement: Added improved clock image
* Bug: Alternative icon folder option now works

= 1.6 =
* Enhancement: Draft titles now have links to their edit page if the current user is allowed to edit them

= 1.5 =
* Maintenance: Code tidy
* Enhancement: Added option to show post/page author
* Enhancement: Added version details to code output
* Enhancement: Added shortcode option

= 1.4 =
* Enhancement: Added icon for scheduled posts (which can be modified and switched off, if required)

= 1.3 =
* Enhancement: Date order now displays according to date of last modification

= 1.2 =
* Enhancement: Now displays scheduled posts as well
* Enhancement: Added new parameter to suppress scheduled posts, if required
* Bug: Fixed bug in limit default

= 1.1 =
* Maintenance: With the release of WP 3.0 different post types are possible and these can get mixed in with the results (e.g. menu items, etc). Changed the code to restrict output to pages and posts only

= 1.0 =
* Initial release

== Upgrade Notice ==

= 2.6 =
* Code quality improvements
