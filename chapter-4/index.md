---
layout: page
title: Chapter 4&#58; Making a CMS Work for You
---

## Table of Contents

* [WordPress Customization](#wordpress-customization)
	* Widgets
		* Tutorial: Adding Widgets
		* Tutorial: Adding Multiple Widgets
	* Menus
		* Tutorial: Adding a Dynamic Menu
	* Supporting Pages
		* Tutorial: Creating an Archive Page
		* Tutorial: Creating a Search Page
		* Tutorial: Creating a 404 Page
	* Using Images in the Template
		* Tutorial: Adding Featured Images & Thumbnails to Theme
* [Plugins](#plugins)
	* Tutorial: Adding Plugins

## <a name="wordpress-customization">WordPress Customization</a>

We currently have gone through the bare minimum of what you could have to get by with a fully functional CMS at this point. The good thing about that is that everything we add from now on will make the CMS fuller and more useful. 

Everything we are doing to WordPress in this chapter is either a general web enhancement that any CMS would use, or a conceptual step forward on ways to organize functionality in a CMS. Widgets, menus, conditional templates, media management, and plugins are all things that are common to every major CMS.

### Widgets

In WordPress, a widget is spot in your template that can easily be changed from the Dashboard. Most CMSs have something like a “widget” though, more often than not, they are called something else. There are several built in Widgets that come with WordPress, but it is possible to add additional widgets to WordPress via plugins or manual coding. 

To learn more about widgets, read the Codex: [http://codex.wordpress.org/WordPress_Widgets](http://codex.wordpress.org/WordPress_Widgets)

*How do you think you could use widgets in specific situations? A blog? A business website? E-Commerce?*

#### Tutorial: Adding Widgets

We are going to add ‘places’ in the actual template for Widgets to live. We will work through adding a single widget in the sidebar and then show you how to add several in the footer.

In this tutorial we will learn about defining functions, using WordPress built in functions, using an array to define options, and adding WordPress actions for additional functionality.

##### Step 1: Create Functions.php File

<p class="message">Create a functions.php file in your theme’s root folder </p>

##### Step 2: Add Code For a Widget 

The functions.php file is where you can add additional functionality the the WordPress CMS. This is for expanding the initial offering of WordPress, but also to specify some configuration and options that are already offered by WordPress. 

Let’s add the code and then discuss what is happening here.

<p class="file-name">function.php</p>
```php

<?php 
/*-------------- Enable Widgets--------------- */

function blank_widgets_init() {
	register_sidebar( array(
		'name' => ('First Widget'),
		'id' => 'first-widget',
		'description' => 'Widget for our sidebar on pages', 
		'before_widget' => '<div class="widget-sidebar">', 
		'after_widget' => '</div>',
		'before_title' => '<h2>',
		'after_title' => '</h2>'						
		));
	}
add_action('widgets_init', 'blank_widgets_init');

```

You are going to want to be able to add widgets and change their options often, so being comfortable with what all of the options do will help you be able to understand this better and prevent mistakes later. Let’s talk about the code:

What you see here first is a WordPress function and the options for that function. It starts with the first part:

```php

function blank_widgets_init() {
```

This is creating a custom PHP function named blank_widgets_init(). You could name this whatever you want, but having an intelligible naming scheme will help you going forward. 

Then we are using the WordPress function ‘register_sidebar()’ that tells WordPress to add a custom widget area that takes into account the options that you define inside the function. The options are pretty self explanatory:

* ‘name’ is the name of the widget, 
* ‘id’ is the id of the widget that we are going to use later for identifying this specific widget area, 
* ‘description’ is the description of the widget, 
* ‘before_widget’ is the code that comes before the widget is included, 
* ‘after_widget’ is the code that comes after the widget is included, 
* ‘before_title’ is the code that comes before the widget is included, 
* ‘after_title’ is the code that comes after the widget is included.

The final part ‘add_action('widgets_init', 'blank_widgets_init');’ tells WordPress to include the custom PHP function we made that defines our widget functionality. 

##### Step 3: Save and Upload your Functions.php File

If you upload the file now, you can go to Appearance -> Widgets and see the widget area ready for you to modify. Drag one of the default widgets to the new widget, modify it appropriately, and then hit save. 

Nothing will show up on our template until we assign this widget to an area in the template so let’s add this widget to the Sidebar.

##### Step 4: Adding the Widget to the Sidebar

We already have a sidebar assigned to the page.php file and it is a separate template file so that it is easy to include where we see fit. Let’s open up our sidebar.php file and add the PHP code WordPress uses to load a widget into the template file. First, delete the filler content you have in your sidebar.php file and then add this:

<p class="file-name">sidebar.php</p>
```php

<?php dynamic_sidebar('first-widget'); ?>

```
The ‘id’ that we defined in the options of the widget in functions.php is the parameter we use to call the widget using the dynamic_sidebar custom WordPress function. 

##### Step 5: Save and Upload your Sidebar.php file

Once you upload the sidebar.php file (and the other files you have modified) you will see that whatever you put in your widget area will show up in your sidebar on page.php. 

#### Tutorial: Adding Multiple Widgets

There is a slight distinction between adding one widget and multiple widgets, but running through it again will help you better understand the concepts you learned in the previous tutorial. 

##### Step 1: Add More Widgets

We already have one widget, so let’s see how we can add multiple to the same custom function we have.

<p class="file-name">function.php</p>
```php

<?php 
/*-------------- Enable Widgets--------------- */

function blank_widgets_init() {
	register_sidebar( array(
		'name' => ('First Widget'),
		'id' => 'first-widget',
		'description' => 'Widget for our sidebar on pages', 
		'before_widget' => '<div class="widget-sidebar">', 
		'after_widget' => '</div>',
		'before_title' => '<h2>',
		'after_title' => '</h2>'						
		));
/*--- New Widget --- */
	register_sidebar( array(
		'name' => ('Footer Widget One'),
		'id' => 'footer-widget-one',
		'description' => 'First widget for our footer', 
		'before_widget' => '<div class="widget-footer">', 
		'after_widget' => '</div>',
		'before_title' => '<h2>',
		'after_title' => '</h2>'						
		));
	/*--- Second New Widget --- */
	register_sidebar( array(
		'name' => ('Footer Widget Two'),
		'id' => 'footer-widget-two’,
		''description' => 'Second widget for our footer', 
		'before_widget' => '<div class="widget-footer">', 
		'after_widget' => '</div>',
		'before_title' => '<h2>',
		'after_title' => '</h2>'						
		));
	/*--- Third New Widget --- */
	register_sidebar( array(
		'name' => ('Footer Widget Three'),
		'id' => 'footer-widget-three',
		'description' => 'Third widget for our footer', 
		'before_widget' => '<div class="widget-footer">',
		'after_widget' => '</div>',
		'before_title' => '<h2>',
		'after_title' => '</h2>'						
		));

}
add_action('widgets_init', 'blank_widgets_init');
```

The only thing we added was three more full register_sidebar functions and their options array. 

##### Step 2: Add More Widget Areas

Now that we have the actual widgets created, let’s add them to our footer. This will take two steps that are both important: 1. Separate the Footer into three equally sized columns, and 2. Add the dynamic_sidebar custom WordPress function. 

<p class="file-name">footer.php:</p>
```html
<footer class=”row”>
	<div class=”four columns”>
<?php dynamic_sidebar('footer-widget-one'); ?>
</div>
	<div class=”four columns”>
<?php dynamic_sidebar('footer-widget-two'); ?>
</div>
	<div class=”four columns”>
<?php dynamic_sidebar('footer-widget-three'); ?>
</div>
</footer>
</div> 
<?php wp_footer(); ?>

</body>
</html>
```

##### Step 3: Save and Upload

##### Step 4: Add More Widget Content in the Dashboard

Go to the WordPress Dashboard and drag widgets into the newly created Widget areas. You should see this content appear in the footer on the front page, and all of your pages and posts.

### Menus

WordPress has a built in menu system that allows you (or a content editor with correct permissions) to create dynamic menus in the Dashboard. This is incredibly useful for handing off a site you’ve created to a client and letting them make minor changes to the menu without too much risk of them destroying the site (though it is still very possible that adding too many items or other changes could make a mess of it all).

For more in depth information about these subjects, go through the following links on the Codex:

* [WordPress Codex: Navigation Menus](https://codex.wordpress.org/Navigation_Menus)
* [WordPress Codex: WordPress Menu User Guide](https://codex.wordpress.org/WordPress_Menu_User_Guide)

#### Tutorial: Adding a Dynamic Menu

##### Step 1: Enable Menus in Functions

	As a note going forward, when I am adding a snippet to code to a file, I may not include the entire file, but rather just a portion of it. If this is the case, assume that you should place the code where I indicate or at the very bottom. 

<p class="file-name">functions.php</p>

```php 
/*-------------- Enable Menu --------------- */

add_theme_support('menus');

```

Add this to the very bottom of the functions.php file, below the Widgets section.

##### Step 2: Add Menus to Your Template File

We are going do two things here: 1. Add a separate area in our header to house our menu, and 2. add code to hold the menu.

<p class="file-name">header.php:</p>
```html
<!DOCTYPE html>
<html>
<head>
<title></title>
<?php wp_head(); ?>

<link rel="stylesheet" type="text/css" href="<?php bloginfo('stylesheet_url'); ?>" />
</head>
<body>
<div class=”container”>
<header class=”row”>
	<div class=”twelve columns”>
		<h1>Blank WordPress Template</h1>
		<p>This is my WordPress template.</p>
	</div>
</header>
<!-- Add Menu Here -->
<div class=”row”>
	<div class=”twelve columns”>
		<?php wp_nav_menu(array(
			'sort_column' => 'menu_order', 
			'container_class' => 'blank-menu-header'
			));?>
	</div>
</div>
```

The WordPress function we used is ‘wp_nav_menu()’. We are using the options array here in a way we haven’t before. We are defining an array explicitly with the array( ) object and then adding the options with their value (key/value pair). The options I included are sort_column and container_class. More information about this and the other options that are available can be found here: [https://codex.wordpress.org/Function_Reference/wp_nav_menu](https://codex.wordpress.org/Function_Reference/wp_nav_menu)

##### Step 3: Save and Upload

##### Step 4: Create a Menu in the Dashboard

The last step for this will be to go to our Dashboard and actually create a menu (Appearance -> Menus). Drag a couple of pages into the navigation menu or add links. When you hit save, it should show up on all of your pages and posts. 

#### Tutorial: Styling an Inline Menu

I am including styling an inline menu here because I think it will help you see how CSS integrates with WordPress better. If you wish to have a different type of menu in the future, feel free to get rid of these changes and add your own. 

##### Step 1: Identifying the Elements to Style

In the previous tutorial we covered adding a menu, but we didn’t think about how to style it so when we enabled the menu it looked pretty hideous. 

*How are we going to style something that is dynamically generated?*

When working with a CMS, there are always going to be inherent traits that the data is pushed into. This could involve classes for styling, ids for javascript behavior, or just any other metadata that may serve any other purpose. 

	Classes (.name-of-class) in HTML is used mostly for CSS. A Class is an identifier that can be used multiple times in a single page.

	Ids (#name-of-id) in HTML is used mostly for JavaScript. An Id is an identifier that should only be used once per page. 

In our menu, we added an object in our options array called “container_class.” The value associated with that option is “blank-menu-header.” This is how we are going to target that area with our CSS. If you inspect the menu you will see that there the class we added in the options is the class surrounding the whole menu. 

Using Google Chrome’s “Inspect this Element” tool (right click on an object in a webpage to bring this up) is a great way to mess around with CSS in browser and to see what behavior is happening in your web page.


##### Step 2: Add CSS to Style.css

<p class="file-name">style.css</p>
```css
/*--- Menu --- */

.blank-menu-header {
	text-align: right;
	margin-top: 40px;
}
.blank-menu-header ul {
	margin: 0; 
	padding: 0; 
	list-style-type: none; 
	list-style-image: none; 
}
.blank-menu-header li {
	display: inline;
}
.blank-menu-header ul li a {
	text-decoration:none;  
	margin: 4px;
	padding: 5px 0px 5px 40px; 
	font-weight: 300;
	font-size: 1.1rem;
}
.blank-menu-header ul li a:hover {
	color: #cccccc;
}
```

This is just one of many ways you make a menu appear. You can find numerous ways to style a menu in different ways on other websites and tutorials (many of which are more elaborate than this one) so feel free to explore those.

##### Step 3: Save and Upload

### Supporting Pages

We have the front page, posts, and internal pages all ready to go. There are plenty of other situations where you may want to specific templates for. Here we are going to cover three common situations: an archive page, a search page, and a 404 page. 

#### Tutorial: Creating an Archive Page

An archive page is useful for listing large amount of posts in a relatively short amount of space. With WordPress, you can use dates, taxonomies, or other metadata to sort your archived posts. We are going to demonstrate how to archive by month or by category. 

More information about creating an archive page can be found on the codex here: [https://codex.wordpress.org/Creating_an_Archive_Index](https://codex.wordpress.org/Creating_an_Archive_Index). 

##### Step 1: Create an archive.php page

<p class="message">Create an archive.php file in your theme’s root folder</p>

##### Step 2: Create the shell of the archive.php page

<p class="file-name">archive.php</p>
```html
<?php 
/* Template Name: Archive Page */

get_header(); ?>
	<div class="row">
		<div class="twelve columns">
			<h2>Archive</h2>	
			<p>Archive content goes here.</p>
		</div>
	</div>
<?php get_footer(); ?>
```

##### Step 3: Add the functionality of the archive.php page

<p class="file-name">archive.php</p>
```html
<?php 
/* Template Name: Archive Page */

get_header(); ?>
	<div class="row">
		<div class="twelve columns">
<?php the_post(); ?>
<!-- data context -->
			<h2>Archives by Month:</h2>
			<ul>
				<?php wp_get_archives('type=monthly'); ?>
			</ul>
			<h2>Archives by Category:</h2>
			<ul>
				 <?php wp_list_categories(); ?>
			</ul>
		</div>
	</div>
<?php get_footer(); ?>
```

In our archive page we are giving the user an opportunity to view by either month or by category. The WordPress function wp_get_archives will generate the information by month automatically because we passed the type=monthly parameter to it. 

##### Step 4: Save and upload files

#### Tutorial: Creating a Search Page

When a user searches your WordPress site (using WordPress’s built in search functionality), they are going to want to see specific information based on their search query. That’s where having a template page to display the results comes in handy. 

We are going to add a search bar to the header, create a new template page, and then add the code to make the search queries appear as we want them to. 

##### Step 1: Create an search.php page

<p class="message">Create a search.php file in your theme’s root folder</p> 

##### Step 2: Add a search bar in the header

You may have already added a search bar into a widget - so using that would lead you to the search page if you tried to use it. Regardless, we are going to add a search bar into the header where it is for many websites for UI purposes. 

The two things we will do is to split up the header into two columns and then add the WordPress function for a search bar. 

<p class="file-name">header.php:</p>
```html
<!DOCTYPE html>
<html>
<head>
<title></title>
<?php wp_head(); ?>
<link rel="stylesheet" type="text/css" href="<?php bloginfo('stylesheet_url'); ?>" />
</head>
<body>
<div class=”container”>
<header class=”row”>
	<div class=”nine columns”>
		<h1>Blank WordPress Template</h1>
		<p>This is my WordPress template.</p>
	</div>
<!-- Add Search Form -->
	<div class=”three columns”>
		<?php get_search_form(); ?>
	</div>
</header>

<div class=”row”>
	<div class=”twelve columns”>
		<?php wp_nav_menu(array(
			'sort_column' => 'menu_order', 
			'container_class' => 'blank-menu-header'
			));?>
	</div>
	</div>
```
##### Step 4: Build the search.php file

<p class="file-name">search.php</p>
```html
<?php 
/* Template Name: Search Page */

get_header(); ?>

	<div class="row">
		<div class="eight columns">
		
		</div>
		<div class="four columns">
			<?php get_sidebar(); ?>
		</div>
	</div>

<?php get_footer(); ?>
```

##### Step 5: Add functionality to the search.php file

To walk through this file, we are going to include the header, the footer, and the grid system from all of the other files. Also, note the PHP comment at the top that says “Template Name: Search Page.” This is used for the identifying this file as a template file. 

<p class="file-name">search.php</p>
```html
<?php 
/* Template Name: Search Page */

get_header(); ?>

	<div class="row">
		<div class="eight columns">
			<h1><?php printf(__('Search Results for: %s'), '<span>' . get_search_query() . '</span>' ); ?></h1>
			<?php if (have_posts()) :
				while (have_posts()) : the_post(); ?> 									<h2><?php the_title(); ?></h2>
					<?php the_content();
				endwhile;
			endif; 
		?>
		</div>
		<div class="four columns"
			<?php get_sidebar(); ?>
		</div>
	</div>

<?php get_footer(); ?>
```

##### Step 6: Create a condition if there is no search results

We already have a functioning search page, but what happens if there is no search results, we would want to make sure something instructive is included.

To that end, we are going to use some conditional logic to make sure IF there is a result we will display that result, but if anything ELSE occurs, we will display a warning. Getting comfortable with conditional logic will help you considerably with programming going forward. 

<p class="file-name">search.php</p>
```html
<?php 
/* Template Name: Search Page */

get_header(); ?>

	<div class="row">
		<div class="eight columns">
			<?php if( have_posts() ) :?>
				<h1><?php printf(__('Search Results for: %s'), '<span>' . get_search_query() . '</span>' ); ?></h1>

				<?php if (have_posts()) :
					while (have_posts()) : the_post(); ?> 							<h2><?php the_title(); ?></h2>
						<?php the_content();
					endwhile;
			 else : ?>
				<h1>Nothing Found</h1>
				<p>Sorry, but nothing matched your search criteria. Please try again with different search terms.</p>
			<?php endif; ?>
		</div>
		<div class="four columns">
			<?php get_sidebar(); ?>
		</div>
	</div>

<?php get_footer(); ?>
```

##### Step 7: Save and Upload Files

#### Tutorial: Creating a 404 Page

A 404 page is for when someone queries your website with a URL that does not point to any actual page. Have an instructive 404 page can help you guide users throughout your site. 

*What could you add to a 404 page to help get users to content they want?*

##### Step 1: Create an 404.php page

<p class="message">Create a 404.php file in your theme’s root folder</p>

##### Step 2: Add functionality to the 404 page

<p class="file-name">404.php</p>
```html
<?php 
/* Template: 404 page (Not Found) */

get_header(); ?>

	<div class="row">
		<div class="eight columns">
			<h1>Not Found</h1>
			<h2>This is somewhat embarrassing, isn't it?</h2>
			<p>It looks like nothing was found at this location. Maybe try a search?</p>
			
			<h2>Try searching for what you need:</h2>
			<?php get_search_form(); ?>
		</div>
		<div class="four columns">
			<?php get_sidebar(); ?>
		</div>
	</div>

<?php get_footer(); ?>
```

Note that we have put a message saying that there is nothing at this URL, but also gave the user a way to find the information they wanted to see. Considering UI throughout the design process is, obviously, important. 

##### Step 3: Save and Upload Files

### Using Images in the Template

Fewer design elements are discussed or handled more than images are. Not only do they tell a thousand words, but they also are pretty and can help you with your overall visual presentation of your design.

WordPress handles images internally by sorting them in the media section. You can also add them very easily in the Post/Page Dashboard. 

We are going to implement another way to use images with WordPress, the “featured image.” These are also referred to as “thumbnails” because of their original usages in the templating system. They are now used more dynamically as a thumbnail and a featured image (or for any of other things you could imagine). 

*Why would you want to use a featured image on a post instead of just placing on in the post itself?*

#### Tutorial: Adding Featured Images and Thumbnails to Theme

WordPress does not enable featured images/thumbnails by default so you have to do it before they can be used. We are going to enable them in the functions file, add them to our front page, and then add them to our posts.

[WordPress Codex: Post Thumbnail](https://codex.wordpress.org/Post_Thumbnails)

##### Step 1: Enabling in Functions file

<p class="file-name">functions.php</p>
```php

/*--- Enable Post Thumbnails
add_theme_support( 'post-thumbnails' ); 

```

##### Step 2: Adding Thumbnails to the index.php file

The code I am using contains a WordPress function and a parameter of ‘thumbnail’ to define which size image we want to serve up here. Also, we want to make sure that we can use featured images only for those posts where there is a featured image - so we are wrapping the code in a conditional statement. 

<p class="file-name">index.php</p>
```html
<?php get_header(); ?>
<section class=”row”>
	<div class=”twelve columns”>
		<?php 
		if ( have_posts() ) {
   		while ( have_posts() ) {
        	the_post();?>
			<h3><?php the_title(); ?></h3>
			<?php 
			if ( has_post_thumbnail() ) {
				the_post_thumbnail('thumbnail');
			}
			the_excerpt(); 
			    } // end while
			} // end if
		?>
	</div>
</section>
<?php get_footer(); ?>
```

I also added some additional PHP so that we are loading only the specific items we want. You should already be familiar with the_title, but you have not seen the_excerpt yet. 

An **Excerpt** is merely a preview of the full text of the post. This allows you to not dump your entire post into the front page. Additionally, on the post dashboard you can manually add the excerpt if you don’t like what they put. 

##### Step 3: Adding featured image support to the post

We are going to do almost the exact same thing we did above except throw a different parameter into the WordPress function. 

<p class="file-name">single.php:</p>
```html
<?php get_header(); ?>
	<div class="row">
		<div class="twelve columns">
			<?php if (have_posts()) :				
				while (have_posts()) : the_post(); 
				if ( has_post_thumbnail() ) { ?>
					<div class=”post-thumbnail”><?php the_post_thumbnail('large'); ?></div>
				<?php } ?>
					<h2><?php the_title(); ?></h2>
					<?php the_content();
				endwhile;
			endif; ?>
		</div>
	</div>
<?php get_footer(); ?>
```

We have full image size going in now, but we could also use “array( width, height)” to define a custom value to display - which we might want to in case we want strict uniformity. For now though, we will just use the full size image and deal with those specifics later - mostly because I have a better way of dealing with uniformity of images. 

##### Step 4: Save and Upload files

## <a name="plugins">Plugins</a>

We already introduced plugins in the first chapter in the context of WordPress. As a reminder: 

	A Plugin is a group of PHP functions that can extend the functionality present in a standard WordPress weblog. These functions may all be defined in one php file, or may be spread among more than one file. Usually, a plugin is a PHP file that can be uploaded to the "wp-content/plugins" directory on your webserver, where you have installed WordPress. Once you have uploaded the plugin file, you should be able to "turn it on" or Enable it from the "Plugins" page in the administration interface of your weblog. The WordPress source code contains hooks that can be used by plugins.

[https://codex.wordpress.org/Glossary#Plugin](https://codex.wordpress.org/Glossary#Plugin)

The concept of a “plugin” is universal to (nearly) all CMSs. It is a concept of adding functionality to a CMS without having a long development process. Extensibility is a huge bonus to using a CMS. If you didn’t have plugins, you would have to 1) consider additional functionality from scratch, 2) consider the CMS you are trying to add functionality to, 3) develop and test that functionality inside of the CMS, and 4) pray that you didn’t break anything (which hopefully testing addressed, but let’s be honest about how that isn’t always the case). 

So instead of going through that process, we can add a “plugin” to a CMS. In fact, the entire purpose of the functions.php file was originally to take the place of plugins as the primary way to add extensibility to WordPress. Plugins take over the necessity to manually code every bit of functionality you will want to add. 

Commercial CMSs may have an additional fee associated with its plugins. Additionally, even WordPress has many paid plugins. One of the first things you should do before entering into a large scale programming project (in general and for plugins) is to see what has been done before and to see if it would be economical to purchase a “plugin” as your solution. From a purely financial standpoint, this is often the best solution. 

The scope of plugins is vast. They can include everything from a custom post type to adding a slider to adding security features to adding SEO boosting mechanisms to complete site health monitoring to eCommerce functionality. In fact, if there is something you will want to do within a website, there is likely a plugin to help you along your way. 

So plugins sound like amazing additions to your site and will make you a master developer with the click of a button, right?

Well, the biggest downside to plugins is that you are using someone else’s code and project. Unless you dive into the plugin, it is tough to say WHAT is in the plugin. Sometimes an otherwise reliable plugin can grow to be out of date (if they don’t release updates) or contain unknown vulnerabilities. 

Another downside is that the plugin may not integrate well into your system for any number or reasons. If you download a plugin that has conflict, there may be a problem that is somewhat difficult to troubleshoot. Additionally, this may not surface until later when you make changes to CSS or PHP and those changes have a detrimental effect. 

My biggest problem with plugins is that they are often bloated. A plugin designer will often make a plugin to comply with any number of systems and conditions. For instance, if there is a jQuery slider plugin, the designer must include EVERYTHING that is needed to run the slider. Also, they must make sure that the plugin works across a large number of different templating systems. Therefore, it has to be complete and as large as it needs to be. 

### Choosing a Plugin

There are a lot of factors to consider when choosing a plugin:

1. The coordination with the CMS we are using

2. The effectiveness of implementing the functionality we want to add 

3. The cost of the plugin (your developer time and the actual price the vendor may charge)

4. Security and reliability (the most important!)

5. If using the plugin is the easiest and best way to do this

6. The added and unneeded bloat/extra functionality that the project does not need

After taking into account all of these factors, you may end up determining that a plugin is not the best choice for this project. Often times, though, there will be a good fit for adding functionality and it will save you an enormous amount of time. 

With WordPress, we can add, enable, and remove plugins from the Dashboard under the “Plugins” tab. The best way to get more familiar with plugins is to actually add them.

### Tutorial: Adding Plugins

Since plugin creation could be a course on its own, we are just going to introduce them and I will show you how to add plugins, and how to determine which plugins are trustworthy. We are not going to go into crafting plugins or modifying them.

There are two easy ways to find plugins to add. The first is by visiting the [WordPress plugins repository](https://wordpress.org/plugins/). You can search through this list and browse through the best choices. 

The other way is to add plugins through your Dashboard.

<p class="message">Go to your Dashboard and click on the “Plugins” tab</p>

After looking around and clicking through the plugins tab, you will probably feel a bit overwhelmed. The problem is that there are so many plugins that it can be overwhelming to decide which ones we might need. So instead of just browsing the plugins list, let’s brainstorm some functionality that we would like added to the site.

*What would you think would be a good plugin to add to almost any WordPress site?*

There are infinite possibilities here, but let’s think about three plugins that I would consider to be useful for every website. They will add security, site monitoring, and SEO. Nothing flashy, but all super important things. I will only walk through the security plugin, since the other two require additional steps we will cover in future lessons. For your edification though, I suggest you undertake the other two plugins on your own. 

#### Suggested plugins:

* Security: Limit Login Attempts
* Site Monitoring: Google Analytics Plugin (requires a Google Analytics account)
* SEO: Google XML Sitemaps (is more useful with a Google Webmaster account)

#### Step One: Finding a Plugin

So I am being nice and telling you a plugin we will want to use. But in most cases you will not be entirely sure which one is best. So using a natural language search will benefit you greatly.

<p class="message">Click “Add New” at the top of the Plugins page on your Dashboard</p>

<p class="message">Search for “Limit Login Attempts”</p>

#### Step Two: Find the Best One

After you search this, you will see several search results - all of varying degrees of rating and naming. We are going to want to consider all of the relevant results and choose the one that is:

	* Up to date
	* Has a lot of positive ratings
	* Does what we actually want

*What is it we want? Why do we want this?*

Luckily the one we want is up at the top and simply called “Limit Login Attempts” and has over 1 million downloads.

	As of writing this, this plugin is out of date and hasn’t been modified in a long time. This would be a big no-no for most plugins, but in this case it should be alright.

#### Step Three: Install the Plugin

<p class="message">Click on the plugin you want</p>

<p class="message">Read through the information</p>

<p class="message">Click “Install Now”</p>

After you click “Install Now” WordPress will automatically download and install the plugin. This is one of the great benefits of using an internal plugin mechanism like the one WordPress has. 

#### Step Four: Activate the Plugin

On the screen where you have the download dialogue, there is a link that allows you to activate the plugin immediately

<p class="message">Click “Activate Plugin</p>

Alternatively, you can activate a plugin from the main plugin dashboard screen.

#### Step Five: Configure the Plugin

After you activate the plugin, it will now show up in your site and be working. In the Limit Login Attempts plugin’s case, the configuration appears under the “Settings” tab in your Dashboard. 

<p class="message">Click on “Limit Login Attempts” under “Settings” in the Dashboard</p>

You will see a bunch of configuration options you can choose for this plugin. Feel free to go through it and change what you think is best. I personally leave the default settings for this plugin. 
