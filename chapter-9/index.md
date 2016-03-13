---
layout: page
title: Chapter 9&#58; Advanced Topics
---
  
## Table of Contents

* [User Interface and User Experience in a CMS](#user-interface-and-user-experience-in-a-cms)
    * Effective Design Elements
    * UI/UX as Part of a Plan
* [Effective Resource Management in Large Scale Systems](#effective-resource-management-in-large-scale-systems)
    * [Tutorial: Specifying your Image Sizes in WordPress](#specifiying-your-image-sizes-in-wordpress)
* [Monitoring Your Site](#monitoring-your-site)
    * Tutorial: Integrating Google Analytics in WordPress
* [SEO Techniques in a CMS](#seo-techniques-in-a-cms)
    * Tutorial: Optimizing WordPress for SEO
* [Styling for Maximum Readability](#styling-for-maximum-readability)
* [Security Primer](#security-primer)
* [Various Readings](#various-readings)
    * “Evoking Trust" and "Knowing Everything”
    * "What is Code?"

## <a name="user-interface-and-user-experience-in-a-cms"></a>User Interface and User Experience in a CMS

Let’s start out our introduction to User Experience and User Interface by watching a video:

[What the #$%@ UX?](https://www.youtube.com/watch?v=Ovj4hFxko7c)

So the topics of UI and UX exist only on the periphery of this course's subject matter. However, the reason we will discuss this topic to a minor extent is because it is very important to everything that you do in the design and execution of a web site/application/resource. Additionally, there are direct ties between CMSs and UI/UX.

	User Experience Design (UXD or UED or XD) is the process of enhancing user satisfaction by improving the usability, accessibility, and pleasure provided in the interaction between the user and the product.

[Wikipedia - User Experience Design](http://en.wikipedia.org/wiki/User_experience_design) 

The Wikipedia article mentioned above has an invaluable outline of UX topics and processes. I recommend you read through it.

### “Effective Use of Design Elements” and User Interaction

We will discuss the following articles in this lecture: 

* [Flat UI and Forms](http://alistapart.com/article/flat-ui-and-forms)
* [Zebra Striping. Does it Help?](http://alistapart.com/article/zebrastripingdoesithelp)
* [40 More Delightful Examples of Attention to Detail](http://www.dtelepathy.com/blog/inspiration/40-more-delightful-examples-of-attention-to-detail)


Here are some questions to ask yourself when looking through these articles:

*Why do forms work so well with “flat design?”*

*What other popular design schemes do we have? Do they address forms well? Try to think of an example.*

*Even if zebra stripes on tables aren’t effective, can we/should we still use them?*

*Looking through the “delightful examples,” what are some that stand out to you as well done? What are some that don’t succeed?*

After you have read those articles, you should have a good grasp about UI generally and specifically. CMSs are intended to be intermediaries between data/the display of data, and the user so there is a need for the UI to be as friendly as possible. 

### UI/UX As Part of a Plan

When you are working with CMSs, there are always two different UIs: one for the person creating content and one for the person accessing it. Though there should be similarities, there should also be notable differences. 

Here is a short list of UI items the **site visitor** will want:

* Site identifier
* Clean display of content
* An attractive presence
* Navigation throughout the site to other content
<br /><br />

Here is a short list of UI items the **content manager** will want:

* Site identifier
* Clean method of inserting content
* A simple presence
* Tools to enhance and verify the quality of the content
<br /><br />

Though this list is clearer over-simplified, it demonstrates that the needs of the users are very different and the UI that they get will also be very different. The entire experience between the two is different therefore the UI will need to speak to that experiential difference. 

So what about the “...as part of a plan” thing? When you are designing a new site/application/anything you will, obviously, want to have a plan. 

One of the most popular UI as a plan documents is the [Google Material Design documentation](https://www.google.com/design/spec/material-design/introduction.html). If you browse through it you can see the thorough planning taking into account for every element. 

When coming up with your plan, here are some things to take into account:

1. **Tools:** What tools will you be using while you design? What are the limitations or benefits to these tools? Do you need more/different tools?
2. **Users:** Studying your users and their needs is the biggest part of usability
3. **Major Interface Elements:** What are the biggest things you are going to NEED to make your application work
4. **Minor Interface Elements:** What things add something to the UI but are not necessary? Do they help or hinder the overall process?
5. **Testing Methods:** What tools are you going to use to test? Can you identify a sample of your user group and get feedback? 

After you identify the things that will make up a part of your plan, creating and designing with these things in mind will help.

Additionally, you can always add new elements to the plan as you go and test, but the plan is key. 

#### Useful Links
* [12 Useful Techniques For Good User Interface Design](http://www.smashingmagazine.com/2009/01/12-useful-techniques-for-good-user-interface-design-in-web-applications/) - Old but still useful
* More to be added (if you have any to add, make a push request)

## <a name="seo-techniques-in-a-cms">SEO Techniques in a CMS</a>

SEO is short for Search Engine Optimization, which translates to trying to get your site to appear as high as possible on search sites (Google, Bing). SEO is one of the most important considerations for a business operating online (or in person as well). I am sure you are somewhat knowledgeable about SEO already, but we are going to discuss the topic in the form of strategy and techniques with regard to CMSs.

### SEO Strategy

The first thing we will consider is strategy. Consider [this Business Insider article for a list of 10 basic SEO tips](http://www.businessinsider.com/10-basic-seo-tips-everyone-should-know-2010-1?op=1).

Taking SEO into account from the start of a project will help you create a structure that is already successful on launch. 

*How do each of these 10 basic tips work with a content management system plan?*

Google provides a document that helps you analyze and enhance your site’s SEO. This is the sort of document you should memorize and should be built into any plan for a website that you have. 

[The Google SEO Starter Guide](http://static.googleusercontent.com/media/www.google.com/en//webmasters/docs/search-engine-optimization-starter-guide.pdf)

*After looking through this, what is one big thing you can do to improve your SEO immediately?*

#### Monitoring where you stand

The first thing that the Business Insider article suggests is that you make sure you are able to see whether your SEO is working in the first place. Any analytics monitoring should always include SEO data. 

The method by which people measure success of SEO is referred to as “page rank.” Having a strong page rank means your site appears highly for specific search results. 

There are many commercial and open source tools to monitor analytics and search engine strength. Some tools include [Google Webmaster Tools (https://www.google.com/webmasters/tools/)](https://www.google.com/webmasters/tools/) and [Bing Webmaster Tools (http://www.bing.com/toolbox/webmaster)](http://www.bing.com/toolbox/webmaster). Having a good monitoring structure built into your site will help you find strengths and weaknesses in your SEO strategy.

#### Specific SEO Elements

Within your coding you are able to take steps to ensure that your SEO will jump. Some of these elements include keywords, link backs, alt tags and description tags, and headers. Though even with all of these, there is one much more important way to ensure your SEO rises. We will talk about that later.

##### Keywords

One of the most misunderstood aspects of SEO are keywords. In ancient times, SEO was driven by meta tags full of keywords. This was due mostly to the less advanced algorithms that were used to search and led to savvy web developers plugging in lots of words in the head of the pages. However, as search algorithms got smarter they realized that the spamming of keywords were not a good indicator of quality. 

Now, keywords are used in a more subtle way and yet carry much more importance. Search bots no longer scan for keywords as stand alone content (as much), but rather look inside of site content. This site content includes titles, page text, URLs, image names and alt tags, and in description text. For a less aggressive SEO strategy, consider the places where search algorithms rank keywords the strongest, page headers and the site title tag. 

*What is a good strategy to getting your content managers to use accurate keywords?*

##### Link Backs

A link back is a link from one site to another - where the resource chooses to link back to the original linker. This is extremely effective when you have other websites link to you, but you can also leverage this for internal linking. One common way to do this is to have links to relevant articles or archives within your own posts/pages. Make sure that the links have text in them that points to their relevance, not just randomness - bots know what works and what doesn’t. 

#### Ultimate SEO Technique, REVEALED!

Wow, this ultimate technique must be really great, right? Well it is - and the good news is you can use it right now if you wanted. 

The secret to good SEO is to **have a site that is healthy, safe, and clearly organized.** Most web crawlers will look for this information before they take anything else into account. So what can you do to ensure this? 

1. **Healthy**: Have your site be fast and optimized. Make sure you aren’t loading too much extraneous stuff
2. **Safe**: No malware and have an SSL certificate. I know for this course we will probably not worry about SSL certificates, but making sure the data is coming and going securely makes a difference in one's SEO rank.
3. **Clearly Organized**: Using the elements listed above is step one (headers, description tags, etc.). Step two is to make sure that your content is organized in a logical manner, is navigable easily, and makes sense. This sounds a lot like UI, doesn’t it? Well, the bots that scan sites are quite advanced and are able to know when the content is good or bad - and when it is organized well or poorly. 

Basically, the secret to good SEO is to have a good website. 

#### Other SEO Techniques

* Sitemaps
* Search Friendly URLs
* Avoiding Flash (deprecated anyway…)
* Image Description Tags
* Link to Others (beware of link farms)

### SEO Techniques

#### Google SEO Starter Guide

Let’s look at [The Google SEO Starter Guide](http://static.googleusercontent.com/media/www.google.com/en//webmasters/docs/search-engine-optimization-starter-guide.pdf) and find some techniques to implement into our site.

*Which singular item did you choose from before? Can you implement that right now?*

*Which item in this guide probably does not apply to you? Any?*

#### Schema.org

[From the schema site](http://schema.org/): 

	This site provides a collection of schemas, i.e., html tags, that webmasters can use to markup their pages in ways recognized by major search providers. Search engines including Bing, Google, Yahoo! and Yandex rely on this markup to improve the display of search results, making it easier for people to find the right web pages.

	Many sites are generated from structured data, which is often stored in databases. When this data is formatted into HTML, it becomes very difficult to recover the original structured data. Many applications, especially search engines, can benefit greatly from direct access to this structured data. On-page markup enables search engines to understand the information on web pages and provide richer search results in order to make it easier for users to find relevant information on the web. Markup can also enable new tools and applications that make use of the structure.

	A shared markup vocabulary makes it easier for webmasters to decide on a markup schema and get the maximum benefit for their efforts. So, in the spirit of sitemaps.org, search engines have come together to provide a shared collection of schemas that webmasters can use.

Essentially, schema is a series of html indicators you can include in a site that will allow the search engines to automatically pull information from them. This is EXTREMELY useful in a CMS environment because the markup can go in the template and then as the site changes, the information fed to search engines will change with it. This allows you to add things like side bars in Google, or information about location, contact info, etc. for searches. 

*What do you think you can add to help your site work better with SEO using Schema.org?*

As a sidenote, Bing Webmaster Tools has a great tool for automatically adding this markup.

##### Tutorial: Integrating Schema.org

Coming Soon!

## <a name="effective-resource-management-in-large-scale-systems">Effective Resource Management in Large Scale Systems</a>

“Content management” shares some issues with resource management, however they also diverge at some points. While the terms “content” and “resource” are very vague, the methods by which we deal with them are unique. When we say “resource management,” we are more concerned with the efficient and organized access to resources, not what is or is not a resource. This is directly related to the “Performance” branch of the web elements. 

Some examples of effective web resource management would include:

* A low latency web server
* Well organized media folders
* Clean and efficient application code
* Utilize the protocols (i.e., HTTP) efficiently for serving files
* Intelligent information architecture

These are not simple goals to achieve, but are important for successful systems, especially when the systems may become large and have a wider reaching audience. 

How are some ways we can make sure we are managing our resources correctly? Let’s start by thinking about these things:

1. Make sure your system is the right size
2. Make sure your system is able to change sizes
3. Make sure you have backups (of both data and personnel)
4. Document your site (Github and/or documentation)
5. Always find ways to improve!
<br /><br />

*Can you think of another way to make sure you are managing resources efficiently?* 

### Specific Techniques to Optimize Resource Management

It is easy to talk about resource management as a theory, but applying it can be much more difficult. In fact, the difference between a good developer and a great developer is often found in efficiency and organization. So what are some things you can do to make sure you are outputting efficient and organized resources (or in this case, code)?

#### 1. Use a CSS Preprocessor (correctly)

Duplicated CSS code is one of the most common and easy to fix issues with site speed. Being incredibly organized is a lot easier than using a system that allows you to compartmentalize and take an object-oriented approach to your styling. 

You can learn more about CSS preprocessing and minifying here: [http://jayres.github.io/Web-Interactivity-and-Engagement//chapter-7/#css-and-template-development](http://jayres.github.io/Web-Interactivity-and-Engagement//chapter-7/#css-and-template-development)

#### 2. Conditional Loading of Files

This one is obvious. Don’t load files you don’t need. The implementation of this is a bit more difficult though. Consider your system and try to make the loading occur after the page load to determine which files need to be loaded. [Reference the conditional loading tutorial for some ideas](http://jayres.github.io/Web-Interactivity-and-Engagement//chapter-8/#enqueuing-files-in-wordpress).

#### 3. CDN (Content Delivery Networks)

Until everything supports HTTP2, you are only able to send one file concurrently over a single connection. This has a big impact on the order you load your files (smallest first) and how many files you can load (as few as possible). Using a CDN is a good way to avoid this concurrent file restriction. Some common CDNs we use are jQuery, Font Awesome, and Google Fonts. 

The downside to CDNs is that you are reliant on their speed and dependability. Make sure you trust the CDN you are using and keep duplicates of the dependent files on your servers (in case they are no longer hosted). 

#### 4. Images, Images, Images

This one is also obvious but can’t really be overstated. Even large media sites have issues with loading the correct size images on the correct devices. There are hundreds of articles with both justification and techniques on the internet for ensuring the correct file size loads. 

#### 5. Optimizing Hosting Services

Don’t use GoDaddy or another host service that has bad latency from the start. Shared servers are often slower than dedicated hosts. A good cloud hosting company may only drop your latency (and thus your load time) by milliseconds (though, sometimes in the hundreds) but when aggregated on the whole could affect your site speed considerably - and thus your user base and the company’s bottom line. 

However, until you need to scale up to a stronger hosting environment, you probably don’t want to dump money into such a service. This is where the “make sure your system is the right size” issue and the “make sure your system is able to change sizes” issues converge.

*What are some other techniques you can think of for efficient resource management?*

### <a name="specifiying-your-image-sizes-in-wordpress">Tutorial: Specifying your Image Sizes in WordPress</a>

Since we have emphasized that images are the single biggest performance issue for large scale systems, let’s implement a strict image policy into WordPress. By only using the exact sizes for our images, we will avoid a loss of quality and also avoid loading oversized images. 

Luckily for us, WordPress has some built in image editing to account for optimized images. Let’s identify our ideal image sizes for our template and then make those sizes the default sizes. 

#### Step One: Define our Image Sizes

For our site there are a few default image sizes:

* Thumbnail: 150px x 150px (for post and page thumbnails)
* Medium: 300px x 300px
* Large: 1024px x 1024px
* Full: Whatever size the image was uploaded to.
<br /><br />

These may not correspond with your theme or your site at all though. You are able to override these sizes, but let’s make use of WordPress functionality to strictly define the sizes of some of our images we know we will use. Take some time to figure out what image sizes exist in your template. 

For us, let’s imagine we are going to use the following sizes in certain situations:

* Front page slider images: 940px x 300px
* Thumbnails for posts: 200px x 200px
* Profile Images: 200px x 300px
<br /><br />

*Are you using a ton of different image sizes throughout and wouldn’t it be better if you had more uniformity?*

#### Step Two: Set Image Sizes in WordPress

WordPress uses the “add_image_size” function to allow you to define your custom images. Let’s register these sizes in our functions file and then add a condition for us to display them as a selection mechanism in the image selection screen. You must have theme support post thumbnails enabled for this to work. 

```php
<?php
add_image_size( 'front-slider', 940, 300, true ); // width, height, crop
add_image_size( 'blog-post-thumbnails', 200, 200, true );
add_image_size( 'profile-images', 200, 300, true );

// Register the image sizes
function wie_custom_image_sizes( $sizes ) {
    return array_merge( $sizes, array(
        'front-slider' => __( 'Front Slider Image' ),
        'blog-post-thumbnails' => __( 'Blog Post Thumbnails' ),
        'profile-images' => __( 'Profile Images' ),
    ) );
}
add_filter( 'image_size_names', wie_custom_image_sizes );
?>
```

#### Step Three: Reference New Image Sizes

Let’s use our blog-post-thumbnails custom size in our regular loop as demonstration.

```php
<?php
query_posts('offset=1');
if ( have_posts() ) {
    while ( have_posts() ) {
        the_post();
        if ( has_post_thumbnail() ) { ?>
            <div class="post-thumbnail-front">
                <?php the_post_thumbnail(blog-post-thumbnails); ?>
            </div> 
        <?php } ?>
        <h3><?php the_title(); ?></h3>
        <?php the_excerpt(); ?>
        <p><a href="<?php the_permalink(); ?>">Read More</a></p>
        <div class="clear"></div>
    <?php }
}  else {
    echo "No Posts, sorry";
} ?>
```

#### Step Four: Save and Upload

You should now see the image size changed. You can also implement the other sizes however you see fit. 

Reference: [Adding and Using WordPress Custom Image Sizes: A Guide to the Best Thing Ever](http://wpshout.com/adding-using-custom-image-sizes-wordpress-guide-best-thing-ever/)

## <a name="monitoring-your-site">Monitoring Your Site</a>

Making sure you are keeping track of what is happening in your site and the behavior of your users is crucial to a successful website. Business sites and blog sites may have different audiences and concerns regarding content, but all types of sites will need to gather and analyze data.

There are plenty of tools, both paid and free, to monitor your site’s analytics. Additionally, if you have a more complicated and/or busier site then you will need to also consider analytics for your server and database.

A very good (and free) analytics platform is Google Analytics. This application can get you pretty far into your analytics and makes for a good introduction into collection and analyzing analytics. 


### Tutorial: Integrating Google Analytics in WordPress

*Coming Soon*

## <a name="styling-for-maximum-readability">Styling for Maximum Readability</a>
As a general rule, you are going to want to make sure the content you present is visible and readable. You don’t need me to tell you that though. The first step to attaining this goal is to avoid obvious distractions (backgrounds behind text, lack of contrast, text too small or too big, etc.). If you follow that first step, odds are people won’t complain too much about your site’s readability. However, you will probably want to aim higher than “good enough.”

Many of the statements below are suggestions and are based off an assumption that you are using a readable system font. As with all things in design, there are trends which carry weight and differing opinions about what is best - so a lot of the things I say below are based off a representative set of research and experiences. 

### Reset CSS Document

One huge way to make sure your site is as readable as possible is to ensure that all styles from the user agent (i.e., the browser) are overwritten right off the bat. There are many ways to implement a CSS Reset, but one easy and free way to do so is to include Normalize at the top of your CSS file tree. 

[Normalize CSS](https://necolas.github.io/normalize.css/)

### Headings

The primary use of headers is not to spread different sized text throughout your site, but rather to organize content in a logical manner. If all of your headings (h1, h2, h3, …) were the same size it would still be possible for you to organize your site logically without worrying about things being different sizes. However, headings are often used in a manner where size is taken into consideration. 

It is okay to use headings with size as one of the properties of their hierarchy, but remember that their primary function is that of content organization. Readability is not just limited to the ability to see the words, but also the ability to parse the content efficiently and accurately. 

### Body Copy

As a general rule, the base font size should be 14px or 16px. I tend to prefer 16px because it is better to go too big as opposed to too small. 

**Line height** is the space between rows of text. you generally will want the space between to be 1.5 times your font size. This allows your text room to breathe without creating a break in the scannability of the text. 

**Line length** is determined by the number of characters per line. It is possible to implement a complicated method for enforcing a strict rule to this, but estimating based off of your font size is usually fine. There are differing opinions about how wide this should be, with opinions ranging from 50 - 75 characters depending on factors such as font choice, font size, and font weight (and letter spacing if you are deviating from the default).  This is further complicated by different screen sizes for responsive design (a mobile screen may want LESS than that for each line to be readable. Make sure you are testing your line length as you would test anything.

Since we are using a grid system in class that has a default width of around 940px and our default font size supports about 120 - 150 for a full width screen on desktop. This means we would want our reading area to be about 50% of the full width (in our case, six columns). On mobile it handles the text much better but you may want to watch out for variations and ensure uniformity. 

Also, it is generally accepted that **serif fonts are easier to read** than sans serif fonts. There is a definite trend towards using sans serif fonts, but consider implementing two fonts - one for body text and one for headings and other text. 

### General Concerns

Contrast is a huge issue, especially for those who have accessibility issues. As a base, you want to have the lightest color background (i.e., white) with the darkest color text (i.e., black).

Letter spacing (a.k.a., kerning) is the space between letters and plays a HUGE roll in readability. It is mostly unwise to mess with a font’s default letter spacing if you are using a major font (times new roman, arial, etc.). 

### Putting it all together

Let’s create a sample css document that maximizes our readability requirements. You may find this css document boring, but it is a good place to start and then whenever you make a change, you can consider it accordingly. 

```css
body {
    font: /*insert your base font here - may be sans serif */;
    font-size: 16px;
    color: #000;
    background: #fff;
}

p {
    font: /*insert a serif font here */;
    line-height: 1.5rem;
}
```

[Readability: the Optimal Line Length - Baymard Institute ](http://baymard.com/blog/line-length-readability)
[Read-able: Web Readability Test Tool](http://read-able.com/)
[Balancing Line Length - Smashing Magazine ](http://www.smashingmagazine.com/2014/09/balancing-line-length-font-size-responsive-web-design/)

### Tutorial: Implement Changes to Our Site for Readability
We are going to want to go through the following steps to enhance our site’s readability using what we learned above.

1. Integrate the CSS into our site
2. Make sure our text areas are six columns wide
3. Make sure headers are used correctly

## <a name="security-primer">Security Primer</a>

Security is something that should be taken VERY seriously. I want to say that **I am not a security expert by any means**, but can speak to some basic techniques in web security that can prevent obvious attempts at your site’s security. Every major website (and company) has either security personnel on staff or security consultancy on call. It is one of the most complicated parts of any IT organization and requires high levels of specialty and experience to do effectively. 

### Basics of Web Security

The reality is that most “attacks” on web sites and computers are due to users following bad protocol. The essential things to know when it comes to web security are generally obvious. Here is a list of some of the obvious ones: 

* Have difficult to guess passwords
* Make sure your passwords aren’t written down on your desk (or in an email/text/other easy to read medium)
* Take advantage of two step authentication when available
* Share your passwords as little as possible
* Change your passwords frequently
* Update your sites/servers/resources often
* Take special care with personal information and/or data
* Monitor your resources to make sure there is no suspicious behavior
* Don’t put strange files/programs onto your server, and…
* Make sure you trust all of the files/programs you do end up using.

The reason this list is obvious is because it has been so ingrained into our computer use. However, these simple rules are also the places where most breaches in security occur so ensure that you follow them and implement them into your resources.

### SSL and HTTPS

Using HTTPS as opposed to HTTP is a good way to prevent a lot of issues with security and it also is a boost to SEO. 

For a site to use HTTPS, there must be an SSL certificate in place. An SSL Certificate allows for an encrypted handshake to take place between the browser and the server - this preventing data from being skimmed.

The only downside to using an SSL certificate is the continued cost to attach it to your site. The cost is rather minor and every functioning site that has server communication (and primarily authentication) should have an SSL certificate. Most hosts will have an easy setup for including an SSL certificate so that your site can operate over HTTPS. 

[Google - Getting Started with SSL](https://support.google.com/adwords/answer/2580401?hl=en)

### WordPress Security

WordPress gets a bad rap for being insecure. It is rarely WordPress that is insecure though, but rather the users who fail to follow the basics of web security listed above. 

Here are a few steps you can take to improve your security situation for WordPress:

* Keep your WordPress installation up to date! This is the easiest and most important of all the security steps.
* Use SSL (see above).
* Have a unique username and hard to guess password - this means deleting your “admin” user completely. This will prevent most brute force attacks.
* Change the location of your WordPress login. [ManageWP Blog - Change WordPress Login URL](https://managewp.com/change-your-wordpress-login-url)
* Limit login attempts (plugins available).
* Turn off comments and make sure you manage user accounts carefully. One slip up from one user is all you need to make your site vulnerable. 

## <a name="various-readings">Various Readings</a>

### [“Evoking Online Trust” by Seth Godin](http://sethgodin.typepad.com/seths_blog/2013/11/evoking-online-trust.html)

### [“Never Heard of It” by Lyza Danger Gardner](http://alistapart.com/column/never-heard-of-it)