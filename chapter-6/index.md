---
layout: page
title: Chapter 6&#58; Storing and Using Content
---

## Table of Contents

* [Data and Managing Data](#data-and-managing-data)
	* Managing Data
* [Databases and CMSs](#databases-and-cmss)
	* Databases Generally
	* Database Operations
	* Security and Separating Systems
* [WordPress and MySQL](#wordpress-and-mysql)
	* MySQL
* [Introduction to Metadata](#introduction-to-metadata)
* [Taxonomies](#taxonomies)
	* Tutorial: Custom Taxonomies in WordPress

## <a name="data-and-managing-data">Data and Managing Data</a>

	Data as a general concept refers to the fact that some existing information or knowledge is represented or coded in some form suitable for better usage or processing.

[Wikipedia - Data](http://en.wikipedia.org/wiki/Data)

I don't expect you to know the very specifics of the definition of "data," but having an understanding of the term and how it should be used is important. Information can be transformed into data. Data is the actual information in a usable form. Usability in this case, of course, depends on the way you want to use it.

*Isn't 'content' data? Can you think of when content is not data?*

### Managing Data

A lot of time and effort goes into managing data. However, WordPress and MySQL handle a lot of that work for us. In fact, most good CMSs and Database software solutions solve these problems for us. 

The topic of data management could be a course on its own, but for our purposes I just want you to appreciate the fact that WordPress handles a lot of our data management without having any real work on our part. 

Okay, so we know roughly what data is and we know that it is important that we manage it effectively. We know that data management is complicated from a structural and philosophical level. And we know that WordPress handles a lot of our data management for us. However, let's learn a bit about databases so that if you have to use a system that is not as simple you will be able to speak knowledgeably about it. 


## <a name="databases-and-cmss">Databases and CMSs</a>

### Databases Generally:

The term **"database"** is used in all sorts of other industries to describe **any collection of things or information**. 

In computer science, a database is often used to refer to a software solution that sorts information to be sorted and queried. We use MySQL for WordPress, but there are plenty of database solutions. Since discussing databases in extreme detail is well outside of the scope of this class, we are going to focus our discussion to CMS based databases. 

With "relational databases," information is stored in a database in tables. There are other types of non-relational database storage systems (e.g., MongoDB), but most CMSs use a relational database system (e.g., MySQL). 

As a side note, I love MongoDB and use it for a lot of my projects. This guy explains the different between relational and non-relational databases a lot better than I could - [Explaining Non-Relational Databases to My Mom](http://www.ignoredbydinosaurs.com/2013/05/explaining-non-relational-databases-my-mom)

In these relational databases, the information is stored in rows and columns. A row will contain a number of columns that are labeled and then store the particular information as it is sorted. 

The table knows how to group information based on the "Primary Key." The primary key is a column in the table that indexes the table. This method of database production is referred to as a "Relational Database" because all of the items in the database relate to one another. 

Let's use WordPress as an example. WordPress will default to a numeric Primary Key. So the first post you make is given the index 0 (index keys generally start with 0 not 1) and the 100th post is given the number 99. 

Each column in the top organizational row is given its own unique name (i.e., Post Title) and all of the other items in that column (i.e., "This is my first post") will be the data for that primary key and parameter. 

<!--

Note from @chrisallenlane:

It's been a while since I've used either Wordpress or MySQL, but I have a
question about the following assertion:

> If a column is empty it will be given a null value and be considered empty.

Is that correct? IIRC, Wordpress would leave most empty fields as an empty
string in the database (`""`), rather than `null`. And MySQL (again, if I
recall correctly) does make a distinction between `null` and `''`.

I haven't used Wordpress for perhaps 3 years though, so I may be mistaken
and/or out-of-date.

-->

Each column next to the primary key will relate directly to the data for that primary key. If a column is empty it will be given a null value and be considered empty. 

The easiest way to think about it is to draw out a table with rows and columns. The top row is organizational and the first column is the primary key to help sort data. 

	I know this is complicated, but stick with me...

### Database Operations

Now that we know about how a database stores information and how it sorts that information, let's talk briefly about what a database management system is able to do with this information. 

The obvious things that it can do include writing, editing, deleting, and reorganizing the information. But the power comes with interacting with other systems in delivering the information. The efficient sorting of information allows a CMS to query information sorted in a database.

#### An Example

As an example, let's say we want to view a post in WordPress called "Fun with Web Design." In WordPress, the database queries for specific posts are controlled by the internal routing function (a.k.a. the URL). So if we were going to find this post, we could use the URL "http://mywpsite.com/fun-with-web-design."

The extremely oversimplified version of what happens behind-the-scenes is this:

1. The server will tell WordPress what has been asked of it
2. WordPress will take the URL as it has been presented to it
3. WordPress will know that it should look for the URL string as it appears after the domain ("fun-with-web-design")
4. WordPress queries the database for the "Post Title" of "Fun with Web Design." 
5. The Database will find that post title and return 1) the primary key of the post and 2) any other information that WordPress asked for (post content, image URLs, etc.)
6. WordPress will run that data through the theme and display the web page

### Security and Separating Systems

The obvious advantage of a database is having an organization structure for your data. Keeping the data separate from the application allows you to make the data more mobile/usable and also sort it from a separate server. 

Another advantage to a database is security. By having a secure system that stores all of the information for a site, it allows you to limit queries at the point of contact while maintaining the functionality of the site. As an example, this can be seen in Facebook, which allows you to view only your data from a database but not other people's data. 

## <a name="wordpress-and-mysql">WordPress and MySQL</a>

	WordPress requires a MySQL database to store all blog information, including posts, comments, metadata, and other information.

[WordPress Codex - MySQL](http://codex.wordpress.org/Glossary#MySQL)

The concept of an application interacting with a database is mostly universal. WordPress' integration with MySQL is no different. Using an index key, WordPress will query information from the database depending on the user's query (often through the URL - or route). 

In fact, we directly discussed how WordPress works with MySQL in the examples above.

For a complete understanding of how WordPress integrates with MySQL go to the [WordPress Codex - Database Description](http://codex.wordpress.org/Database_Description)

### MySQL
	
	MySQL is a popular choice of database for use in web applications, and is a central component of the widely used LAMP open source web application software stack… MySQL is a relational database management system (RDBMS), and ships with no GUI tools to administer MySQL databases or manage data contained within the databases. 

[Wikipedia - MySQL](http://en.wikipedia.org/wiki/MySQL)

<!--

Note from @chrisallenlane:

This is as much a question as it is a suggestion:

Again, I haven't used Wordpress for a while, but last I heard, the open-source
community was slowing migrating away from MySQL and into MariaDB, which is
(allegedly) a drop-in replacement:

https://mariadb.org/

My understanding is that the motivation for making that change is mostly
related to licensing - Oracle purchased MySQL some time ago, and there are
fears that MySQL will become increasingly closed-source.

In your experience, are a meaningful number of Wordpress sites powered by
MariaDB yet? Is the latter worth mentioning?

-->

I have pulled a lot from this article here - in quotes below: [What is MySQL? What is a Database? What is SQL?](http://www.thesitewizard.com/faqs/what-is-mysql-database.shtml) because it's really good and you should read it fully if you want a better understanding of the topic. 

As we have established, web sites and other software need to receive data. Most of these systems that need data use a database to store, hold, and alter the data.

	"To make it easy for other programs to access data through them, many database software support **a computer language called "SQL"** (often pronounced as "sequel"). SQL was specially designed for such a purpose. Programs that want the database software to handle the low-level work of managing data simply use that language to send it instructions."

	"There are many databases that support the use of SQL to access their data, among them is MySQL. In other words, MySQL is just the brand of one database software, one of many. These databases are very popular among programs that run on websites which is why you often see one or both of them being advertised in the feature lists of web hosts, as well as being listed as one of the "system requirements" for certain web software (like blogs and content management systems)."

You won't need to learn the programming language SQL or really learn how to use MySQL if you are a front end developer (or even a backend developer in some cases). WordPress handles a lot of the work for MySQL handling internally and it is done without your worrying about it. 

You may work with MySQL through a GUI interface (such as Workbench) or through a command line interface. Depending on the server type you are using, the command line interface will differ slightly, though the functionality is much the same.

Luckily for us we will have limited interaction with the MySQL databases for this course and there will be very little that you will ever have to do with it. 

Hopefully you understand how databases work and if you are ever tasked with a problem with them you will at least have a starting point. Additionally, understanding how the database sends information will help you understand how WordPress pulls it.

## <a name="introduction-to-metadata">Introduction to Metadata</a>

Metadata is any data about data. For our purposes, we will primarily be using metadata for WordPress in the context of taxonomies.

	The main purpose of metadata is to facilitate in the discovery of relevant information, more often classified as resource discovery. Metadata also helps organize electronic resources, provide digital identification, and helps support archiving and preservation of the resource. Metadata assists in resource discovery by "allowing resources to be found by relevant criteria, identifying resources, bringing similar resources together, distinguishing dissimilar resources, and giving location information."
[Wikipedia - Metadata](http://en.wikipedia.org/wiki/Metadata)

There are two types of metadata (for our purposes): 

1. Descriptive metadata, 
2. Structural metadata

<br />
**Descriptive metadata** is any data that describes or identifies information sources. Describing an item is useful for archiving or for sorting. Taxonomies would fall under the descriptive metadata context.

**Structural metadata** facilitates navigation and presentation of electronic resources. Some structural metadata helps provide structure to the data. For example, if we were looking at an image tag, the width and height would be the structural metadata. Additionally, structural metadata could also include the primary key in a mysql database. 

*How else could you use "data about data" in a web site?*

## <a name="taxonomies">Taxonomies</a>

A taxonomy is not when you make a dead animal into a sculpture, it is a fancy term for grouping things together. 

Taxonomy is the practice and science of classification. In a wider, more general sense, it may refer to a classification of things or concepts, as well as to the principles underlying such a classification. 

Our experience with WordPress already has led us to two different types of taxonomies: Tags and Categories. A post or a page can be tagged with either a tag or a category. Either a tag or category object can be added or deleted whenever you'd like. You can also use multiple categories and tags for each post and page if you'd like or none at all.

These two ways of grouping content work differently in one way, hierarchy. A category allows for a hierarchical sorting while a tag is merely a short phrase to describe the post/page.

The WordPress Codex has a great and more in-depth explanation of taxonomies: [WordPress Codex - Taxonomies](http://codex.wordpress.org/Taxonomies)

### Tags

Often, a tag is used for sorting and for identifying data. They can be used in a tag cloud or in other tag based sorting mechanisms. Tags were initially very popular for SEO reasons and because tag clouds were a thing for a period of time (though now they look dumb). 

From the WordPress Codex: 

	Tags can be made up on the fly, by simply typing them in. They can be seen on the site in the '/tag/name' types of URLs. Posts tend to have numerous tags, and they are generally displayed near posts or in the form of tag clouds.

### Categories

Often, a category is used to to sort information into an appropriate area. This can be used for site navigation or just general sorting. In WordPress categories also can be used to modify your URL structure if you set it up that way in the settings. These categories can then be seen on the site by using '/category/name' types of URLs. Categories tend to be pre-defined and broad ranging.

Things get slightly more complicated and a lot more powerful with the addition of custom taxonomies…

### Tutorial: Custom Taxonomies

We are going to use the example as outlined in the [WordPress Codex - Custom Taxonomies](https://codex.wordpress.org/Taxonomies#Custom_Taxonomies).

For a second opinion, feel free to use this tutorial: [Tuts+ - Custom Taxonomies](http://code.tutsplus.com/tutorials/introducing-wordpress-3-custom-taxonomies--net-11658)

For a third opinion, feel free to use this tutorial: [Smashing Magazine - Create Custom Tutorials](http://wp.smashingmagazine.com/2012/01/04/create-custom-taxonomies-wordpress/)

Our project goal will be to create a taxonomy of different web development techniques that can be used alongside our existing categories.

#### Step 1: Add a Function to your Functions.php File

The first step in adding a new taxonomy is register the taxonomy with WordPress through your Functions file - which we know modifies the way WordPress works from a theme level. Feel free to add this code to the bottom or top, but not between any other open functions.

<p class="file-name">functions.php</p>
```php
function custom_taxonomy_wie_init() {
}
add_action( 'init', 'custom_taxonomy_wie_init' );
```

This should look a LOT like the Widget registration process, and that's a good thing. 

#### Step 2: Add Information About the Taxonomy

<p class="file-name">functions.php</p>
```php
function custom_taxonomy_wie_init() {
	// create a new taxonomy
	register_taxonomy(
		'webdevelopment',
		'post',
		array(
			'hierarchical' => true,
    			'label' => 'Web Development Types',
'query_var' => true
		)
	);
}
add_action( 'init', 'custom_taxonomy_wie_init' );
```

The array of options has three different parameters:

hierarchical (which asks whether the custom taxonomy will have the characteristics of embedded levels like a category)
label (which is simple the label of the taxonomy that will be displayed)
query_var (allows us to search and sort based on this custom taxonomy)

#### Step 3: Add Some Values to Your Taxonomy

From WordPress Codex: 
	
	Once you've added a taxonomy, you'll find that WordPress creates a new meta box on posts for you. This new meta box looks almost exactly like the Tags box and will let you add tags to those posts.

To fully appreciate the custom taxonomy you should go into your Dashboard and add some values. If you are feeling uncreative, add "JavaScript," "CSS," and "HTML."

#### Step 4: Implementing Some Use of the Custom Taxonomy

I must admit the Codex suggests some rather complicated methods for using the custom taxonomy (many of which are inane). We are going to use it to implement a list of our new custom taxonomy in our Sidebar.php file - so that if we include the sidebar file, we will know it will display the list of our custom taxonomy. 

We are going to use the WordPress function get_terms. More information can be found here: [WordPress Codex - get_terms](https://codex.wordpress.org/Function_Reference/get_terms)

Here is what our sidebar currently looks like:

<p class="file-name">sidebar.php</p>
```php
<?php dynamic_sidebar('first-widget'); ?>
```

Let's keep the widget, but add some functionality to display our custom taxonomy.

<p class="file-name">sidebar.php</p>
```php
<?php dynamic_sidebar('first-widget'); ?>

<ul>
<?php 

$args = array(
    'orderby'           => 'name', 
    'hierarchical'      => true, 
  ); 

$terms = get_terms('webdevelopment', $args);

if ( ! empty( $terms ) && ! is_wp_error( $terms ) ) {
    $count = count( $terms );
    $i = 0;
    $term_list = '<li>';
 	foreach ( $terms as $term ) {
        $i++;
    	$term_list .= '<a href="' . get_term_link( $term ) . '" title="' . sprintf( __( 'View all post filed under %s', 'my_localization_domain' ), $term->name ) . '">' . $term->name . '</a>';
    	if ( $count != $i ) {
            $term_list .= ' &middot; ';
        }
        else {
            $term_list .= '</li>';
        }
    }
    echo $term_list;
}
?>
</ul>
```

Wow! That sure is a lot to take in. However, I urge you to go through the code and consider what each step does. It could be interesting. Just copying and pasting the code will not really make you a stronger programmer, but understanding what is happening will. 

#### Step 5: Save and Upload

If you added some values to your posts regarding your custom taxonomy, it should show up anywhere your sidebar is loaded in. 

Knowing how to do this is useful, but it also can allow you to solve a large number of problems that may not seem apparent right now. Data management is a problem you will only appreciate when it actually is a problem in front of you. 

*Can you think of a way to make use of custom taxonomies outside of sorting?*
