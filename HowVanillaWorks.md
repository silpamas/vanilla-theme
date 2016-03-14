# Templating Engine #

Vanilla uses PHPTAL - a templating engine. This adds a bit of overhead, but because PHPTAL does it’s own caching, the added overhead is (relatively) minimal.

Thanks to this templating engine, you’re never going to hear people stressing out about whether they’re “in the loop” or not. It just doesn’t matter any more, because the template HTML is only merged with the WordPress “data” at the last stage of processing, when all data has been collected. You’re free to put things on the page wherever you like, no matter where or when or how WordPress does it’s thing.

Example: when you’re logged in and you view a single page or post, you’ll see an Edit Page link in the top-right menu. Now, that link was processed by WordPress “in the loop”, well after the top menus were processed. Nonetheless, you’ll see that the link is one of the menu items and there are not tricks to it: I just added it to the top menu because I wanted it there, and the templating engine took care of it. Simple.

(PHPTAL also caches page content but I’ve overridden this during alpha development. The cache files are created but are updated on every page call.)

# Fully Widgetized #

Vanilla doesn’t just have a primary and secondary sidebar. Sure, it has these, but they are now only two of a number of “widget blocks” where you can drop widgets in, at your pleasure. You will recall that at installation, you had to move some widgets into their “default” widget blocks to get the Blogologist child theme to look right.

The philosophy here is about opening up all key areas of the page for widgets, and to remove from the page templates key blocks of content that you should be free to put somewhere else, if you wish. So, for example, the “Branding” widget which includes the blog title and description. In Vanilla, these are not hard-coded into the header area of the page, but are in the Branding widget. In the Blogologist child theme, they need to be in the Header widget block, but you might have a different idea in mind for your child theme, hence the widget approach.

The same is true of footer text, and so forth. In fact, the only content on the page which is not resident in a widget is the main page content which is processed “in the loop”. Everything else is in a widget, and you can put it wherever you want.

This is especially powerful for people who want to use the bottom of the page for widgets -- something which has become very popular to do. Vanilla includes (up to) four widget blocks in the “utility” area of the page (above the footer). If you would like to use these, simple drop some widgets in these widget blocks, instead of (or along with) the sidebars.

# Custom Layouts and Bullet-Proof CSS #

Vanilla uses Yahoo’s YUI CSS library to give you a strong, simple and bullet-proof CSS foundation to build on. At a minimum, you will need to use the YUI Grids, as these are integrated into Vanilla. Optionally (and highly recommended), you can use the YUI Reset and YUI Fonts CSS files. The Blogologist child theme uses all three.

One of the very “sexy” features of Vanilla is the custom layouts. In a nutshell -- and without touching code -- you have a huge range of layout options to choose from, with the each of select-boxes in the theme’s Layouts admin page. These options control page width, number and size of sidebars, and the number of utility widget blocks you’d like.

Want a three-column theme? Choose that. Want a single column theme with three columns (utility blocks) of widgets at the bottom of the page? Choose that. Want sidebars on the left instead of the right, or one each side? Choose that.

Better still, thanks to Carrington’s atomic templates, Vanilla lets you customize the layout of individual pages or page sections. Does this ever end??

# Template Sets #

Debate the point if you wish, but there are arguably four different kinds of websites people are in the habit of building using WordPress:

  * Blogs
  * Photoblogs
  * Corporate/Business sites
  * Magazine/Newspaper sites

Accordingly, Vanilla will include not one, but a template set for each of these four different types of theme.

(At the present moment, Vanilla comes with the blog template set, and I’m working on the photoblog set right now. Stay tuned for an update!)

As you would expect, template sets are fully child theme compatible. This means that if you want to create a child theme based on Vanilla’s photoblog template set, you can. You can then customized any/all of that template set’s PHP or HTML files and Vanilla will use your child theme’s file instead of the default.

As is the point with child themes, all this is to ensure that as Vanilla is updated, you can confidently update it to the latest release, knowing that all your customizations are in your child theme. Gotta love child themes!

# Sandbox’s Semantic Markup #

This is old news for most of us, but Vanilla includes the Sandbox theme’s wonderfully powerful semantic markup. This means that, along with what amazing customizations you can achieve with Carrington atomic templates, you can also do some very cool stuff with CSS alone. Want a page to look different according to the time of day? Done. Want the first post on a page to have a different background? Done. Want different blog categories to include different header images? Done.

All in CSS with not a single line of PHP or HTML code added. That’s Sandbox!

# Carrington Atomic Templates #

Alex King and his team are geniuses and they’ve come up with the Carrington theme. He writes:

> Carrington is an attempt to better abstract WordPress theme organization, and simplify commonly needed theme functionality.

> Theme functionality is broken up into thoughtfully crafted abstractions to enable customizations at different levels (the loop, the post/page content, comments, etc.) and a context-aware hierarchical template override system that chooses which template to be used for each segment of the theme.

> The abstractions and supported template types are designed to easily handle most of the customization scenarios we commonly see.

For more on what Carrington does (to which Vanilla adds a whole lot more), [read this](http://crowdfavorite.com/wordpress/carrington/readme/).

# Hooks Everywhere! #

You can’t have too much of a good thing. So Vanilla has a hook for everything.

A hook allows you to add things to a page in a convenient and simple way. Check out the Vanilla Blocks page in your WordPress admin (in the Appearance menu). Just drop in some HTML code there and it will appear on the page in the appropriate place.

For any 3rd party widget that is provided in either a Flash of Javascript block of code, this is by far the easiest way to get it onto the page.

(Note that this is one area of Vanilla that needs more polish. Stay tuned!)