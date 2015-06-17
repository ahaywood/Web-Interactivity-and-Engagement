---
layout: page
title: Chapter 8&#58; Advanced  WordPress Customization
---

## Table of Contents

* [Custom Posts and Pages](#)
	* Custom Posts
		* Tutorial: Adding Custom Post Type
	* Custom Page Templates
		* Tutorial: Adding a Custom Page Template
* [Custom Fields](#)
	* Tutorial: Using Custom Fields
* [Shortcodes](#)
	* CSS Based Tutorials
		* Tutorial: Styling the Search Bar
* [Integrating Outside Resources](#)
	* Tutorial: Custom Fonts
* [Child and Parent Themes](#)
* [Using MetaData](#)
	* Tutorial: Custom Fields
* [Adding Functionality](#)
	* Tutorial: Proper way to Link to CSS Files
	* Tutorial: Creating a Separate Page for Blog Posts
	* Tutorial: Integrating Breadcrumbs into your WordPress pages

## Custom Posts and Pages

We know that WordPress has two ways to display content: Pages and Posts. As a reminder, pages are more permanent and posts and meant to be time-based. 

We also know that the page.php file is for displaying pages and the single.php file is for displaying posts. Well, what if we want to make new types of posts (for organization reasons or as new types of content that are outside of the scope of a “blog post.”)? What if we want to have different ways to display page content?

This is where custom posts and pages come into play. There are plenty of scenarios where you may need to go away from the typical look of your page or post. Adding custom page or post templates allows you to add multiple looks for different types of posts or pages. The concept behind their customization is very different and will be useful for entirely different reasons. 

### Custom Posts

A Custom Post will be a completely new content type in the WordPress CMS. The usefulness of this functionality cannot be understated, but it is complicated and can be confusing.

[WordPress Codex - Custom Post Types](https://codex.wordpress.org/Post_Types#Custom_Post_Types)

[Smashing Magazine - The Complete Guide To Custom Post Types](http://www.smashingmagazine.com/2012/11/08/complete-guide-custom-post-types/)

*Can you think of some uses for a custom post type?*

#### Tutorial: Adding Custom Post Type

**Coming Soon**

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

