---
layout: page
title: Chapter 2&#58; The Dynamic Web
---

## Table of Contents

* [PHP and WordPress](#php-wordpress)
* [WordPress Loop](#wordpress-loop)
* [The Component Based Web](#component-web)
	* Upside of Components
	* Downside of Components
	* CMSs and Components
* [Elements of a Web Site](#elements)
	* Environment
	* Story
	* Aesthetics
	* Performance
	* Usability 

## <a name="php-wordpress">PHP and WordPress</a>

In the last chapter we discussed how all of the web languages work together. So where does WordPress fit into this scheme?

WordPress is a PHP based content management system that generates content dynamically from a database. WordPress is (essentially) the name of a series of components and functions that perform tasks. The components that perform these tasks are written in PHP. 

Some of these tasks include:

* Writing content to the MySQL Database (where the information of the posts, pages, user info, etc.) is stored.

* Fetching the content sorted in the MySQL database

* Displaying the content that was fetched

* Performing manipulation to the data that is displayed

* Deleting or rewriting content in the MySQL database

* Managing User roles and responsibilities

PHP is a server side language that provides directions to a PHP parser on the server to perform these tasks. As you work through the PHP lessons, the scope of how this works should become more apparrant. 

PHP is merely the language that WordPress uses to provide directions to the server’s PHP parser to perform the tasks. This is why you will see a lot of custom WordPress syntax for simplifying these tasks from a developer’s standpoint. Not having to think about many of the small details of website programming is key to CMSs and CMS design. 

The goal of WordPress is to make the performance of these tasks simple and seamless for the user and the content manager. As we work through the tutorials and projects, the scope of these functions will become more transparent and seem a bit less like magic.

A good example of a WordPress component is the WordPress Loop. 

## <a name="wordpress-loop">WordPress Loop</a>

The “Loop” is the mechanism that WordPress uses to display content from the MySQL database repeatedly. 

From the [WordPress Codex - The Loop](https://codex.wordpress.org/The_Loop):

	The Loop is PHP code used by WordPress to display posts. Using The Loop, WordPress processes each post to be displayed on the current page, and formats it according to how it matches specified criteria within The Loop tags. Any HTML or PHP code in the Loop will be processed on each post.

 
``` php

<?php 
if ( have_posts() ) {
	while ( have_posts() ) {
		the_post(); 
	} // end while
} // end if
?>
```
Let’s walkthrough the Loop breaking down each step.

WordPress creates a conditional statement to ask if there are any posts to display:

``` php
	if ( have_posts() ) {
```

Next, inside of that conditional statement, WordPress directs that as long as there are posts to display, display the post:

``` php
while ( have_posts() ) {
	the_post(); 
```

<p class="message">Conditional statements are covered in greater detail in the PHP lessons, but if you have not made it that far through those lessons, know that a conditional statement performs a check to see if “something” is true of false and then performs an action depending on the truthiness of that “something.”</p>

Then you end the “while” conditional statement and then end the “if” conditional statement by closing the tags containing the PHP code.

This simple PHP code contains a lot of power. WordPress is using its custom syntax and PHP to generate the content from all posts that are stored in your MySQL database. There is a lot that the WordPress software environment does to make sure this happens, but from a developer standpoint it is not necessary for you to specify all of the little details. 

Making sure that the code is wrapped in “<?php” and “?>” tags lets the server know that it should process this code as PHP and not just to send it as HTML. 

Additionally, there are a lot of parameters you can use (both in your code and in the WordPress admin) to manipulate how the simple Loop works. We will get into those things later.

The concept of a “loop” is common to both CMSs and programming generally. The ability to repeat a task is paramount to a dynamic resource.


## <a name="component-web">The Component Based Web</a>

As we've said above, WordPress is a series of “components” that perform tasks. All of these little components of code make up the whole of the WordPress CMS. As a whole, WordPress is in itself a component of your WordPress website. You may add a jQuery slider, a contact form, or a CSS animation library to your WordPress site to perform other tasks that WordPress does not have built in. All of these individual parts will end up becoming the whole of your web site when it is ready to be published. 

As a philosophy, separating the individual functions of a resource is often referred to a “component based” approach. 

From Wikipedia - [Component-based Software Engineering:](http://en.wikipedia.org/wiki/Component-based_software_engineering):

	Component-based Software Engineering... emphasizes the separation of concerns in respect of the wide-ranging functionality available throughout a given software system. It is a reuse-based approach to defining, implementing and composing loosely coupled independent components into systems. This practice aims to bring about an equally wide-ranging degree of benefits in both the short-term and the long-term for the software itself and for organizations that sponsor such software.

There are many projects that are embracing the Component Based philosophy from the ground up. For example, [Polymer: https://www.polymer-project.org/](https://www.polymer-project.org/)

The Polymer website says:

	“Web Components usher in a new era of web development based on encapsulated and interoperable custom elements that extend HTML itself. Built atop these new standards, Polymer makes it easier and faster to create anything from a button to a complete application across desktop, mobile, and beyond.”

Though this concept is not novel, applying this philosophy from the start of a project can help you manage your project easier.

### Upside of Components

The upside to using components is huge. You can quickly add large amounts of functionality to a resource quickly with little to no programming work by adding a good component. 

We often take for granted the use of components, but imagine programming a DOM manipulating plugin (slider, UI, etc.) to a web site without using the powerful jQuery library. Each step of the creation of that plugin would have to be done manually from scratch. With the use of a component, we can painlessly make a site from being static to dynamic. 

### Downside of Components

Having a lot of different components working together can make for a confusing and complicated web of functionality. Without proper documentation and software management, component based development could create bugs and issues that may be hard to find.

### CMSs and Components

WordPress makes the concept of components transparently obvious. You can quickly add a plugin, activate that plugin, and then use the additional functionality that comes from that plugin. 

Nearly all CMSs have a plugin library or API which allow for the addition of components in a relatively painless manner. 

Outside of plugins though, the addition of components can add extensibility to a CMS even where that CMS did not originally intend.

*How do you think a CMS could adopt functionality through an external component?*

## <a name="elements">Elements of a Website</a>

The design of every web page has many dimensions. We make both conscious and subconscious decisions about sites when designing, coding, and making technical decisions. It’s easy to get caught in the mire of technical details and weighing how important a feature of a site can be. For that reason, I will discuss the details that go into a website in the context of five elements:

* Environment
* Story
* Aesthetics
* Performance
* Usability

We will discuss these 5 elements and how each of them is equally important – especially when we are creating scalable systems that a wide variety of users will rely on.

### 1. Environment

Environment is essentially a grouping of concepts/items/situations related to the user at the time of accessing a resource. 

This may include the user’s location, weather in their area, device they are accessing the site/resources on, noise in the area, connection speed, and loads of other situational considerations.  

It is useful to take into account as many environmental factors as possible when you are creating a resource so that you can control potential negative influences surrounding your user’s experience but also to take advantage of the user’s environment to make functional enhancements.

#### i. Physical factors: 
Serving a resource to a user will inevitably be hindered or enhanced by **physical factors** on the users end. This does not apply to just web resources, but every experience that a user will be a part of (in life and in design). Some factors could include weather, temperature, physical objects, location, time, or other users. 

An example of environmentally influenced situation would be a cell phone user that is trapped at a coffee shop by a rain storm. The physical factors in this example would be 1) a mobile device, 2) inclimate weather, 3) a cafe (location), and 4) possibly the fact that the user is crowded by other users who are experiencing the same thing. 

*How could you use these factors to enhance a user’s experience?*

#### ii. Mental factors: 
**Mental factors** will be anything that the user is experiencing internally, generally controllable as a result to stimulus. This could mean stress, happiness, tiredness, or anger. 

An example would be a frustrated bank customer calling their bank to get an issue resolved. 

*What benefits would you see in acknowledging and adjusting to these factors?*

#### iii. Resource generated factors:

**Resource generated factors** that you intentionally create (and are effective) can be one of the most positive and tangible experience enhancements for the user. A resource factor that you unintentionally create runs the risk of decreasing positive experiences for the user. Some resource generated factors could be connection speed, device speed, and user interface generally. 

An example of resource generated factors being applied could be a user opening a native application on their smart phone. 

*What are some techniques to use these resource generated factors knowing that some of your users won’t be on the newest devices in the best connection areas?*

Read [“Environmental Design with the Device API,”](http://alistapart.com/article/environmental-design-with-the-device-api) an A List Apart article about using factors in the design of your resource. 

<p class="message">API is short for application programming interface (API) and specifies how software components interact with each other. Essentially, it is a phrase that is used to describe anytime two programs interact with one another. For instance, the Twitter API is used for integrating Twitter into other software.</p>

### 2. Story

**Story** encompasses the content and the display of the resource as a method of communicating a message. 

Content includes text, photos, videos, and other informative items - but it also includes the method of delivery and stylistic decisions (note the overlay with other elements). It is easy to see the practical importance of effective storytelling in news, PR releases, and fiction/non-fiction. 

But storytelling is not limited to the sharing of knowledge, it can also be about the guided experience of a user. Having a narrative through design can help enhance the usability and enjoyment of the user and also allows you to communicate effectively. 

<p class="message">Do not think of story as being limited by just the words and pictures on a site. The location of elements and stylistic decisions also weigh heavily on a user. Branding and other warm fuzzy feelings might also play a role in storytelling.</p>

*Can you think of another useful perk of storytelling other than those I’ve listed?*

### 3. Aesthetics

Design is not always about beauty and beauty is not always about design. 

**Aesthetics** (at least for the purposes of this lesson) is about having a site that is enjoyable to be in. 

[From Wikipedia - Aesthetics](http://en.wikipedia.org/wiki/Aesthetics)

	(Aesthetics) is more scientifically defined as the study of sensory or sensori-emotional values, sometimes called judgments of sentiment and taste.

Think about color, shape, composition, organization, and space (especially space) whenever you are designing. And after you think about those elements, think about how they may be distracting or enhancing the ultimate goal of your resource.

The philosophy of aesthetics makes the judgment of quality an extremely subjective matter. This is a good thing from an artistic standpoint, but makes designing an enjoyable website for a large group of users much more difficult, especially when designing for large to medium scale systems. 

For this reason, knowing the user or potential user is important for designing the overall aesthetics of the resource. Both the designer’s personal “aesthetic preference” and the user base’s “aesthetic preference” always will need to be balanced, but being conscious of both of these preferences will ease any potential disruption due to this element.

<p class="message">As an aside, I find that most people who come into this course either put themselves in the visual designer category or the code junkie category. When going through these lessons, consider which of the two you are stronger in and focus on the other. The code in this course is rather simple - so invest your efforts in expanding your design skills, but if you are a visual designer primarily, focus your efforts on understanding the coding concepts.</p>

*What are some common design trends, popular frameworks, or design ideologies that are prevalent now? Why do you think they are so popular?*

### 4. Performance

**Performance** is the speed with which your information is obtained by the user, but also how efficiently the user is able to navigate to the information they seek. Performance can apply to a broad range of topics such as bandwidth, file size, number of queries, usability, amongst other things. 

Performance is the easiest element to measure and has the most tangible benefits (tangible meaning money) for a resource. A lot of time and money can (and should) be dumped into improving performance of a resource. Nearly an infinite amount of factors will weigh on the performance for each individual, but the strategy of tackling the largest possible performance factors will provide solutions for most performance issues. 

*What are some additional performance factors you can think of?*

#### Site Speed Monitoring 

There are actual tools you can use to monitor the speed of your site that also help you improve performance. Spend some time messing around with these tools:

- [Google PageSpeed Plugin: https://developers.google.com/speed/pagespeed/](https://developers.google.com/speed/pagespeed/)

- [ySlow: http://yslow.org/](http://yslow.org/)

This Yahoo Developer article,has a great walkthrough of how performance can be monitored: [http://developer.yahoo.com/blogs/ydn/high-performance-sites-importance-front-end-performance-7160.html](http://developer.yahoo.com/blogs/ydn/high-performance-sites-importance-front-end-performance-7160.html)

We will talk more specifics about optimization and how a CMS can help influence performance later on in the course.

### 5. Usability

**Usability** is the efficiency with which a user is able to use (or interact and perform tasks with) something. Making sure the user of your resource can do so in a positive and efficient manner is one of the biggest challenges of designers. 

The key for usability is that the user does not notice that your site is usable or not usable - you want them to seamlessly interact with the resource.

#### “Is usability even important?”

It is easy to sell usability. If your resource is very usable then people will have a more positive reaction to it. If it is less usable there is a large chance that people will just not use your resource. The best possible way to demonstrate the importance of usability (or any of these elements) to a decision maker is to provide data. We will talk more about the effectiveness of using data in decision making later in the course. 

#### “Users will just figure it out - why waste time nitpicking over details?”

The worst mentality to take towards usability is “If they can’t use it, then it is their problem and they will learn.” This “brute force” method is not ideal, but may be inevitable (think Facebook). A more “seamless” method is much more desirable and should be the goal of the designer. The need to balance the two methods with often arise - especially if you are putting something into the marketplace that has not been considered before. 

#### “How do I even know usability is being applied?”

The good news is that there are methods in existence to measure and perfect usability. Some common methods include A/B testing, user feedback, and eye tracking software. 

Read [“Defining a Vision: Making Sure Your Work Matters,“](http://alistapart.com/article/defining-a-vision-making-sure-your-work-matters) an A List Apart article.
