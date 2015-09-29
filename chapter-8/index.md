---
layout: page
title: Chapter 8&#58; Advanced  WordPress Customization
---
  
## Table of Contents

* [Custom Posts and Pages](#custom-posts-and-pages)
	* Custom Posts
		* Tutorial: Adding Custom Post Type
	* Custom Page Templates
		* Tutorial: Adding a Custom Page Template
* [Using MetaData and Custom Fields](#custom-fields)
	* Tutorial: Using Custom Fields
* [Shortcodes](#shortcodes)
* [Integrating Outside Resources](#integrating-outside-resources)
	* Tutorial: Custom Fonts
* [Child and Parent Themes](#child-and-parent-themes)
* [CSS Based Tutorials](#css-based-tutorials)
    * Tutorial: Styling the Search Bar
    * Tutorial: Sticky Header
* [Adding Advanced Functionality](#adding-functionality)
	* Tutorial: Creating a Separate Page for Blog Posts
	* Tutorial: Integrating Breadcrumbs into your WordPress pages

## <a name="custom-posts-and-pages">Custom Posts and Pages</a>

We know that WordPress has two ways to display content: Pages and Posts. As a reminder, pages are more permanent and posts and meant to be time-based. 

We also know that the page.php file is for displaying pages and the single.php file is for displaying posts. Well, what if we want to make new types of posts (for organization reasons or as new types of content that are outside of the scope of a “blog post.”)? What if we want to have different ways to display page content?

This is where custom posts and pages come into play. There are plenty of scenarios where you may need to go away from the typical look of your page or post. Adding custom page or post templates allows you to add multiple looks for different types of posts or pages. The concept behind their customization is very different and will be useful for entirely different reasons. 

### Custom Posts

A Custom Post will be a completely new content type in the WordPress CMS. The usefulness of this functionality cannot be understated, but it is complicated and can be confusing.

[WordPress Codex - Custom Post Types](https://codex.wordpress.org/Post_Types#Custom_Post_Types)

[Smashing Magazine - The Complete Guide To Custom Post Types](http://www.smashingmagazine.com/2012/11/08/complete-guide-custom-post-types/)

*Can you think of some uses for a custom post type?*

#### Tutorial: Adding Custom Post Type

We are going to use the [Smashing Magazine - The Complete Guide To Custom Post Types](http://www.smashingmagazine.com/2012/11/08/complete-guide-custom-post-types/) guide for this tutorial. I am going to do it a bit different, but if I confuse you with my method feel free to reference it. 

Before we get too deep into the tutorial let’s come up with a concept so that we can focus our understanding on a real world example. Our concept will be “Interesting Web Resources.” This will allow us to create links to interesting posts and brief descriptions of them. We could apply this as a method for linking to outside sources without clogging up our own content. 

Since there is a lot of complicated PHP work in this tutorial, I am going to add the various parts much slower and talk about what is happening in more detail. 

##### Step 1: Add the Register Function

<p class="file-name">functions.php</p>
```php
function custom_web_resources() {

}
add_action( 'init', 'custom_web_resources' );
```
You should recognize this code from the widget initialization code; The same concepts that are there apply here. You are creating a function and adding that function to WordPress through the add_action function.

##### Step 2: Add the Custom WordPress Function

Next we will add a WordPress function used for adding custom post types. It is called register_post_type and more information about it can be found here: [WordPress Codex - Function Reference - Register Post Type](https://codex.wordpress.org/Function_Reference/register_post_type)

This codex entry can help you go through the next step of our tutorial if you are having trouble.

<p class="file-name">functions.php</p>
```php
function custom_web_resources() {
$labels = array();
$args = array();
register_post_type( 'resources', $args ); 
}
add_action( 'init', 'custom_web_resources' );
```

As you can see, we used the register_post_type function to register a post type called ‘resources,’ included an empty array called $args, and included an empty array called $labels. The $args array is called where the function’s arguments would go. 

This is done a bit different than the Smashing Magazine tutorial but I think it is a slightly better way to go about it. 

##### Step 3: Add our Options into the Arrays

There are numerous options that can be added to the register_post_type function. Instead of passing these options through directly, we are creating an object as an array to hold them. This will make our code a bit more organized and modular (which is a very good thing).

<p class="file-name">functions.php</p>
```php
function custom_web_resources() {
$labels = array(
/*--- Begin Labels Options ---*/

    'name'               => _x( 'Links', 'post type general name' ),
    'singular_name'      => _x( 'Link', 'post type singular name' ),
    'add_new'            => _x( 'Add New', weblink ),
    'add_new_item'       => __( 'Add Link' ),
    'edit_item'          => __( 'Edit Links ),
    'new_item'           => __( 'New Link ),
    'all_items'          => __( 'All Links ),
    'view_item'          => __( 'View Links ),
    'search_items'       => __( 'Search Links ),
    'not_found'          => __( 'No links found' ),
    'not_found_in_trash' => __( 'No links found in the Trash' ), 
    'parent_item_colon'  => '',
    'menu_name'          => 'Web Links'

);
$args = array(
/*--- Begin Arguments Options ---*/

'labels' => $labels,
'description'   => 'Place to put useful links to other web resources',
'public'        => true,
'menu_position' => 5,
'supports'      => array( 'title', 'editor', 'thumbnail', 'excerpt', 'comments' ),
'has_archive'   => true,

);
register_post_type( 'resources', $args ); 
}
add_action( 'init', 'custom_web_resources' );
```
One thing to notice is that the entire $labels array is brought in as an option to the $args array. Consider what each item in the options does so that you can see the sort of things that WordPress would want in order to make sure the CMS is using this new custom post type as effectively as possible. 

Also, consider the ['_x'](https://codex.wordpress.org/Function_Reference/_x) and the ['__' functions](http://wpengineer.com/2237/whats-the-difference-between-__-_e-_x-and-_ex/) in the args array. *What do they do? How is this useful?*

There are even more parameters that can be passed to the arguments. These can be found [in the WordPress Codex entry for the register_post_type function](https://codex.wordpress.org/Function_Reference/register_post_type#Parameters). The one parameter we want to focus on is the “has_archive” parameter. This allows us to create an archive page to display these posts. 

##### Step 5: Save and Upload

After you save and upload, this is where the errors would become apparent. When you are adding big chunks of code 

##### Step 6: Displaying the Custom Post

If you are following with the Smashing Magazine tutorial, skip down to “Displaying your content.”

We could create a custom archive page for our new custom post and then we will be able to view our posts in one central place (almost like a blog roll for our custom post type).

However, WordPress will automatically route us to an archive of our posts if we use the name of our post type  (Links) at the end of the URL for our WordPress site (http://www.mysite.com/links). It will automatically use our archive.php file. The routing sets the data context to our custom posts. 

If we wanted to create a custom archive page (which would be pretty reasonable) then you could simply create a PHP document named ‘archive-links.php’ or if you have a different name of the custom post it would be ‘archive-[custom-post-name].php’, and then add the appropriate code (probably copied from the existing archive.php file and then modified).

### Custom Page Templates

[WordPress Codex - Page Templates](http://codex.wordpress.org/Page_Templates)

The Tuts+ Tutorial below gives a great account of a use case for custom page templates.

	“A perfect example of a popular use for a custom page template is a ‘full-width’ page. A vast majority of WordPress templates have two or three columns: one ‘main content’ column where post/page content is held, and one or two sidebars that display widgets and calls to action. Sometimes a user will want to take advantage of the full-width of the container those columns are held within, and choose to omit the sidebar column(s) in favor of increasing the size of the ‘main content’ column. Pages that feature media such as image galleries or videos will often benefit from this type of custom page template.”

[Tuts+ - Creating Custom Page Templates ](http://codex.wordpress.org/Page_Templates)

As a sidenote, sometimes a conditional statement or a custom field could serve you better than creating an entire new template page. Custom page templates are more useful for layout type customization while conditional statements and custom fields can ensure that you have content displaying where you want it too. 

For our custom page template, we are going to create a full width template.

#### Tutorial: Adding a Custom Page Template

##### Step 1: Create a file

The first step will just be to create a file in our template.

<p class="message">Create a ‘page_fullwidth.php’ file in your theme's root folder </p>

The naming conventions for page templates is often the word page, an underscore, and then the word describing the template. So I am going to create this file named “page_fullwidth.php.” This is not mandatory but it is good to remain within conventions. 

This file must be placed within your theme directory for WordPress to read it. 

##### Step 2: Add the Identifying Code to the Template File

The only mandatory part of a custom template file is this bit of code:

<p class="file-name">page_fullwidth.php</p>
```php 
<?php 
/* 
Template name: Full Width 
*/ 
?>  
```

This registers the custom template with WordPress automatically (it works simply and easily!)

Of course this alone will not work because it does not give any code for the content. The easiest way to fix this is to copy the page.php code, paste it in this custom page, and edit it from there.

##### Step 3: Copy the Page.php Code into our Custom Template

Just open up your page.php file and copy it into the page_fullwidth.php file. It should look like this now:

<p class="file-name">page_fullwidth.php</p>
```php 
<?php 
/* 
Template name: Full Width 
*/ 
?>
<?php get_header(); ?>
<section class="row">
	<div class="nine columns">
	<!-- BEGIN PAGE PHP -->
            <?php if (have_posts()) : 
                /* OUR DATA CONTEXT IS DEFINED  */
                while (have_posts()) : the_post(); ?> 
                    <h2><?php the_title(); ?></h2>
                    <?php the_content();
                endwhile;
            endif; ?>
	<!-- END PAGE PHP -->
	</div>
    <!-- Begin Sidebar Area -->
    <div class="three columns">
        <?php get_sidebar(); ?>
    </div>
    <!-- End Sidebar Area -->
</section>
<?php get_footer(); ?>  
```

###### Step 4: Make the Page Template Full Width

Our custom template is now identical to our default page template, so let’s make it into a full width template using our Skeleton framework and get rid of the sidebar. 

I am also going to add a custom class to the wrapper in case we want to make changes to the CSS for this page only. Adding a class in a template and rules in our CSS file allow us to keep our code separate and clean. 

<p class="file-name">page_fullwidth.php</p>
```php 
<?php 
/* 
Template name: Full Width 
*/ 
?>
<?php get_header(); ?>
<section class="row full-width-class">
	<div class="twelve columns">
	<!-- BEGIN PAGE PHP -->
            <?php if (have_posts()) : 
                /* OUR DATA CONTEXT IS DEFINED  */
                while (have_posts()) : the_post(); ?> 
                    <h2><?php the_title(); ?></h2>
                    <?php the_content();
                endwhile;
            endif; ?>
	<!-- END PAGE PHP -->
	</div>
</section>
<?php get_footer(); ?>  
```

###### Step 5: Save and Upload Files

We should upload the page_fullwidth.php file to our theme folder. 

###### Step 6: Enable the Page Template on our Site

The last step of the tutorial is to enable the template in an existing page. Let’s first create a page with some filler content ([Lorem Ipsum](http://www.lipsum.com/)). 

Next, let’s go to the Page editing page and change the Template under the “Page Attributes” panel to “Full Width.”

If you don’t see the “Page Attributes” panel, then you have to click on “Screen Options” at the top of the page and then check the “Page Attributes” box.   

You can apply the idea of a Custom Page Template to any number of other scenarios where layout needs to be modified.

## <a name="custom-fields">Using MetaData and Custom Fields</a>

Coming Soon!

https://codex.wordpress.org/Custom_Fields 

## <a name="shortcodes">Shortcodes</a>

Shortcodes are a great way to integrate high level functionality into the WordPress admin directly. Many plugins use shortcodes as a means for displaying their generated content. You can also use shortcodes as a means to integrate your own custom functionality into WordPress. 

From the WordPress Codex:

    The Shortcode API makes it easy to create shortcodes that support attributes like this:

    [gallery id="123" size="medium"]

    The API handles all the tricky parsing, eliminating the need for writing a custom regular expression for each shortcode. Helper functions are included for setting and fetching default attributes. The API supports both self-closing and enclosing shortcodes.

[https://codex.wordpress.org/Shortcode_API](https://codex.wordpress.org/Shortcode_API)

If you see a snippet of code in WordPress that is surrounded by two brackets (“[ ]”) then it is likely that you are dealing with a shortcode. The way they are used are defined by the function that created it. 

Further down in the jQuery slider tutorial we will briefly include a mechanism to use shortcodes so you can see a tangible example. 

## <a name="integrating-outside-resources">Integrating Outside Resources</a>

In Chapter 7 we discussed the ways to link to a CSS or JavaScript file in WordPress. 

There are three ways to link to “outside resources” in WordPress:

Use a link in the header
(For CSS) Use an @import in the stylesheet
Use WordPress to enqueue the files and to handle dependencies. 

Each of these methods has it ups and downs. Each of these methods has a compelling use case and when you are linking to files you should consider which method is best. 

**Linking in the header** is the most common and oldest way of integrating outside resources into the web page. This generally looks like this:

```html
<script src=”javascript.js:></script>
<!-- OR -->
<link rel="stylesheet" type="text/css" href="stylesheet" />

```

The other way to do this is to use an **@import in the stylesheet** for CSS files. This usually looks like this:

```css
@import url(stylesheet.css);
```

The third way, **enqueuing files**, was covered in the previous chapter and is a convenient way to organize files and deal with dependencies, but is a bit more time intensive with a slightly higher learning curve. 

As an example, I will demonstrate how to add a custom font using [Google Fonts](https://www.google.com/fonts). 

### Tutorial: Adding a Custom Font

#### Step 1: Find the Font you Want

Google Fonts is a good place to find free fonts in a wide variety. There are numerous other services which allow for font integration (most paid), but for this tutorial I am going to use Google Fonts. 

Navigate to [Google Fonts](https://www.google.com/fonts) and select a font you like. After you select the font, click on “Review” towards the bottom. If everything seems okay, click “Use.” Check the boxes for the variety of weights and variants that you will use. Remember that the more you choose the more site speed impact the font will have. 

#### Step 2: Link to the Font in Your Stylesheet

Google Fonts gives you three ways to link to the font:

The header linking method
The @import method (Which we will use)
The JavaScript insert method (probably the better choice…)

Copy the @import code from the “Use” tab and paste it into your style.css file. Here is an example of what it should look like:

<p class="file-name">style.css</p>
```css
@import url(http://fonts.googleapis.com/css?family=Open+Sans:400,600,700,300);
```

#### Step 3: Add the Font Family to your Webpage

Assuming you will only want one font for your whole site, let’s add the font to our body in our style file.

<p class="file-name">style.css</p>
```css
body, html {
 font-family: 'Open Sans', sans-serif;
}
```

You can find the font-family code on the Google Fonts page. They make it as easy as possible for you. 

#### Step 4: Save and Upload


## <a name="child-and-parent-themes">Child and Parent Themes</a>

The concept of a child and parent theme is generally available in almost every CMS. In WordPress they are a useful tool to maintaining structure in a template where there is multiple versions of a site with one overlying template. 

We won't over-discuss Child and Parent Themes in this book, but will have a slight overview for informational purposes. It is important to know about from a conceptual standpoint. 

A child theme is essentially a separate file structure that references a parent theme.  Child themes were created for making modifications to a theme, specifically one that is commercial in nature. The parent will be a fully operational theme in and of itself, but the child theme will modify the styles/structure of the parent theme for its own purposes. 

[Child Themes](http://codex.wordpress.org/Child_Themes)

[Tuts+ - Child Themes in WordPress](http://wp.tutsplus.com/tutorials/theme-development/child-themes-basics-and-creating-child-themes-in-wordpress/?search_index=7)

Using a child theme has many advantages, including:

- Child themes can be a great way to ensure that you are not modifying a theme that would otherwise be updated to a point where it will become un-updatable.  

- Allows the user to do any number of things – including distinct multisite features – while allowing the admin to maintain a strong template infrastructure.

- If we create a child theme we will not need to create a new theme from scratch which will translate into faster development time.

There are a lot of free and commercial theme frameworks available which give us a wide range of functionality will not need too much customization in our child themes.

If we use child themes as opposed to directly modifying the parent theme to suit our needs, we will easily be able to upgrade to a newer version of the parent theme without losing any of our customization.

A lot of times parent themes not only provide the design but also include widgets and plugins which can be directly used if we create a child theme of that parent theme.

If it’s a popular parent theme you are using, either free or commercial, it’s more likely to have fewer bugs and be more stable as it has been used and tested on multiple sites.
Some of the disadvantages of child themes are:

- A lot of the theme frameworks are very extensive and provide a lot of features which might not be useful to you. This makes frameworks complex and it would increase the time taken to learn and master the framework. 

- It may also affect performance with multiple server side lookups and redundant or unused files. 

In the more general outlook of CMSs, the idea of having themes that are subservient to a main theme is extremely common.  From a conceptual standpoint, WordPress itself is the parent and the theme is the child – though they obviously perform different functions.  With many commercial CMSs though, the parent may hold many styles and functions that will need to be modified.  Considering the structure of a CMS with the idea of parent/child or master/servant in mind will help you understand where to make changes and how they may affect a larger scheme. 


## <a name="css-based-tutorials">CSS Based Tutorials</a>

### Tutorial: Styling the Search Bar

The search bar is a really important tool for websites from a usability and functional UI standpoint. If you have a moderate to large size site, users will likely rely on this as one of the primary means of finding information. 

Let’s work on styling the search bar on our site so that it is a bit prettier and also so that you will know how to style it in your own way later on. 

A lot of the code for this tutorial comes from the [WordPress Codex entry for get_search_form.](https://codex.wordpress.org/Function_Reference/get_search_form)

#### Step One: Locate the Search Bar and Create a File to Modify it

First, let’s note where the search bar is located. Earlier when we created our theme, we included it in the header. 

WordPress is loading the search form based off of its default settings. In order to create a better search form that suits our needs, we are going to recreate the search form and include it in our theme folder. 

    Create “searchform.php” file and put it in your theme’s root directory

#### Step Two: Add Code and Modify searchform.php

WordPress will now use our newly created searchform.php in place of the default search form. Let’s add some code so that something will start to show up.

<p class="file-name">searchform.php</p>
```html
<form role="search" method="get" class="search-form" action="' . esc_url(home_url('/')) . '">
    <label>
        <span class="screen-reader-text">' . _x('Search for:', 'label') . '</span>
        <input type="search" class="search-field" placeholder="Search" value="' . get_search_query() . '" name="s" title="' . esc_attr_x('Search for:', 'label') . '" />
    </label>
    <input type="submit" class="search-submit" value="'. esc_attr_x('Search', 'submit button') .'" />
</form>
```

This is the default for HTML5 in WordPress. Knowing what is happening here could be interesting from a knowledge standpoint so feel free to [delve into the GET method and how it works in search forms.](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms/Sending_and_retrieving_form_data)

#### Step Three: Modifying the Search Form for our Purposes

The code for the Search Form is pretty solid for our purposes. We are going to add a CSS class to the code so that we can target it in the way we want. 

<p class="file-name">searchform.php</p>
```html
<form role="search" method="get" class="search-form wie-search-form" action="' . esc_url( home_url('/')) . '">
 <label>
  <span class="screen-reader-text">' . _x( 'Search for:', 'label' ) . '</span>
  <input type="search" class="search-field" placeholder="Search" value="' . get_search_query() . '" name="s" title="' . esc_attr_x('Search for:','label') . '" />
 </label>
 <input type="submit" class="search-submit" value="'. esc_attr_x('Search', 'submit button') .'" />
</form>
```

Now that we have the classes identified, we can add CSS to make it look how we want. I am going to just get rid of the screen reader text in a way that will still allow it to be actually readable by a screen reader but not displayed by the browser to the average viewer. Note that this way of getting rid of content on a page is prefered to using display:none;. 

<p class="file-name">style.css</p>
```css
.wie-search-form .screen-reader-text {
    position: absolute;
    left: -999em;
    width: 1em;
    overflow: hidden;
}

```

#### Step Four: Save and Upload

### Tutorial: Sticky Header Bar

A very common element on websites is a sticky element on the page. We are going to use CSS only to make our header attach to the top of the page no matter what. There are more sophisticated methods using JavaScript, but for our needs we can get away with just using a few lines of CSS. 

Essentially, we are going to use CSS’s positional elements (fixed) and then add values to the header element to make it fit in a way that is pleasing from a visual and UI standpoint. 

#### Step One: Wrap the Header

<p class="file-name">header.php</p>
```html
<div class=”header-container”>
<!-- Put your header content here -->

</div>
```

#### Step Two: Modify the CSS to Make it Work

<p class="file-name">style.css</p>
```css
.header-container {
   width:100%;
   position:fixed;
   top:0px;
   z-index:2;
}
```

Each rule here has it’s own purpose: The width makes sure it takes up the entire width of the window; the position: fixed tells the browser to make the div fix to its location on the screen; top:0px tells the distance from the top of the browser and; z-index is the value of the z parameter which control which items are on top of other items.(the default is 1 so a 2 would make it on top of everything else). 

Step Three: Add Other Styling to the Header

You can feel free to add other styling to the header to make sure it looks how you want. Here are some “ideas:”

<p class="file-name">style.css</p>
```css
header {
   height:50px;
   background:#F0F0F0;
   border-bottom:1px solid #CCC;
   margin:0px auto;
}
```
#### Step Four: Save and Upload

## <a name="adding-functionality">Adding Advanced Functionality</a>

This area is for various tutorials related to WordPress functionality. 

### Tutorial: Creating a separate blog page

If you want to use WordPress as a fully functional CMS, you will probably need to separate the blog portion of WordPress into a separate area. There are ways to do this:

The WordPress built in way (covered here: [http://www.wpbeginner.com/wp-tutorials/how-to-create-a-separate-page-for-blog-posts-in-wordpress/](http://www.wpbeginner.com/wp-tutorials/how-to-create-a-separate-page-for-blog-posts-in-wordpress/) which allows you to reconfigure your main page as a static page and your blog page as an internal page that can be queried. 
Create a post query in a custom page and then assign that value to an existing page (covered here: [https://upthemes.com/blog/2011/07/how-to-build-a-custom-page-template-for-blog-posts/](https://upthemes.com/blog/2011/07/how-to-build-a-custom-page-template-for-blog-posts/)

We are going to the second option because I prefer it as it is less confusing (for me at least).

#### Step One: Create a Custom Page

Earlier in this chapter we learned how to create a custom page template. Let’s go ahead and create a new file and populate it with our bare minimum code.

    Create a file titled “blog_custom_page.php”

Let’s copy page.php into this file. This will save us time and ensure we have some uniformity to start out with. 

<p class="file-name">blog_custom_page.php</p>
```php
<?php get_header(); ?>
    <div class="row">
        <div class="twelve columns">
            <?php if (have_posts()) : 
                while (have_posts()) : the_post(); ?> 
                    <h2><?php the_title(); ?></h2>
                    <?php the_content();
                endwhile;
            endif; ?>
        </div>
    </div>
<?php get_footer(); ?>
```

#### Step Two: Add the Custom Page Requirements

Since this is technically a custom page template, we need to follow the formalities of that. 

<p class="file-name">blog_custom_page.php</p>
```php
/*
Template Name: Blog Posts
*/
<?php get_header(); ?>
    <div class="row">
        <div class="twelve columns">
            <?php if (have_posts()) : 
                while (have_posts()) : the_post(); ?> 
                    <h2><?php the_title(); ?></h2>
                    <?php the_content();
                endwhile;
            endif; ?>
        </div>
    </div>
<?php get_footer(); ?>
```

#### Step Three: Adding a Custom Query for Posts

The next step is basically about replacing the default code in the page with a custom query for all blog posts. This is a lot like the main index.php page except we need to be explicit about the data context and making sure we handle it correctly. 

<p class="file-name">blog_custom_page.php</p>
```php
/*
Template Name: Blog Posts
*/
<?php get_header(); ?>
<?php query_posts('post_type=post&post_status=publish&posts_per_page=10&paged='. get_query_var('paged')); ?>
    <div class="row">
        <div class="twelve columns">
            <?php if (have_posts()) : 
                while (have_posts()) : the_post(); ?> 
                    <h2><?php the_title(); ?></h2>
                    <?php the_content();
                endwhile;
            endif; ?>
        </div>
    </div>
<?php get_footer(); ?>
```
If you look at the code closely you can see that the query loads the 10 most recent published pages. It also allows for pagination. 

#### Step Four: Add Navigational Links

We are going to want to add some navigational links into our code so that this blog page can do everything we need it to as a separate functioning blog roll. 

<p class="file-name">blog_custom_page.php</p>
```php
/*
Template Name: Blog Posts
*/
<?php get_header(); ?>
<?php query_posts('post_type=post&post_status=publish&posts_per_page=10&paged='. get_query_var('paged')); ?>
    <div class="row">
        <div class="twelve columns">
            <?php if (have_posts()) : 
                while (have_posts()) : the_post(); ?> 
                    <h2><?php the_title(); ?></h2>
                    <?php the_content();
                endwhile; ?>
            <!-- Navigation -->
            <div class="navigation">
                <span class="newer"><?php previous_posts_link(__('« Newer','example')) ?></span> <span class="older"><?php next_posts_link(__('Older »','example')) ?></span>
            </div>
           <?php endif; ?>
        </div>
    </div>
<?php get_footer(); ?>
```

We put it at the end of our while loop because we want it to be outside of the loop, but still inside of the if statement about showing posts. If there are no posts then there will be no pagination. 

#### Step Five: Reset the Query

We are going to want to reset the query so that it knows when to stop.  

<p class="file-name">blog_custom_page.php</p>
```php
/*
Template Name: Blog Posts
*/
<?php get_header(); ?>
<?php query_posts('post_type=post&post_status=publish&posts_per_page=10&paged='. get_query_var('paged')); ?>
    <div class="row">
        <div class="twelve columns">
            <?php if (have_posts()) : 
                while (have_posts()) : the_post(); ?> 
                    <h2><?php the_title(); ?></h2>
                    <?php the_content();
                endwhile; ?>
                <div class="navigation">
                    <span class="newer"><?php previous_posts_link(__('« Newer','example')) ?></span> <span class="older"><?php next_posts_link(__('Older »','example')) ?></span>
                </div>
            <?php endif; 
            wp_reset_query(); ?>
        </div>
    </div>
<?php get_footer(); ?>
```

#### Step Six: Making it a Fuller, More Useful Blog Page

So the code above is sufficient for handling all of the needs of the blog page. I am going to add some other code just for error handling and for stylistic efforts. Read through the code so you understand what is happening at each stage. 

<p class="file-name">blog_custom_page.php</p>
```php
/*
Template Name: Blog Posts
*/
<?php get_header(); ?>
<?php query_posts('post_type=post&post_status=publish&posts_per_page=10&paged='. get_query_var('paged')); ?>
    <div class="row">
        <div class="twelve columns">
            <?php if (have_posts()) : 
                while (have_posts()) : the_post(); ?> 
                    <a href="<?php the_permalink(); ?>"><?php the_post_thumbnail(); ?></a>
                    <h3><a href="<?php the_permalink(); ?>"><?php the_title(); ?></a></h3>
                    <?php the_excerpt(__('Continue reading »','example'));
                endwhile; ?>
                <div class="navigation">
                    <span class="newer"><?php previous_posts_link(__('« Newer','example')) ?></span> <span class="older"><?php next_posts_link(__('Older »','example')) ?></span>
                </div>
                <?php else: ?>
                <div class="404-section">
                    <p><?php _e('None found.','example'); ?></p>
                </div>
            <?php endif; wp_reset_query(); ?>
        </div>
    </div>
<?php get_footer(); ?>
```

Note how we added some 404 handling and better outlined the post content that will be displayed. 

#### Step Seven: Save and Upload


### Tutorial: Integrating Breadcrumbs into your WordPress pages

