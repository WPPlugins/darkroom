=== Darkroom ===
Contributors: jed
Donate link: http://www.innerturtle.com/darkroom
Tags: picture, gallery, collection
Requires at least: 2.6
Tested up to: 2.6.5
Stable tag: 1.1

Implements a full-fledged photo gallery function within WordPress.

== Description ==

Darkroom is a plugin I wrote for my own blog and thought other people might like to use in their blogs. Iíve tried 
to build in some flexibility as well as ease-of-use, but there are always compromises. I look forward to your feedback 
so I can make it better. To contact me about the plugin please use darkroom@innerturtle.com so that I know what 
your e-mail is about.

Features:
* Captions are loaded through EXIF/XMP tags. You just upload your pictures and go.
* Use of lightbox through the slimbox plugin
* The ability to list different ìgalleriesî either in your sidebar or directly in the page content.
* Complete control over where your gallery appears.
* The ability to watermark your pictures for copyright purposes.
* Most customization is done through the regular WordPress admin page.

== Installation ==

1.  Download the source, uncompress it, and put the darkroom folder in your WordPress plugins directory.
1.  Create a folder called ìpicsî in the root of your WordPress installation. Create sub-folders and put pictures 
    in them. For Example:
    1.  My blog is located at /usr/web/innerturtle.com/. I can access this via FTP.
    1.  I created a new folder called pics. It lives at /user/web/innerturtle.com/pics/. This will be the place where
       darkroom gets all the pictures. But wait, I canít put any pictures files into this folder SOÖ
    1.  I create subfolders, maybe ìBirthdayPicturesî and ìHikingPicturesî. These would live at 
        /user/web/innerturtle.com/pics/BirthdayPictures/ and /user/web/innerturtle.com/pics/HikingPictures/
        respectively.
    1.  I put my birthday pictures in /user/web/innerturtle.com/pics/BirthdayPictures/ and I put my hiking pictures in 
        /user/web/innerturtle.com/pics/HikingPictures/.
    1.  Now Darkroom will show that I have two ìcollectionsî: one of birthday pictures and one of hiking pictures.
1.  Go into your WordPress Admin Console and create a new page. The name of your page is as it will appear on your site
    (unless you change this, see below.) You must enter a custom field: make the KEY of 'darkroom' and the VALUE of 'true'.
    Do not include the single-quotes and use all lower-case letters.
1.  View your new page. If youíve done the previous steps correctly, youíll see a photo album.

== Advanced Installation ==

1.  *Use the database cache.* Go into the Darkroom settings and turn on both "Use Database Cache" and
    "Create/Recreate Database Table". If you only turn on the first option, it will automatically turn-off because there 
    is no database table to use.
1.  *Use a sidebar.* Turn-on the Darkroom setting for Use Sidebar for Navigation. Then, put the following code in your
    sidebar.php file in your theme: `<?php darkroom_sidebar(); ?>`.
    
	There are several parameters available for this function: `darkroom_sidebar($include_timestamps = TRUE, 
    $head_name = ëPicture Galleriesí, $is_item = TRUE, $title_before = ë<h2><em>í, $title_after = ë</em></h2>í,
	$list_class = ëcategoriesí)`
    1. $include_timestamps (TRUE) - whether to include the timestamp for each collection in the list in the sidebar. This 
     doesnít work well with all themes.
    1. $is_item (TRUE) - whether the sidebar entries should be surrounded in a <li> tag. This varies from theme to theme.
    1. $title_before (’<h2><em>’) - this is what to put before the sidebar heading/title.
    1. $title_after (’</em></h2>’) - this is what to put after the sidebar heading/title.
    1. $list_class (’categories’) - this is the class to make the sidebar list, which may vary from theme to theme.

    Once you get the sidebar working, you may want to supress some of the other sidebar content. Also see
    ìCustomize Your Theme,î below, for the functions you can use to do this.
1.  *Enable the footer.* First, put the following code in your footer.php file in your theme: `<?php darkroom_footer(); ?>`.

    There are two parameters available for this function: `darkroom_footer($before=î, $after=í<br />í)`.
    1. $before - this is what to put before the footer text.
    1. $after - this is what to put after the footer text.
1.  Customize your theme. There are two approaches:
    1. Use the WordPress is_page() function. For example, my page is called pictures so I could write test against 
    is_page(ípicturesí).
    1. Use the Darkroom function is_darkroom(). This function does not take any variables.

    For example, most themes include the page name at the top of the page. This just messes up the flow of Darkroom.
    You could change a line in your themeís page.php to read something like this: `<?php if (!is_darkroom()) { ?><h2>
    <?php the_title(); ?></h2><?php } ?>`

== New Features in Version 1.1 == 

* A new option has been added for “Sidebar Title.” This replaces the option in the darkroom_sidebar function. The installation 
section has been updated below. (The readme.txt in the old version has the correct information for that version.)
* Added experimental “widget” support. You should have the option to use the Darkroom sidebar widget if you use widgets to 
customize your sidebar. Please note: If you use the widget, it will display in your sidebar any time the darkroom content is 
displayed — even if the “Use Sidebar for Navigation” option is set to No. It’s strongly recommended that you turn “Use Sidebar 
for Navigation” option to “on” if you’re using the widget.


== Frequently Asked Questions ==

= Why should I use Darkroom =

If you want to use a picture/photo gallery in your blog, Darkroom is a good choice. It is a fully-integrated solution
that doesn't just put nondescript thumbnails on a page that are hard for people to understand in a context. It's also
very customizable.

== Screenshots ==

1. This shows Darkroom listing the "collections" (picture galleries) in a relatively default configuration
2. This shows Darkroom listing the "collections" via the sidebar.
3. This shows Darkroom listing the contents of one of the collections.
4. This shows Darkroom showing one of the pictures in a collection (note, this is accomplished via slimbox.)