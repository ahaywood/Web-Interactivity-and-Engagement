---
layout: page
title: Chapter 5&#58; Content and the Content Manager
---

## Table of Contents

* [Content Generally](#content-generally)
	* Portability of Content
	* Handling Content
	* Information Architecture
* [Choosing a CMS](#choosing-a-cms)
	* CMSs to Choose From
	* Factors to Consider When Choosing
* [Elements of Web Design and CMSs](#elements-of-web-design-and-cmss)
* [Wireframing and Mocking Up a Site for a CMS](#wireframing)

## <a name="content-generally">Content Generally</a>

Content "is information and experiences that provides value for an end-user or audience." [Content - Wikipedia](http://en.wikipedia.org/wiki/Content_(media))

For us, **content** is text, images, video, audio, or anything that conveys information or experiences to a user. We will use this term generally because it isn't important to get into the specifics or etymology of the term. What is important is that there is information that needs to be sent to a user effectively and efficiently. 

Dealing with content can be a complicated affair. Before we can even begin to think about how to handle content through a CMS, we must first identify what content we are trying to manage.

*What content would be difficult to distribute in WordPress?*

It is easy to think about one CMS managing all content effectively, but the reality is that content management is never so simple. Each type of content has different characteristics that make each unique in their management challenges. 

We are going to look at three articles to get a better grasp of how content exists and why it is important to consider the content before you even begin to design any resource to handle it. 

* [Your Content, Now Mobile - A List Apart](http://alistapart.com/article/your-content-now-mobile)
* [Strategic Content Management - A List Apart](http://alistapart.com/article/strategic-content-management)
* [Content Modelling: A Master Skill - A List Apart](http://alistapart.com/article/content-modelling-a-master-skill)

### Portability of Content

Making sure you are able to control where your content goes is important for numerous reasons. Having your blog posts show up on your site is one step, but also allowing RSS readers (or their equivalents) to display your blog posts could be cool too. Additionally, what if another site wants to use your content? What if a teacher wants to use the content in a lecture? 

Isn't having your content distributed as widely as possible a good thing? Well, maybe not always. The concept of portability with content is an important consideration when you are crafting your content strategy. For every instance where you would want visibility of your content, there may exist one where you don't want it to be visible.

*What are some instances where you would want your content to be more visible? instances where you wouldn't?*

Let's say you do want your content to be widely distributed. If you do that, it would be nice to have it as easy to access as possible. And not only by users, but also by other systems that may want to use that content. This is the whole concept of an Open API platform. 

<!--

Note from @chrisallenlane:

The term "Open API" has been made unfortunately ambiguous recently. I assume
that, above, you're referring to "Open API" in this sense:

https://en.wikipedia.org/wiki/Open_API

As of Jan 1 2016, however, swagger.io (the API description tool) has been
adopted by the industry broadly and renamed as the Open API Initiative:

https://openapis.org/

Using the term as the former is still correct, of course - but now students may
become confused by conflicting Google results.

Perhaps it's worth using the more generic phrase "public API" instead of "Open
API"? Alternatively, it might be worth explicity making the distinction between
the general and specific uses in a "message" div or something.

-->

Additionally, you will want to "future-proof" your content early. Let's read a passage from the ["Your Content, Now Mobile" article](http://alistapart.com/article/your-content-now-mobile): 

<blockquote>"If you take the time to figure out the right way to get your content out there, you'll have the freedom (and the flexibility) to get it everywhere. You can go back to thinking about the right design and development approaches for each platform, because you'll already have a reusable base of content to work from."</blockquote>

<blockquote>"By taking the time now to examine your content and structure it for maximum flexibility and reuse, you'll be (better) prepared the next time a new gadget rolls around. You'll have cleared out all the dead wood, by pruning outdated, badly written, and irrelevant content, which means all your users will have a better experience. You'll have revised and updated your processes and tools for managing and maintaining content, which means all the content you create in every channel—print, desktop, mobile, TV, social—will be more closely governed."</blockquote>

### Handling Content

We now know that we will want to consider how expansively our content should be used very early on in our design steps. After, we need to consider what approach we should use to implement our content management plan. 

<p class='message'>I acknowledge that a "content management plan" or "content strategy" may not be an explicit plan for every project (certainly not the ones covered in this course), but considering the scope of how to use content will help you make better decisions as you go.</p>

Content strategy is a key step in any design process.  You should read this article in its entirety: [Strategic Content Management - A List Apart](http://alistapart.com/article/strategic-content-management)

Technology plays a big role in how we handle content. In olden days, people would manage content using file folders and whatever other sorting mechanisms suited a particular organization. However, with the emergence of computers as tools, content management (or organizing content in some cases) has become more efficient and complex. Databases, file structures, and metadata all help us organize our content more logically. CMSs and other administration mechanisms allow us to distribute, create, and alter content more effectively. With the emergence of more complicated tools comes the need for better planning and consideration of the content strategy. 

Content and the technology to manage content go hand in hand with the impression and effectiveness that your content will have on a user. 

### Information Architecture

After making sure we know how we want to use our content and what methods we are going to use to handle the content, we will think about the overall organization and presentation of our content. That's where information architecture comes in. 

> Information architecture (IA) focuses on organizing, structuring, and labeling content in an effective and sustainable way.  The goal is to help users find information and complete tasks.
[Information Architecture Basics - Usability.gov](http://www.usability.gov/what-and-why/information-architecture.html)

Read the ["Content Modelling: A Master Skill"](http://alistapart.com/article/content-modelling-a-master-skill) article to get a grasp on how one might think about using information architecture as a content planning tool. 

Structure of our content to the systems, users, and administrators of the content will shape the way people think about the content and how usable it will be to users. 

<!--

Note from @chrisallenlane:

Perhaps the phrase "version control solution" in the next paragraph is somewhat
confusing, because that term usually refers to programs like git, mercurial,
svn, etc. (It's true that some flat-file CMSes - Jekyll, Metalsmith, etc. - use
git for versioning, but I would argue that the "version control solution" is
not itself the CMS.)

I think I understand what you're getting at, though. Perhaps here, instead of
using the phrase "version control solution", the phrase "flat-file CMS" would
be more appropriate?

-->

Each CMS will have inherent biases to the content and the way it is organized. A blog CMS will treat organization differently than an image handling software. A version control solution will treat content differently than a ecommerce CMS. Developing a content strategy plan and an information architecture plan is a great first step to choosing a CMS.

## <a name="choosing-a-cms">Choosing a CMS</a>

When you are choosing a CMS, don't always go with the one that you are most comfortable with or that the client wants/already has.  Choosing a CMS is a very specific choice depending on the situation and whether you consider yourself more of a coder, administrator, or designer, having the ability to choose the system of a correct scale for a client is a useful skill. 

##### So how do we choose the right CMS? 

*Would Amazon want the same CMS as Delta Airlines?*

*Would the Miami Dolphins need the same CMS as the Florida Aquarium?*

*How about Mom and Pop shop vs. a multinational corporation?*


### CMSs to Choose From

I am going to list 6 CMSs that are currently in use. With them will be a brief (and vastly oversimplified) description of them with their strengths and weaknesses. I want you to consider how they all are able to perform different tasks better than others and what circumstances you could foresee for using them.

There are obviously a lot more than these 6 and this list may become out of date rather quickly, so if nothing else use this section as a learning tool. If you want to add one or replace one with another that you know better, please feel free to do so through GitHub. 

#### 1. WordPress

**Description:** The world's most popular CMS at this moment. WordPress was originally a blogging platform that has expanded into a full use CMS with a lot of extensibility. 

**Technical Specs:** PHP, MySQL

**Pros:** Easy templating and modification, good community of support, easy to use UI, lots of plugins
**Cons:** Potential security issues, limiting functionality without significant development, frequent updates.

#### 2. [Drupal](http://en.wikipedia.org/wiki/Drupal)

**Description:** "It is used as a back-end framework for at least 2.1% of all Web sites worldwide ranging from personal blogs to corporate, political, and government sites including WhiteHouse.gov and data.gov.uk. It is also used for knowledge management and business collaboration. The standard release of Drupal, known as Drupal core, contains basic features common to content management systems."

**Technical Specs:** PHP, MySQL

**Pros:** Large community, PHP, lots of plugins (modules)
**Cons:** Usability concerns, performance/scalability, outdated plugins (modules)

#### [3. Liferay](http://en.wikipedia.org/wiki/Liferay)

**Description:** Liferay Portal is a web platform that includes a built-in web content management system allowing users to build websites and portals as an assembly of themes, pages, portlets/gadgets and a common navigation. Liferay is sometimes described as a content management framework or a web application framework. Liferay's support for plugins extends into multiple programming languages, including support for PHP and Ruby portlets. Although Liferay offers a sophisticated programming interface for developers, no programming skills are required for basic website installation and administration.

**Technical Specs:** Java

**Pros:** Little to no development experience needed to implement, framework with a lot of other plugins, Scalable
**Cons:** Java, huge learning curve, bulky

#### [4. SquareSpace](http://en.wikipedia.org/wiki/Squarespace)

**Description:** Squarespace is a SaaS-based content management system (CMS) which is composed of a website builder, blogging platform and hosting service. The service allows individuals and businesses to create and maintain websites and blogs.

**Technical Specs:** 100% in-browser editor.

**Pros:** Easy to use, all technical requirements are handled for you.

**Cons:** Limited functionality, no customization


#### 5. A Homemade CMS

**Description:** A special project from scratch that does exactly what the client wants and needs. 

**Technical Specs:** Whatever you want or need

**Pros:** Nearly all needs are met - so the pros are unlimited.

**Cons:** Potentially infinite cost and project time. 

#### 6. A File Cabinet

**Description:** A piece of metal that holds file folders.

**Technical Specs:** Whatever sorting methods the previous person used.

**Pros:** Simple and cost effective.

**Cons:** May be too simple and comes with no dynamic content management.

### Factors to Consider When Choosing

This will by no means be an exhaustive list and depending on the project specifications each factor may have different importance. 

#### 1. Content

Making sure you know what type of content you are dealing with makes the weeding down portion of the CMS selection process a lot easier. Consider types of content and how the CMSs individually handle that type of content (if they do at all). 

#### 2. Portability and Distribution of Content

We talked about the importance of portability and distribution of content above, but how do we measure how well a CMS performs those tasks? This is not an easy question to answer, but the more you learn about this topic the better you will become a making decisions about how portable content is. 

We also want to make sure that we even want our content to be portable or distributable (see security concerns below). 

#### 3. Information Architecture

Many CMSs have built in information architecture structures. These are very, very important to consider when choosing. Also, if you have an IA plan coming into the selection process you will want to make sure your plan is executable under the CMSs you are reviewing. 

#### 4. Client

The client might be the single biggest factor in your choice of a CMS. A lot will depend on what the client wants and what they are capable of. Making sure you consult heavily with the client will help you get to the best fit for the client, but also will give you buy in for your decisions from the client (which will save you a lot of headaches down the road). 

##### Things to consider about the client:

1. *Current size of the organization*: Knowing the size of the organization will help you make a decision about the next factor (scale of the CMS). 
2. *Potential future size of the organization*: You are going to want to make sure that if you choose a CMS, it will be able to grow with the organization. Obviously you won't be a mind reader but you should inquire to both growth strategies that are currently in place. 
3. *Technological capabilities of the organization and its staff*: If the staff is not very technically able, you are going to want to consider the UI of the CMS from the content manager position a lot more heavily. 
4. *Percentage of organizational operations that occur on the internet*: Not only percentage, but also the types of transactions the organization undertakes online. Your CMS is going to want to perform or integrate with tasks that are key to the business. So extensibility may play a bigger role depending on the type of business that the organization undertakes. 
5. *Security needs of the organization*: This will be huge. A organization that needs a blog will have entirely different needs than an organization that handles sensitive documents and data (especially medical organizations). Make sure you are not giving them a solution that will come back to cause liability for that organization. I know getting into security can be both intimidating and overwhelming, but making sure you know of potential security concerns can help you make a decision or consult with others about what the best decision would be. 


<!--

Note from @chrisallenlane:

With point 5 above, it may be worth mentioning HIPAA by name, just to expose
students to the term. It may also be worth noting that rigorous regulations
(PCI DSS, commonly referred to as "PCI compliance") likewise apply to
applications that store credit card data.

-->


#### 5. Scale of the System

You don't want to get a CMS that is too big and slow when what you need is small and fast. This is obvious but is also an important consideration. Additionally, having a system that is the right scale, but also scalable to larger or smaller sizes will help you serve your client better if they do grow or shrink without having to make a huge jump in technology. 


### Applying What We've Learned

Let's consider the following fact patterns and attempt to choose the best CMS from the above list.

a. Small neighborhood market that has trouble with people finding where it is

b. Large, local office supply store that wants to start selling online

c. Florida non-profit that wants to have a larger public face

d. Internet startup that wants to sell doodads 

e. Internet startup that wants to sell consulting services

f. Local doctor's office

*Do you see how there can be vaguery for each of these and several might fit the needs to the client?* 

## <a name="elements-of-web-design-and-cmss">Elements of Web Design and CMSs</a>

We understand what a CMS is and a process to select a CMS, but what about the other important aspects of web design we talked about earlier?

Let's talk briefly about the elements in the context of a CMS and CMS selection.

### Environment:

<p class='message'>Environment is essentially a grouping of concepts/items/situations related to the user at the time of accessing a resource.</p>

*Is there something inherent about a CMS that will affect the user when they're accessing the resource?* 

### Story

<p class='message'>Story encompasses the content and the display of the resource as a method of communicating a message.</p>

*What role does a CMS have in the story you tell? Should it have any role at all?*

### Aesthetics

<p class='message'>Aesthetics is about having a site that is enjoyable to be in.</p>

*How could a CMS help with the aesthetic quality of a CMS? How could it hinder it?*

### Performance

<p class='message'>Performance is the speed with which your information is obtained by the user, but also how efficiently the user is able to navigate to the information they seek.</p>

Performance is definitely one of the most important choices with a CMS. It is also one of the most tangible to measure (both in general web design and in CMS selection). A good CMS will consider performance in its infrastructure (especially for file handling and serving). 

*Can a CMS solve all of your performance concerns? How can it relieve some of your performance concerns?*

### Usability

<p class='message'>Usability is the efficiency with which a user is able to use (or interact and perform tasks with) something. Making sure the user of your resource can do so in a positive and efficient manner is one of the biggest challenges of designers.</p>

Having a CMS that can both stay out of the way of usability and enhance the experience for the content managers would be amazing. There are plenty of CMSs that do these two things, but inevitably situations will arise where usability frustrations come from the structure of the CMS. 

*What role does a CMS play in the usability for users of your site?*

*What role does a CMS play for the content manager's usability?*

## <a name="wireframing">Wireframing and Mock-up Up a Site for a CMS</a>

### Wireframes

The process of wireframing may seem like busy work. However, it actually is a really, really important step in creating a new web site or other resource. 

> Wireframes are created for the purpose of arranging elements to best accomplish a particular purpose. The purpose is usually being informed by a business objective and a creative idea. The wireframe depicts the page layout or arrangement of the website's content, including interface elements and navigational systems, and how they work together. The wireframe usually lacks typographic style, color, or graphics, since the main focus lies in functionality, behavior, and priority of content.[3] In other words, it focuses on what a screen does, not what it looks like.

[From Wikipedia - Website Wireframe](http://en.wikipedia.org/wiki/Website_wireframe)

There are many, many ways you can make a wireframe - from a pencil drawing to a photoshop mock-up to using a web tool for help. The style of a mock-up may differ for different organizations. Personally, I feel that anything that works in effectively conveying the UI, layout, and potential content is good enough though.

*After you make the wireframes, what would the next step be?*

Well, in most design organizations you would take the wireframes and perform a critique of them, refine them, and repeat until you have a solid structure for the CSS specialists and the graphic designers to work with. Additionally, you would perform UI and UX testing and then further refine the structure. Additionally, the wireframes would be subject to change throughout the design process depending on changed circumstance. 

For our course though, we are going to use a more "self-intuition" method of choosing and refining wireframes. However, they are an important step in the design process - even if we aren't going to test the wireframes for effectiveness. 

#### Wireframing Resources

[Beginners Guide to Wireframing](http://webdesign.tutsplus.com/tutorials/workflow-tutorials/a-beginners-guide-to-wireframing/)

[Balsamiq - Wireframing tool](https://balsamiq.com/)

[Wireframe.cc - untested by me](https://wireframe.cc/)

[Wireframing Information - Wikipedia](http://en.wikipedia.org/wiki/Website_wireframe)

### Visual Mock-ups

If there was a lot of vaguery in the wireframing process above, there will be even more in the visual mock-up category. However, these are often the more important of the two for the client. 

#### The visual mock-up provides two benefits.

The first is that you are able to make design decisions from a more tactile standpoint. Having an accurate visual representation of the project will help you balance all of the design decisions early on in the process.  

Additionally, all of the technical specifications in the wireframe and project proposal will not always convey the look, feel, and direction of the project. Clients are often non-technical and need something pretty to look at. Having something pretty to show them will help convey your direction with the project. 

#### Making a visual mock-up

Well, there is no tutorial here, only advice.

Each person will, inevitably, have their own method for doing this. I tend to take my wireframes and copy them into Photoshop (or illustrator). I will then gather other project specifications such as colors, images, fonts, etc. and space out potential content. Having several versions of a single mock-up is always a good idea. I will often start over from scratch several times so that I don't get embedded in a single way of doing something.
