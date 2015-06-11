---
layout: page
title: Chapter 3&#58; Templating & Layouts
---

## Table of Contents

* [Templating and CMSs](#templating-and-cmss)
* [Creating a Blank WordPress Template](#creating-a-blank-wordpress-template)
	* Tutorial: Creating a WordPress Template
	* Tutorial: Enabling the Blank Template
* [Grid-Based Layouts](#grid-based-layouts)
	* Linking to Files in a Template
	* Tutorial: Implementing a Grid System
* [Separating Template Files](#separating-template-files)
	* Tutorial: Header and Footer
* [WordPress and PHP Templates](#wordpress-and-php-templates)
	* Tutorial: Adding the Loop
* [Internal Pages and Posts](#internal-pages-and-posts)
	* Data Context
	* Tutorial: Pages Template
	* Tutorial: Posts Template
	* Tutorial: Sidebars Includes
* [Introduction to Styling WordPress](#introduction-to-styling-wordpress)

## <a name="templating-and-cmss">Templating and CMSs</a>

**A Template** is defined as "anything that determines or serves as a pattern; a model." - [http://dictionary.reference.com/browse/template](http://dictionary.reference.com/browse/template)

This concept of a "pattern" or a "model" is important to thinking about HOW templates work within a CMS, including WordPress.  

Most CMSs allow you to create a visual identity for your site outside of the default settings. This is so that the CMS itself can be expanded over a broader market than just internal audiences. 

The practical reason for having "templates" exist on top of a CMS is somewhat obvious - to separate the functional aspects of the software environment from the visual aspects. The software provider (CMS creator) will want to make sure their software remains stable, but the customer (person using the CMS) will want to make changes so that the CMS is their own.

This dynamic between software stability and visual uniqueness is played out in every commercial software environment and the outcome is nearly always different. It is no different with CMSs (both open source and commercial). The level of permission that the designer will have to make changes to the CMS vary greatly. For this reason, the needs of a person to make changes to a template should be taken into account when deciding on which CMS to choose. Additionally, knowing your designer's ability to make changes could make the limited changes be a selling point. 
 
Another practical value of a template is that it allows uniformity in the presentation of content. This "pattern" philosophy lets the content manager and the designer maintain uniformity/consistency throughout the template. 

*Why do you think uniformity is important?*

So now that we know why nearly every CMS allows some level of templating, let's explore WordPress's extremely generous templating engine. 

## <a name="creating-a-blank-wordpress-template">Creating a Blank WordPress Template</a>

Since we want to understand WordPress from a fundamental level, we are going to start by walking through the primary display mechanism of the CMS, a template. 

The WordPress template holds all of the files for content display throughout the site. Without a template, WordPress wouldn't know how to display any of the information that is input through the Dashboard. It also wouldn't know what CSS or JavaScript to add to modify the content it displays. 

Every WordPress template needs certain files to make sure that the content is displayed.

Here is a list of the files you will add in the upcoming lessons for creating a template:

* **Index.php:** By default, the front page of your WordPress site. 

* **Header.php:** The included file that holds your header section of your template.

* **Footer.php:** The included file that holds the footer section of your template.

* **Style.css:** The CSS file that holds your base CSS styles.

* **Functions.php:** Houses all of your PHP Functions that you add to make WordPress do more, or to enable things WordPress already intends to do.

* **Page.php:** The template file for your pages.

* **Single.php:** The template file for your posts.

* **Archive.php:** A template file that displays groupings of past courses.

* **Search.php:** The template file that displays search results from using WordPress' built in search

* **404.php:** The page that will display if there is a 404 error (page not found).

All of these files should seem fairly simple (with the functions file being the possible exception). You can actually create a template using only the index.php file and the style.css file - but having these additional files allows WordPress to function to its fullest power. 

### Blank Templates Generally

Very few CMSs will come with completely blank templates. Even WordPress provides you will several fully functional templates in case you have limited programming experience. 

In practice, you will never code a template from scratch. In fact, the only reason you would want to do that is because 1) you are taking a class about learning the concepts of CMSs, or 2) you make a LOT of templates for a specific CMS and making sure the specific details you rely on are included and nothing else is important to you.

Even with our "from scratch" approach, I will still utilize external frameworks to add functionality (see Components). Many CMSs have preferred frameworks that they integrate well with, so sometimes knowing a CMS also includes knowing certain frameworks too. 

### Tutorial: Creating a WordPress Template
Making a template is a relatively easy process. The difficult part is making it look how you want it to. 

#### Step 1: Create a folder for your blank template

This step is the most important part of the template creation process. This blank template folder will contain all of your theme files and be the only folder you will upload to your server at any point in this project creation process. 

I often will use a "development" folder off of my desktop that I work in. Make the folder easy to use.

<p class="message">Create folder titled "Firstname_Lastname_Blank_Template"</p>

#### Step 2: Create an index.php and a style.css file

This step of this template creation should be very simple to you, since it should look like something you've done plenty of times before. We aren't even going to add a bit of PHP to the template until we already have it activated and running. 

Open your text editor and create two files:

<p class="message">Create file titled "index.php" and save it in your Blank Template folder</p>
<p class="message">Create file titled "style.css" and save it in your Blank Template folder</p>

#### Step 3: Populate your index.php file

Let's remember something we already learned: PHP is merely a means to generate content to go inside of HTML. This means that PHP will work seamlessly with HTML already and any PHP file can have HTML, CSS, JavaScript, and any other language that a browser will parse. The only thing a PHP file cares about is the code inside of the <?php … ?> brackets. For this reason, we aren't going to write a bit of PHP in the index.php file and that's okay - because the server will see that there is no PHP in the file and just return the HTML we write to the browser. 

You may recognize this next bit of code we are going to add to the index.php file:

<p class="file-name">index.php</p>
``` html

<!DOCTYPE html>
<html>
<head>
<title></title>
</head>
<body>
</body>
</html>

```

Notice anything weird here? You shouldn't. It is the basic setup for any HTML file you will ever create. 

Let's add some text in the 'body' section of the page:

<p class="file-name">index.php</p>
``` html
<body>
	<h1>Blank WordPress Template</h1>
	<p>This is my WordPress template.</p>
</body>

```

Save your file. Let's move to the style.css file

#### Step 4: Populate your style.css file

We don't cover CSS much in this course because it is assumed that you already understand how to use it or to find resources that will help you be able to use it. I will occasionally include styling into a tutorial so that it is easier to understand the interplay of templating, PHP, and CSS. 

WordPress gets the information about the template (metadata) from the style.css file. For this reason, we have to add the style.css file and some commented out information for our template to show up. I included some CSS so that we can get started.

<p class="file-name">style.css</p>
``` css

/*
Theme Name: FirstName Blank Theme
Theme URI: URL for FirstName Blank
Author: FirstName LastName
Description: Blank theme for WIE course
Version: 0.1
License: Open
Text Domain: firstname_lastname_blank_template
*/

*{
	color: #000000;
	font-size: 14px;
	line-height: 16px;
}
```
Make sure you change the places in that commented out section that seem obvious. 

Save your style.css file.

#### Step 5: Upload your theme folder

We covered where everything is located in WordPress in the first chapter. If you are ever unsure about what belongs where, reference that information. 

The last step of creating a bare bones theme will to upload it to our server. As a reminder, you will upload all themes to the themes folder in the wp-content folder. Anytime you make a change to a file in WordPress and want it to go live in your template, you will upload it to the theme folder in your wp-content folder. 

### Tutorial: Activating a WordPress Template

This will be a relatively easy process which hardly warrants a tutorial, but since you are very early on with your experience with the WordPress admin, I wanted to make sure you were aware of how to do this. 

#### Step 1: Log into your WordPress admin

To log into WordPress, visit the URL of your site (http://www.yoursite.com/wordpress-folder) and then go to the log in page (can be found at (http://www.yoursite.com/wordpress-folder/wp-admin or http://www.yoursite.com/wordpress-folder/wp-login.php). 

#### Step 2: Go to Appearance -> Themes

While in your Dashboard, go to the Appearance navigation item on the left hand side and then go to the Themes item. 

You should be looking at a list of several different themes to enable, including one without a picture called "Firstname Blank Theme."

#### Step 3: Activate the theme

Click on "Activate" on your theme.

#### Step 4: Make sure it works

Go to your site URL to verify that it has been enabled. You should see ONLY the text you put in between the body section. This is a pretty reasonable thing to happen because it is the only thing you told WordPress to display. 

WordPress isn't doing anything on the pages because you didn't tell it to do anything for you. Don't worry though, we will be adding WordPress functionality very shortly.

## <a name="grid-based-layouts">Grid Based Layouts</a>

A majority of modern web sites use a grid to determine where to place content. The advantages to a grid based layout is that you can place items on your site in a uniform manner. Many of the grid frameworks also make it very easy to have a fully responsible site with very little work.

If you have a good amount of experience with grid based layouts, this following section may be overly simple for you. I am including it because 1) it is not obvious on its own and 2) MANY mistakes are made by misusing a grid system.

### Using a Grid

For this class, we are going to use [Skeleton](http://getskeleton.com/) as our framework for responsive design and for basic styles. We are using this because it doesn't have a lot of code and will allow you to customize without having any additional styles getting in the way. 

Many other grid systems use the same methodology for laying out a site as Skeleton. Here is how Skeleton uses it:

``` html
<div class="container">

  <div class="row">
    <div class="six columns">Content for 1/2 width column</div>
    <div class="six columns">Content for 1/2 width column</div>
  </div>

  <div class="row">
    <div class="four columns">Content for 1/3 width column</div>
    <div class="five columns">Content for 5/12 width column</div>
    <div class="three columns">Content for 1/4 width column</div>
  </div>

</div>
```

If read through the code, you can see that Skeleton uses a 'div class="container"' to hold everything inside of it. Then inside of the container, the 'div class="row"' holds the 'div class="# columns"'. Lastly, you see that the divs that hold the columns have two classes: a number class and the "columns" class. The number class is based on there being 12 parts to the full width. You can see how I used different numbers in the number class to demonstrate how it works. This will certainly make more sense once you apply it.

Simplifying what is happening above, you will see that the essential syntax is this (all HTML taken out for understanding purposes):

	Container
		Row
			Column
		Row
			Column
			Column
			Column

You may also notice that this seems very similar to HTML tables:

``` html
<table>
	<tr>
		<td></td>
	</tr>
	<tr>
		<td></td>
		<td></td>
		<td></td>
</tr>
</table>		
```

The idea of a "table based layout" has long since gone, but these responsive frameworks have taken the best parts of it without having all of the terrible table limitations. 

## <a name="linking-to-files-in-a-template">Linking to Files in a Template</a>

Something you are probably more than familiar with, linking to files in a template changes slightly after you begin using a CMS. In WordPress, you can choose to link to external files through your Functions file, or by putting it in the head section, like you would with a regular HTML page. We will cover the more advanced file querying mechanism in later chapters.

As a review, here is the simple, HTML method for linking to a file:

```html
<!-- Link to a CSS file --> 
<link rel="stylesheet" type="text/css" href="style.css" />

<!-- Link to a JavaScript file --> 
<script src="custom.js"></script>

```

Now we are going to write our very first PHP for WordPress so that we can load something dynamic. We are going to link to our style.css file and the skeleton.css framework file.

<p class="file-name">index.php:</p>

```html
<head>
<!-- Links to our Style.css file -->
	<link rel="stylesheet" type="text/css" href="<?php bloginfo('stylesheet_url'); ?>" />
</head>
```

The '<?php bloginfo('stylesheet_url')_; ?>' portion of the code we added contains a built in WordPress function (bloginfo()) and a parameter that the function will use ('stylesheet_url'). The purpose of this function is to link to your default stylesheet in a dynamic way so that if you move your theme around to different servers, the link will always work relatively. 

Next we will create a folder inside of our theme folder (firstname_blank_theme) named "css". Then download the Skeleton CSS file and put that file inside of the firstname_blank_theme/css folder. 

We are going to store all of our CSS files EXCEPT our style.css file in this folder. The style.css file needs to be in the theme's root directory because it contains administrative information. 

Lastly we will add an @import to our style.css file for our Skeleton CSS file (downloaded from the Skeleton site.

<p class="file-name">style.css:</p>
``` css

@import url("css/my_custom_style.css");

```
When we save and upload our index and style.css file you should be able to see that they are loading. 

### Tutorial: Implementing a Grid System

This tutorial will show you how to implement the Skeleton Grid system. This will make your site responsive and the simplified layout should help you with your development. 

Let's remember what our current index.php page looks like:

<p class="file-name">index.php:</p>
```html

<!DOCTYPE html>
<html>
	<head>
		<title></title>
	<!-- Links to our Style.css file -->
		<link rel="stylesheet" type="text/css" href="<?php bloginfo('stylesheet_url'); ?>" />
	</head>
	<body>
		<h1>Blank WordPress Template</h1>
		<p>This is my WordPress template.</p>
	</body>
</html>

```
#### Step 1. Add HTML 5 Sytnax

Let's add some more HTML5 syntax so that we can have a blank template that is fuller and richer. 

<p class="file-name">index.php:</p>
```html
<!DOCTYPE html>
<html>
	<head>
		<title></title>
		<!-- Links to our Style.css file -->
		<link rel="stylesheet" type="text/css" href="<?php bloginfo('stylesheet_url'); ?>" />
	</head>
	<body>
		<header>
			<h1>Blank WordPress Template</h1>
			<p>This is my WordPress template.</p>
		</header>
		<section>
			<p>Body content goes here.</p>
		</section>
		<footer>
			<p>Footer content goes here.</p>
		</footer>
	</body>
</html>

```
Basically we added 'header', 'footer' and some filler text. However, the site makes more sense from a layout perspective. If you upload the index.php file to your server now, you will see the changes as you have made them.

#### Step 2. Add Skeleton grid syntax

Next, let's implement the Skeleton grid system as we learned above. Note how we integrate the HTML5 elements as if they were divs. This is okay!

<p class="file-name">index.php:</p>
```html
<!DOCTYPE html>
<html>
	<head>
		<title></title>
		<!-- Links to our Style.css file -->
		<link rel="stylesheet" type="text/css" href="<?php bloginfo('stylesheet_url'); ?>" />
	</head>
	<body>
		<div class="container">
			<header class="row">
				<div class="twelve columns">
					<h1>Blank WordPress Template</h1>
					<p>This is my WordPress template.</p>
				</div>
			</header>
			<section class="row">
				<div class="twelve columns">
					<p>Body content goes here.</p>
				</div>
			</section>
			<footer class="row">
				<div class="twelve columns">
					<p>Footer content goes here.</p>
				</div>
			</footer>
		</div> <!-- ends container -->
	</body>
</html>
```

Do you see how the container class has been added and then the site was laid out using rows and columns? We added a columns div to each row because it is syntactically important to the grid system. Using the embedded methodology of the grid system is helpful, but you must strictly use it for it to work. 

#### Step 3. Save and upload files

If you upload the index.php file to your server, you should now have a responsive website!

## <a name="separating-template-files">Separating Template Files</a>

When I say separating template files I mean the process of splitting up one template file into separate parts for the purpose of reusing code dynamically.  There is both a technical and design purpose in separating template files. 

The technical reason for separating template files is to reduce file size and to ensure that there is file consistency.

The design reason for separating template files is for consistency and ease of use of a templating engine. 

In the below tutorial we split off the header and the footer file. The reason for this is because we are going to want the header and the footer to be consistent throughout the site, but we are going to want the other template files to be different. By grouping the header and footer into separate files, we can easily reuse that code consistently.

### Tutorial: Header and Footer

If we take our code from above, it is easy to see that there are clear differences between the sections (mostly thanks to HTML5 syntax). I have added comments in the below code for you to see where we are going to chop up the index.php file. 

#### Step 1. Add Comments for Separation

<p class="file-name">index.php:</p>
```html
<!DOCTYPE html>
<html>
	<head>
		<title></title>
		<!-- Links to our Style.css file -->
		<link rel="stylesheet" type="text/css" href="<?php bloginfo('stylesheet_url'); ?>" />
	</head>
	<body>
		<div class="container">
			<header class="row">
				<div class="twelve columns">
					<h1>Blank WordPress Template</h1>
					<p>This is my WordPress template.</p>
				</div>
			</header>
			<!-- END OF HEADER - BEGIN SECTION CONTENT -->
			<section class="row">
				<div class="twelve columns">
					<p>Body content goes here.</p>
				</div>
			</section>
			<!-- BEGINNING OF FOOTER - END SECTION CONTENT -->
			<footer class="row">
				<div class="twelve columns">
					<p>Footer content goes here.</p>
				</div>
			</footer>
		</div> <!-- ends container -->
	</body>
</html>
```
#### Step 2. Create Header and Footer file

Next, let's create two files:
<p class="message">Create file titled "header.php" and save it in your Blank Template folder</p>
<p class="message">Create file titled "footer.php" and save it in your Blank Template folder</p>

#### Step 3. Chop up the index.php file

<p class="file-name">header.php:</p>

```html
<!DOCTYPE html>
<html>
	<head>
		<title></title>
		<!-- Links to our Style.css file -->
		<link rel="stylesheet" type="text/css" href="<?php bloginfo('stylesheet_url'); ?>" />
	</head>
	<body>
		<div class="container">
			<header class="row">
				<div class="twelve columns">
					<h1>Blank WordPress Template</h1>
					<h2>This is my WordPress template.</h2>
				</div>
			</header>
<!-- END OF HEADER - BEGIN SECTION CONTENT -->
```

<p class="file-name">index.php:</p>

```html
			<section class="row">
				<div class="twelve columns">
					<p>Body content goes here.</p>
				</div>
			</section>
```

<p class="file-name">footer.php:</p>
```html
<!-- BEGINNING OF FOOTER - END SECTION CONTENT -->
			<footer class="row">
				<div class="twelve columns">
					<p>Footer content goes here.</p>
				</div>
			</footer>
		</div> <!-- ends container -->
	</body>
</html>
```

#### Step 4. Link to the header and footer

Next we add the WordPress functions that link to the header and footer. These two PHP functions are built in to the WordPress syntax and can be found in the WordPress Codex if you want to learn more about them.

<p class="file-name">index.php:</p>
```html
<?php get_header(); ?>
	<section class="row">
		<div class="twelve columns">
			<p>Body content goes here.</p>
		</div>
	</section>
<?php get_footer(); ?>
```

#### Step 5. Add additional WordPress functions to enhance functionality

WordPress needs some additional functions in the header and footer to make sure that some added features are included. One of these is the Dockbar that follows you throughout your site if you are logged in. Another is for various functional reasons that are not worth getting into - just do it.

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
		<div class="container">
			<header class="row">
				<div class="twelve columns">
					<h1>Blank WordPress Template</h1>
					<p>This is my WordPress template.</p>
				</div>
			</header>
<!-- END OF HEADER - BEGIN SECTION CONTENT -->
```

<p class="file-name">footer.php:</p>
```html
<!-- BEGINNING OF FOOTER - END SECTION CONTENT -->
			<footer class="row">
				<div class="twelve columns">
					<p>Footer content goes here.</p>
				</div>
			</footer>
		</div> <!-- ends container -->
	<?php wp_footer(); ?>
	</body>
</html>
```

#### Step 6. Make the Header Work Dynamically

Let's add some necessary items to our header now. We are going to add two built in WordPress functions to the header.php file where we are loading static content. 

<p class="file-name">header.php:</p>
``` html
<!DOCTYPE html>
<html>
	<head>
		<title></title>
<?php wp_head(); ?>
		<link rel="stylesheet" type="text/css" href="<?php bloginfo('stylesheet_url'); ?>" />
	</head>
	<body>
		<div class="container">
			<header class="row">
				<div class="twelve columns">
					<h1><?php bloginfo('name'); ?></h1>
					<p><?php bloginfo('description'); ?></p>
				</div>
			</header>
<!-- END OF HEADER - BEGIN SECTION CONTENT -->
```

Notice how we are using the bloginfo function that we used in the linking to the stylesheet, except we are using it here with different parameters inside the function. Instead of saying "Blank WordPress Template" we can now say whatever we want, from the WordPress admin. We changed nothing here but the text in between the 'h1' and 'p' tags because all we wanted to make happen was to have WordPress dynamically generate that content for us, not make it display differently. 

#### Step 7. Save and Upload

Double check that you did everything correctly by uploading the files to the server. Everything should look as it did before you separated the files. 

## <a name="wordpress-and-php-templates">WordPress and PHP Templates</a>

The only thing worth adding about WordPress and PHP that hasn't been said in an earlier chapter is that I want you to consider how we had a completely capable website without adding much, if any, PHP. Appreciating how a PHP file can function without any PHP but how an HTML file cannot function with PHP is an important concept to grasp with regard to back end programming generally.

### Tutorial: Adding the WordPress Loop

Now that we have done some PHP and have our index site split into three separate template files, let's add the actual functionality of WordPress so that we aren't just serving static content. 

#### Step 1: Create Five Posts of Content

Though this may seem tedious, it is important to have a subset of data to program off of. My suggestion is to make 5 posts with different headings and plenty of body text. You will do this by going into the Dashboard, clicking on "Posts" and then "Add New." For each one, put a different heading and some filler content

For example:

	My First Post

	Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

#### Step 2: Adding the Loop

We already have our Index.php file split up so that it dynamically loads the header and footer. We have a grid system implemented and some filler content too. Here it is as a reminder:

<p class="file-name">index.php:</p>

```html
<?php get_header(); ?>
	<section class="row">
		<div class="twelve columns">
			<p>Body content goes here.</p>
		</div>
	</section>
<?php get_footer(); ?>
```

We also already have the loop from the previous chapter. Here is The Loop as a reminder:

```php
<?php 
if ( have_posts() ) {
    while ( have_posts() ) {
        the_post(); 
    } // end while
} // end if
?>
```
So let's combine this code! By doing this, we will add the PHP functionality found in the Loop into the index.php page. 

<p class="file-name">index.php:</p>
```php
<?php get_header(); ?>
	<section class="row">
		<div class="twelve columns">
<!-- BEGIN LOOP -->
			<?php 
			if ( have_posts() ) {
			    while ( have_posts() ) {
			        the_post(); 
			    } // end while
			} // end if
			?>
<!-- END LOOP -->
		</div>
	</section>
<?php get_footer(); ?>
```

I have left plenty of room for you to see where I took out the filler content and placed the loop in there. If you need to remember what exactly the loop is doing, reference the previous chapter. 

#### Step 3. Save and Upload

After saving and uploading, you should see the 5 posts of content in their entirety on the front page. 

You now have a dynamically working CMS integrated web page. 

## <a name="internal-pages-and-posts">Internal Pages and Posts</a>

Having a front page is really important, but there will be times when you want to only display one post of content or one page of content that isn't the front page. You will notice that the process for creating a page and for creating a post are almost identical!

Before we move on, let's discuss an important concept: Data Context

### Data Context

I am going to completely oversimplify this section because it is somewhat of an advanced concept, but it is an important concept to think about when working with a CMS. 

The **Data Context** is the Data that is being displayed based on a Context. I know, very instructive. Practical application of this concept will help demonstrate what I mean though. 

*Example 1: A Book*

The Data in a book is the words, images, etc.

The Context in a book depends on a lot of factors. But let's say we want to tell someone to read only Chapter 2 of a book. Then the Context iwe are talking is one chapter of a book. 

Therefore the Data Context of this scenario is the words, images, etc. of chapter 2 of this book. 

*Example 2: A File Cabinet*

The Data is the objects inside of file folders inside the file cabinet. 

The Context depends on what part of the file cabinet you want to look in. But let's say we want to point someone to a single drawer with only the folders that start with the letter L. Then the Context we are talking about is one drawer of a whole file cabinet.

Therefore, the Data Context of this scenario is the file folders (and their contents) that begin with L in an entire file cabinet. 

*Example 3: A Blog*

The Data is the words, images, metadata, etc. of a blog

The Context depends on what part of the site you are querying. But let's say we want to point someone to a single post in a blog. Then the Context we are talking about is one post of a whole blog's website.

Therefore, the Data Context of this scenario is the words, images, metadata, etc. of a single blog post of a blog. 

Got it? If so, let's create a template files for these items. 

### Tutorial: Pages Template

Remember, *"a Page is often used to present 'static' information about yourself or your site."* Let's add a template file knowing that anything we make that can be considered a "Page" will be displayed by this page. 

#### Step 1: Create a Page.php file

<p class="message">Create file titled "page.php" in your theme folder</p>

#### Step 2: Add the Grid, Header, and Footer

Let's write some code for the Page.php file that we already understand. 

<p class="file-name">page.php:</p>
```html
<?php get_header(); ?>
	<section class="row">
		<div class="twelve columns">
			<h1>Our Page</h1>
			<p>Filler content for our page.</p>
		</div>
	</section>
<?php get_footer(); ?>
```

#### Step 3: Add the PHP to load the Page

We discussed the "Data Context" above,  but here we are going to apply it to our code. Another thing to note about this code is that it should look almost identical to our loop (and the logic IS identical). We have added two important WordPress functions we will talk about after we add the PHP. 

<p class="file-name">page.php:</p>
```php
<?php get_header(); ?>
	<div class="row">
		<div class="twelve columns">
<!-- BEGIN PAGE PHP -->
			<?php if (have_posts()) : 
				/* OUR DATA CONTEXT IS DEFINED 	*/		
				while (have_posts()) : the_post(); ?> 
					<h2><?php the_title(); ?></h2>
					<?php the_content();
				endwhile;
			endif; ?>
<!-- END PAGE PHP -->
		</div>
	</div>
<?php get_footer(); ?>
```

The way that the PHP we added works looks a lot like the index.php loop. We do a test to see IF we have posts, then we define our data context by saying WHILE we have posts, let's display the post. Though it works identical to the loop logically, the data context is entirely different. 

When you are templating (and just copying my code) it isn't apparent, but there is an assumption occurring here. That assumption deals with routing, which is essentially applying a data context through a URL (please excuse that oversimplified definition). 

To simplify that explanation, the PHP is being written with the assumption that the URL will contain the proper data context to display.

So this URL: 
	http://myblog.com/the-name-of-my-post 

will return only the data found in the post (or page): 
	"The Name of My Post."

WordPress handles all the routing for you because it is built in functionality. So you don't need to worry about any of that, but know WHY the code that is essentially a loop functions differently on the front page than it does on the internal pages and posts. 

The second part to notice is the specifics of the content we are adding. This is a good opportunity to notice how easily PHP integrates with HTML. The part I am taking about is this:

``` php
…
<h2><?php the_title(); ?></h2>
<?php the_content(); ?>
…
```

'the_title' and 'the_content' are both custom WordPress functions. 

*What do you think these functions do? (hint, it's quite obvious)*

You will notice that the_title is wrapped in 'h2' tags. This is easy to do because the PHP tags are closed and opened around them. This is how the PHP parser on the server know what is PHP and what isn't. When the PHP parser sends the page to the client (person accessing the web page), it only parses the parts of the site wrapped in '<?php ?>' tags as PHP and the rest is sent as HTML and parsed PHP. 

Wrapping PHP tags in HTML tags is such a common practice in WordPress templating that you should make sure you fully grasp this concept right now.

#### Step 4. Save and Upload

If you have a page to view, you should be able to see it in this template after you save and upload this file to your server. If you do not, make a page in the Dashboard (Pages -> Add New) and then click the "View Page" button in the Dashboard or in the Page itself. 

### Tutorial: Posts Template

Remember, *"posts are articles that you write to populate your blog."* Let's add a template file knowing that anything we make that can be considered a "Post" will be displayed by this page. 

* Posts are not templated as a post.php file, but rather by a single.php file. 

#### Step 1: Create a Single.php file

<p class="message">Create file titled "single.php" in your theme folder</p>

#### Step 2: Add the Grid, Header, and Footer

Let's write some code for the Single.php file that we already understand. 

<p class="file-name">single.php:</p>
```html
<?php get_header(); ?>
	<section class="row">
		<div class="twelve columns">
			<h1>Our Post</h1>
			<p>Filler content for our post.</p>
		</div>
	</section>
<?php get_footer(); ?>
```

#### Step 3: Add the PHP to load the Post

This should look eerily similar to the Page tutorial above. That's because the logic is the exact same and the defining data context concept is also the same. 

<p class="file-name">single.php:</p>
```html
<?php get_header(); ?>
	<div class="row">
		<div class="twelve columns">
<!-- BEGIN SINGLE PHP -->
			<?php if (have_posts()) :
				/* OUR DATA CONTEXT IS DEFINED 	*/				
				while (have_posts()) : the_post(); ?> 
					<h2><?php the_title(); ?></h2>
					<?php the_content();
				endwhile;
			endif; ?>
<!-- END SINGLE PHP -->
		</div>
	</div>
<?php get_footer(); ?>
```

Notice any differences from page.php? You shouldn't see any (except the comments). It is important to make sure you understand that though these template files are currently identical, we have separate files for pages and posts because they serve very different functions in the CMS and will probably want to be treated differently going forward. 

#### Step 4. Save and Upload

If you have a post to view, you should be able to see it in this template after you save and upload this file to your server. In the Dashboard click the "View Post" button in the Dashboard or in the Post itself. 

### Tutorial: Sidebars Includes

When you are doing this tutorial, think about the header and the footer. This is the EXACT same thing and if you understand how to link to a header or footer, you can link to a sidebar.

#### Step 1: Modify the Page.php File to have a Sidebar

The first step will be to modify the LAYOUT of our page.php file. I have taken out the old comments from the previous steps and added in new ones for this tutorial. 

<p class="file-name">page.php:</p>
```html
<?php get_header(); ?>
	<div class="row">

<!-- MAKE THIS COLUMN NINE WIDTH -->
		<div class="nine columns">
			<?php if (have_posts()) :			
				while (have_posts()) : the_post(); ?> 
					<h2><?php the_title(); ?></h2>
					<?php the_content();
				endwhile;
			endif; ?>
		</div>
<!-- ADD IN A THREE WIDTH COLUMN - COMPLETE THE TWELVE REQUIREMENT WIDTH -->
<!-- BEGIN SIDEBAR -->
		<div class="three columns">
			<h3>Sidebar Text</h3>
			<p>This is the sidebar content to put in here.</p>
		</div>
<!-- END SIDEBAR -->
	</div>
<?php get_footer(); ?>
```

First we broke up the row into two columns instead of one. We made one column a nine width and the other a three width. This satisfies the requirement that the columns equal twelve. We then add filler content into the three width column so that there is something there. Feel free to upload the page.php file and check it out. 

#### Step 2: Create a Sidebar.php File

<p class="message">Create a file called "sidebar.php" in your themes root folder.</p> 

#### Step 3: Separate the Sidebar from the Page

Now we are going to place the content that is between the Begin and End Sidebar comments into the Sidebar.php file. We will then modify the Page.php file to link to the sidebar.php file. 

<p class="file-name">sidebar.php:</p>
```html
<h3>Sidebar Text</h3>
<p>This is the sidebar content to put in here.</p>
```

<p class="file-name">page.php:</p>
```html
<?php get_header(); ?>
	<div class="row">
		<div class="nine columns">
			<?php if (have_posts()) :			
while (have_posts()) : the_post(); ?> 
					<h2><?php the_title(); ?></h2>
					<?php the_content();
				endwhile;
			endif; ?>
		</div>
<!-- BEGIN SIDEBAR -->
		<div class="three columns">
			<?php get_sidebar(); ?>
		</div>
<!-- END SIDEBAR -->
	</div>
<?php get_footer(); ?>
```

#### Step 4: Save and Upload 

Notice how simple this is? It is the exact same idea as the header.php and footer.php. 

*Why did we separate the sidebar.php file?*

## <a name="introduction-to-styling-wordpress">Introduction to Styling WordPress</a>

You will not want to do much styling for a blank template. Additionally, we already have a framework loading in and it will handle a significant amount of the basic styling we would otherwise use. This section is useful more as a way for you to see how CSS works with WordPress and to learn how to make basic changes in future lessons. 

Our style.css file currently looks like this:

<p class="file-name">style.css</p>
```css
/*
Theme Name: FirstName Blank Theme
Theme URI: URL for FirstName Blank
Author: FirstName LastName
Description: Blank theme for WIE course
Version: 0.1
License: Open
Text Domain: firstname_lastname_blank_template
*/

*{
	color: #000000;
	font-size: 14px;
	line-height: 16px;
}
```

Which is totally fine! That's actually probably more than we need. For the purpose of this lesson, I am going to modify the headers (H1, H2, etc.) to look different. Feel free to make other changes to see how CSS and WordPress works, but make sure to delete them after you are done (so that you truly do have a blank template). 

<p class="file-name">style.css</p>
```css
/*
Theme Name: FirstName Blank Theme
Theme URI: URL for FirstName Blank
Author: FirstName LastName
Description: Blank theme for WIE course
Version: 0.1
License: Open
Text Domain: firstname_lastname_blank_template
*/

h1, h2, h3, h4, h5, h6 {
	color: blue;
}

h2, h4, h6 {
	font-weight: 100;
}

h1 {
	font-size: 2.4rem;
}
h2 {
	font-size: 2.0rem;
}
h3 {
	font-size: 1.8rem;
}
h4 {
	font-size: 1.5rem;
}
h5 {
	font-size: 1.2rem;
}
h6 {
	font-size: 1.0rem;
}
```

When you upload the CSS file, it should be apparent that there are immediate changes after you reload a page. We will definitely go into more advanced CSS with WordPress in the future - but I wanted to quickly touch on one of the biggest parts of template design. 
