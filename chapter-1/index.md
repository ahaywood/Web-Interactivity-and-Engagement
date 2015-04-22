---
layout: page
title: Chapter 1&#58; Introduction to WordPress and CMSs
---

## Table of Contents
* [Content Management Systems (CMSs)](#cmss)
* [Installing WordPress](#installing-wordpress)
	* Advice about installing WordPress
	* Two Methods of Installing WordPress
		* Using your Host
		* Manual Installation 
* [Walkthrough of WordPress](#walkthrough-wordpress)
	* File Structure
		* Primary Folders
			* wp-admin
			* wp-content
				* Themes
				* Plugins
				* Uploads
			* wp-includes
	* WordPress Administration
		* Posts
		* Pages
		* Media
		* Comments
		* Appearance
		* Plugins
		* Users
		* Tools
		* Settings
		* Toolbar
* [WordPress Lessons Applied to Other CMSs](#lessons-applied)
	* Separation of Theme and Functionality
	* Plugins
	* Widgets and Custom Menus
	* Pages and Posts
	* Taxonomies
	* Dashboard Administration
	* User Management
	* Media Library Handling
	* Content Management Generally
* [How do the languages work together?](#languages-together)
	* Client Side Languages
		* HTML
		* CSS
		* JavaScript
	* Server Side Languages
		* PHP
		* Other Server Side Languages
	* Servers Generally
	* Databases Generally

## <a name="cmss">Content Management Systems (CMSs)</a>

The name “Content Management Systems” is already pretty instructive about what the scope and purpose of such a system is - managing content. So, good, it looks like you’ve learned everything you need to know in this class...

CMSs come in all shapes and sizes. There are innumerable choices to make when selecting one, and due to their variety selecting one is never an easy choice. We will cover the criteria for selecting a CMS in greater detail later, but lets get to the definition and characteristics of a CMS before we move on to the practical application of a CMS through WordPress. 

From Wikipedia:
<div class="message">The function and use of content management systems is to store and organize files, and provide version-controlled access to their data. CMS features vary widely. Simple systems showcase a handful of features, while other releases, notably enterprise systems, offer more complex and powerful functions. Most CMS include Web-based publishing, format management, revision control (version control), indexing, search, and retrieval.

A CMS may serve as a central repository containing documents, movies, pictures, phone numbers, scientific data. 

Distinguishing between the basic concepts of user and content. The content management system (CMS) has two elements:

1. Content management application (CMA) is the front-end user interface that allows a user, even with limited expertise, to add, modify and remove content from a Web site without the intervention of a Webmaster.

2. Content display application (CDA) compiles that information and updates the Web site.

Web content management systems

A content management system (Web CMS) is a bundled or stand-alone application to create, deploy, manage and store content on Web pages. Web content includes text and embedded graphics, photos, video, audio, and code (e.g., for applications) that displays content or interacts with the user. Content Management has many roles in today's market place and is an important base for any website blogging, articles, news, description of products etc. A Web CMS may catalog and index content, select or assemble content at runtime, or deliver content to specific visitors in a requested way, such as other languages. Web CMSs usually allow client control over HTML-based content, files, documents, and Web hosting plans based on the system depth and the niche it serves.

</div>

Wow. Couldn’t have said it better myself. The only thing I would add, which almost every modern CMS has, is user management.

Here is the refined list of features of a CMS:

1. Manage and store content (text, images, etc.)
2. Provide version control
3. Allow for organization and access of the content
4. Separates the display and management of content
5. Allows for user administration
6. Allows a person with non-technical skills to manage and create content

Many CMSs have additional features, but these are those that are most common. 

Keep track of these 6 features of a CMS as we go through the WordPress walkthrough in this chapter. 

## <a name="installing-wordpress">Installing WordPress</a>

WordPress is the primary tool we will use in this course to demonstrate the principles of Content Management Systems (CMS). Luckily for us, getting an instance of WordPress up and running is a relatively easy process.

Because it is assumed that you have 1) a host, 2) an understanding of how to use FTP or an FTP client and 3) a text editor, I will skip any information about those topics. See the resources for suggestions on which FTP and/or text editors to use. 

The instructions for installing WordPress can be found on the WordPress Codex here: [https://codex.wordpress.org/Installing_WordPress](https://codex.wordpress.org/Installing_WordPress).

<div class="message">The WordPress Codex will the primary source of information for WordPress as we go forward. It is the primary documentation for WordPress. </div>

### Advice about installing WordPress

For organizational purposes I highly suggest you install WordPress into a subdirectory of your host. That means you will install WordPress in a folder inside of your file server. This is a rule I follow for all of my WordPress installations. 

For purposes of this course, you will need to do this so that you are able to complete the multiple projects on multiple installations of WordPress. For purposes of being a future forward web developer, having subdirectories hold applications allows you to organize your file structure more logically and that will improve your efficiency in the long term. 

### You have two choices for installing WordPress: 

#### a. Using Your Host to Help you Install WordPress

The easiest way to get started with WordPress is to use a feature on your host for installing WordPress. Most hosts feature a “One Click Install” feature for WordPress. 

I highly suggest you go this route with installing WordPress since it allows you to focus more on the template design and the conceptual level of this course and not get down in the weeds of system administration. 

Consult your host’s documentation for any help you may need for installing WordPress with this process.  

#### b. Installing WordPress on your own

If you are an ambitious person and want to know WordPress from the bottom up, maybe installing WordPress manually is the way to go. The process is by no means difficult, but for purposes of this course this task is irrelevant. 

Details for how to install WordPress manually are clearly outline on the “Installing WordPress” in the Codex here: [https://codex.wordpress.org/Installing_WordPress](https://codex.wordpress.org/Installing_WordPress)

## <a name="walkthrough-wordpress">Walkthrough of WordPress</a>

Understanding the file structure and classification of data in WordPress is useful to bringing context to both this course and becoming a competent WordPress admin. To best understand this lesson, make sure you have WordPress installed so that you can observe and follow along.

### File Structure

The installation of WordPress is split up into several subdirectories which I will outline below. 

#### Primary Folders:

When you first access the folder where you have WordPress installed (the root), you will see three folders and various other files:

* wp-admin
* wp-content
* wp-includes

As a note, there are a few files you may need to edit that exist in the root of the WordPress installation (specifically the wp-config.php file). These files exist mostly as either a settings file or are there to allow servers to process the WordPress framework correctly. For this class, you will most likely not need to modify these files. 

##### WP-ADMIN

<div class="message">You will never want to edit the wp-admin folder. If WordPress is updated it will overwrite any changes made here.</div>

The wp-admin folder contains the files that tell WordPress how to function. The files here are not meant to be modified since they are the files that do all of the work that you don’t have to. The files here are changed whenever you update WordPress. WordPress defaults to updating automatically too, so any changes here would be overwritten if you have this setting enabled. But don’t worry about that - you are using this dynamic CMS exactly for the reason that you wouldn’t have to modify its core functionality. 

##### WP-CONTENT

This is where the magic happens. Inside this folder are all of the template, plugin, and media (images, etc.) files. 

The wp-content folder contains all of the files you will need to modify or use. There will be an assumption that anything we do in this course occurs in this folder (because everything we will do in this course with WordPress will occur here). 

###### THEMES

The Themes folder holds the template files for your themes. When you want to add a new theme, you will put it inside of this folder. The theme editing is where the vast majority of the tutorials in this class will take place. 

When you first install WordPress the Themes folder contains several default WordPress themes (e.g., TwentyFifteen) so that any content will be able to be displayed as soon as WordPress is installed. 

###### PLUGINS

This folder holds all of the plugins and their dependent files. Plugins are an easy way to add functionality to WordPress. We will learn more about plugins as we go forward. 

###### UPLOADS

The Uploads folder stores all of the files you upload through the WordPress Dashboard. These files include images and other media. 

The Uploads folder is sorted by date (year first, then month, then date). Additionally, WordPress resizes images you upload for optimized file serving. If you upload an image in the dashboard, it will store several versions of that image in different sizes in the uploads file. 

<div class="message">With regard to the Plugins and Uploads folder, note that when you have a local version of your WordPress site (on your own computer), the server version of your WordPress site will store the files and plugins you add through the WordPress Dashboard.</div>


##### WP-INCLUDES

<div class="message">You will never want to edit the wp-admin folder. If WordPress is updated it will overwrite any changes made here.</div>

The wp-includes folder contains the files that WordPress uses to support its primary functions. The files in here are referenced by WordPress during its operation. An advanced WordPress developer may need to modify this area at points.

### WordPress Administration

After you install WordPress and have logged into the WordPress Dashboard, you will come across a bunch of stuff you may not have seen before. Let’s walk through the different items in the Dashboard. The best way to follow this portion of the lesson is to be logged into the WordPress Dashboard and to see mess around to see how everything works.

Many of the definitions of the terms below are taken directly from the WordPress Codex.

The left-hand sidebar contains the primary navigation items for WordPress.

#### i. Posts Tab

> Also known as “articles” and sometimes incorrectly referred to as “blogs”. In WordPress, “posts” are articles that you write to populate your blog. 

[https://codex.wordpress.org/Glossary#Post](https://codex.wordpress.org/Glossary#Post)

#### ii. Pages Tab: 

> A Page is often used to present "static" information about yourself or your site. A good example of a Page is information you would place on an About Page. A Page should not be confused with the time-oriented objects called posts. Pages are typically "timeless" in nature and live "outside" your blog.

[https://codex.wordpress.org/Glossary#Page ](https://codex.wordpress.org/Glossary#Page )

Under both the Pages and the Posts tab are many sub-tabs which we will cover in more detail later. 

#### iii. Media Tab

The Media tab is where you will may perform administration on your uploaded images and other files. 

#### iv. Comments Tab

> Comments are a feature of blogs which allow readers to respond to posts. Typically readers simply provide their own thoughts regarding the content of the post, but users may also provide links to other resources, generate discussion, or simply compliment the author for a well-written post. 

[https://codex.wordpress.org/Glossary#Comments] (https://codex.wordpress.org/Glossary#Comments) 

This course highly suggests you disable comments in the Settings Tab. They are useful for many sites, but may end up being a security liability if not handled correctly.

#### v. Appearance Tab

The Appearance Tab contains quite a bit of important administrative functionality. These include:

a. Menus: Allows you to make custom menus that can be placed in your template

b. Widgets: Allows you to edit the information inside of Widgets. Widgets are “regions” you can put in your template that can carry a wide variety of functionality. Widgets are a great way to allow your content manager a way to make changes to theme’s regions without having to edit code. 

c. Themes: The “skin” of the WordPress site. This tab is where you will enable or change the themes you have in the themes directory in wp-content.

For now, let’s move past these three very important elements. We will cover all three in much greater detail going forward. 

#### vi. Plugins Tab

> A Plugin is a group of PHP functions that can extend the functionality present in a standard WordPress weblog. These functions may all be defined in one php file, or may be spread among more than one file. Usually, a plugin is a PHP file that can be uploaded to the "wp-content/plugins" directory on your webserver, where you have installed WordPress. Once you have uploaded the plugin file, you should be able to "turn it on" or Enable it from the "Plugins" page in the administration interface of your weblog. The WordPress source code contains hooks that can be used by plugins. 

[https://codex.wordpress.org/Glossary#Plugin](https://codex.wordpress.org/Glossary#Plugin) 

The Plugins tab is where you will manage, add, and remove Plugins for your WordPress site. This topic will be discussed in much greater detail later on. 

#### vii. Users Tab

The Users tab contains information and administration for users of your WordPress site. This is where you will add additional users, modify the rights/information of the current users, or delete old users. 

#### viii. Tools Tab

The Tools tab is strange and might end up being more confusing than anything else if you don’t fully understand how limited it is in its usage. The Tools tab contains only a few items - none of which you will use for the direct purpose of this course. 

#### ix. Settings Tab

The Settings tab contains all of the settings for the operation of your WordPress site. 

a. General: Contains general settings of the WordPress site. Most importantly, the Title of your site, the tagline of your site, and how you want to display date/time information.

b. Writing: Contains the settings for the users who write content in WordPress. 

c. Reading: Contains a few important settings, such as how many posts to display by default and whether to use a blog roll or a static page as your main page. We will cover these aspects of WordPress from a much more in depth manner. 

d. Discussion: Contains the settings for comments.

<div class="message">You will want to disable comments ASAP from this section. Uncheck all three of the Default Comment Settings.</div>

e. Media: Contains settings for images. This is a place you can set your default Thumbnail size and the default resize settings for uploaded images. 

f. Permalinks: Settings for how your site URLs work. 
<div class="message">You will want to set the Permalink to be “Posts” as soon as you can. This is both SEO friendly and logical from a UI standpoint.</div>

#### x. Toolbar:

> The Toolbar is an area of the screen just above that site that lists useful administration screen links such as add a new post or edit your profile. 

[https://codex.wordpress.org/Glossary#Toolbar](https://codex.wordpress.org/Glossary#Toolbar)

[https://codex.wordpress.org/Toolbar](https://codex.wordpress.org/Toolbar)

The Toolbar can also be accessed from any page if you are logged in to WordPress. Also called the “dockbar,” it is a very useful tool for providing quick administration of your WordPress site from anywhere on your site. 

## <a name="lessons-applied">WordPress Lessons Applied to Other CMSs</a>

WordPress is just one of MANY Content Management Systems that are available. We will talk about those other CMSs in future chapters, but let’s tie together the things we learned in this chapter thus far.  

Some of the basic concepts of WordPress are universal to all (or most) CMSs.

### a. Separation of Theme and Functionality

Knowing that different levels of technical understanding exist in your organization and being able to separate tasks based upon this technical understanding is an important function of an organization. This concept is primarily why a CMS works so well as a tool for web publishing. 

It is easy to envision a content manager who is a talented writer but has no technical skills. You would not want to give that person access or responsibility over delicate design or programming files for obvious reasons. 

However, the same issue exists between the designer and the back end programmers and the server administrators. You probably wouldn’t want someone who is an expert in front end languages (HTML, CSS) making edits to a large application written in a back end language (PHP, Ruby) - and vice versa. 

Additionally, what if you want to make changes to the application itself but not to the visual look of the application (or vice versa)?

This is where theming comes in. The separation of the application/functionality and the visual aspects of the CMS allows the CMS to work best with people who are best at what they do. It also allows updates to occur separately from one another for a more efficient workflow. 

For this reason, many CMSs have themeing and back end application separated. 

### b. Plugins

A plugin is essentially a lazy way to add functionality. 

*Is that a bad thing? Not always.* 

Nearly every open source or commercial CMS allows you to add packaged functionality to the CMS without forcing the designer to dig too deep into the core files. 

WordPress does this just as well as anyone, but keep in mind that this behavior is very common across most CMSs. 

*What could you think of to add to your CMS in this lazy way?*

### c. Widgets and Custom Menus

Widgets and Custom menus are theme modifications that make the content manager’s life easier. These things allow you to integrate modifiable regions throughout the theme without forcing the content manager to have any extra technical training. 

This concept of modifiable theme regions are fairly common and are useful for the designer to know how to effectively implement and useful for the content manager to know how to edit in the dashboard. 

### d. Pages and Posts

The concept of static, permanent content (pages) is important to both blogging and non-blogging CMSs. On the opposite end of the spectrum are posts which are generally temporary, time sensitive, or only relevant for a limited time. These two concepts work together and separate. Distributing your content into pages and posts is a conceptual step that WordPress asks you to do. 

Many other CMSs will ask you to distribute your content into permanent (pages) and temporary/time sensitive (posts) categories similar to how WordPress handles these concepts. However, I have never seen two CMSs handle the differentiation between pages and posts exactly the same way. 

*Why do CMSs split content up in this way? Should it really matter?*

### e. Taxonomies

We haven’t talked about this concept yet, but taxonomies are universal to CMSs. A taxonomy is basically any grouping of content. In WordPress it is used as tags or categories. Much, much more on this later. 

### f. Dashboard Administration

Being able to have a web interface to efficiently make changes to the site is common to all modern CMSs. Having a Dashboard provides a great benefit for the content managers, the administrative users, and their communication together for having a simple, uniform UI to make changes in. 

*Besides being able to make changes to content and the site easily, what is another use of the Dashboard as a tool of communication?*

### g. User Management

Similar to Dashboard Administration, managing users and the roles of those users is common to all CMSs. Role assignment and the ability to partition responsibilities in CMSs is an important feature for content security and task management. Many of the other CMSs do a vastly better job than WordPress does at role management though WordPress is certainly sufficient for a blog or small site.

*Why is user management so important for a CMS?*

### h. Media Library Handling

Being able to handle images, video, audio, etc. inside of the CMS is a very common feature amongst all CMSs. The definition of a CMS announces this feature as being primary. 

*Why do you think this is? What is the benefit of having an internal media management function?*

### i. Content Management Generally

The whole purpose of the CMS is to manage content. A non-technical user should be able to create, edit, and delete content without having to receive any technical training. WordPress is great for this - and is one reason it has become the most popular blogging platform. 

This philosophy of easy to use content management is (or should be) core to every CMS you encounter. When you are considering a CMS, think about this philosophy and how your non-technical users will use the product. 


## <a name="languages-together">How do the Languages Work Together?</a>

Every part of a web site is important in its overall operation. The interrelationship between the different software solutions and programming languages is often taken for granted when learning how to create web sites. This next lesson may be overly simple or obvious for you, but if you don’t have a solid understanding of how the languages work together, a lot of confusion may arise later on. 

### Client Side (Front End) Languages:

#### HTML: “The Practical One”

**Hypertext Markup Language (HTML)** is the language that browsers read to display web pages. Think of HTML as the language that provides structure and context to the webpage. For instance, if a paragraph is wrapped in a <p> tag, the browser (and you) will know that it is a paragraph. 

HTML is a very simple language that has a lot of power (much of which is taken for granted). The current version of HTML that is supported by most modern browsers is HTML5.

The most important thing to remember is that HTML is the language the browser reads and then parses (or translates into what you see on the page). So when you write HTML, you are “speaking” to the browser and then the browser works as the translator (parses) for the person accessing your site.

<div class="message">When I say you speak to the browser, I mean you create a file that the browser will read when it is loaded. Thinking of programming languages as actual languages is a good way to conceptualize how they work.</div>

#### CSS: “The Pretty One”

**Cascading Style Sheets (CSS)** affect the way that items look or how they are displayed. CSS is a language the browser reads (and then parses) to apply styling to the HTML elements. Just like with HTML, CSS is a language you “speak” to the browser and then the browser translates (parses) it for the person accessing your site. 

#### JavaScript: “The Fun One”

I will not try to overly simplify JavaScript like I have done for HTML and CSS. In the last few years JavaScript has been expanded from being “that thing jQuery is based on” to “the most dynamic and powerful language for application development.” 

For purposes of this example though, know that JavaScript tells the browsers what events to perform - thus it is “the fun one.” What JavaScript does is it allows the page in the browser to undergo changes depending on user conditions or events. It does this by integrating with the Document Object Model (DOM) of the browser. We will discuss JavaScript and DOM manipulation more in this course later.

Like HTML and CSS, you “speak” JavaScript to the browser and the browser translates it (parses) to the person accessing your site.

### Server Side (Back End) Languages:

#### PHP (or other back end languages): “The Workhorse”

So HTML gives structure, CSS gives style, and JavaScript gives functionality - what does PHP even need to exist for? 

Let’s look at the Wikipedia entry for PHP for some information - [http://en.wikipedia.org/wiki/PHP](http://en.wikipedia.org/wiki/PHP) :

> PHP is a server-side scripting language designed for web development but also used as a general-purpose programming language… PHP code can be simply mixed with HTML code, or it can be used in combination with various templating engines and web frameworks. PHP code is usually processed by a PHP interpreter... After the PHP code is interpreted and executed, the web server sends resulting output to its client, usually in form of a part of the generated web page; for example, PHP code can generate a web page's HTML code, an image, or some other data.

(Very) simply put, PHP allows a server to dynamically generate web pages. The output of the PHP is almost always HTML. All of PHP work happens on the server, while all of the HTML, CSS, and (almost all of the) JavaScript happens in the browser. This will be made clearer when we begin using PHP alongside HTML, CSS, and JavaScript. 

Unlike HTML and CSS, you “speak” PHP to the server (not the browser) and the server speaks HTML to the browser (and the browser parses the HTML into a web page). 

*We now know that  PHP can generate HTML pages dynamically, but what does that mean and how is it useful?* 

This is sort of the purpose of the whole class - using a tool to dynamically generate a web resource. There are ways to create pages so that it is time consuming, difficult, and requires training from every member of an organization, and there are ways to create pages so that it is simple, seamless, efficient, and requires minimal training from any member of an organization.

Being able to leverage tools and knowing which tools to leverage is the way to make an organization more efficient and productive - this applies to web development and any organization generally. For us, HTML, CSS, JavaScript, and PHP are all tools we are using to make the lives of our content managers (or users) a lot easier and more efficient. 

So when I say PHP dynamically generates HTML web pages (or web resources), I mean that it is a tool that helps eliminate inefficiencies in the process of creating web pages by performing many of the tasks associated with web page creation automatically. 

The good thing about PHP is that it also does a ton of other things really well too!

#### A note about other server side languages

Pretty much any other server side language can do what PHP does. Each language has its advantages and disadvantages. In fact, many content management systems and web applications will leverage multiple and  different languages for different tasks. The good thing about learning PHP is that you learn principles that can be applies to all server side languages. 

### Servers Generally

Servers are where files are stored and processes are run. Servers are really just hardware (computers) that run software (the server system specifically) per the specifications of the user (you or your server admin). The server software will run applications or processes and then serve files to the browser/users. 

For a simple, HTML only website, the server software will receive a request and fill that request by sending an HTML file for the browser to parse. This process is actually quite complicated if described in detail, but server software solutions make it easy for the user and admin to understand.

For this course we will use Apache for our server solutions. There are entire degrees and certifications based on servers, so just having a cursory understanding of how a server works will be sufficient to complete this course. 

### Databases Generally

We will discuss Databases in much greater detail in later lessons, but for the time being just know that Databases are software solutions for storing data that can be accessed via queries from a wide variety of sources.