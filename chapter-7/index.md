---
layout: page
title: Chapter 7&#58; Advanced Theme Development
---

## Table of Contents

- [CSS and Template Development](#css-and-template-development)
    - Tutorial: Adding the Basic CSS for a Template
- [JavaScript and Adding Functionality](#javascript-and-adding-functionality)
    - The wp-includes folder
- [WordPress Dynamic File Loading](#wordpress-dynamic-file-loading)
    - Tutorial: Linking to JavaScript and CSS Files Correctly in WordPress

## <a name="css-and-template-development">CSS and Template Development</a>

In an ideal world you will have a complete team of individuals who do nothing but design and create a style guide and you will have a team that only does front end work (HTML, CSS, JavaScript) to realize the dreams of those designers and to properly implement the style guide. However, sometimes we will have to take on several roles at the same time and be both the designer and the front end dev. This is okay though because having an understanding of both roles allows you to be better at each individually. Knowing the front end workflows and results/expectations (regardless of your role) is an important part of being a competent web professional. 

CSS is (as we know) the language that makes things pretty. It is a very powerful language that controls much of what we see and do on a webpage. CSS is the primary tool that is used to bring a designer’s vision to life. So how is this relevant to template development?

Well, CSS is merely a series of rules that the browser follows to display content. And a template is merely a series of rules that the browser (or server) follows to display content. CSS is only one part of a template, but is an integral part of how a template works. Making sure you are using CSS correctly can improve performance, organization, and portability. If you use CSS poorly, you will have bloat, bugs, and ugliness. 

This is worth pointing out because in templating, having highly specific CSS rules is counter-intuitive to the entire philosophy. It also can produce inconsistencies in the site and thus cause confusion (probably not, but it will at least look funky which can throw a user off). 

### Frameworks

One way we deal with the uniformity and efficiency issue with CSS is through frameworks. In this book we have already used the Skeleton framework which is a relatively small grid and style system to build off of. There are many other frameworks which are significantly more or less bloated. Frameworks like [Bootstrap](http://getbootstrap.com/) tend to be a lot larger in file size but provide signficant additional services for their users. Skeleton is definitely on the slimmer side of frameworks but you should know that there are many parts of Skeleton that we will never use. 

Loading unused CSS rules is basically the worst part of CSS frameworks. When you have a larger framework like Bootstrap you are certainly sacrificing some site speed in lieu of development time (less time writing code but more time loading pages). The opposite is true for smaller frameworks.

You have a few options with dealing with this problem:

- Accept the bloat and move on (and also accept the judgment of other web developers for having too much bloat)
- Don’t use a framework (obviously)
- Edit an existing framework to only contain the rules you need (could be a lot of work which would negate the whole reason you used a framework to begin with)
- Find the best framework that fits your needs as closely as possible and accept whatever judgment that may come

Having knowledge about the range of frameworks available to you will help you make the best decision here. Also, it may be good to make your own framework at some point so that you can quickly spin up a site on the fly with only the rules you need for your project. 

### Minifying and CSS Preprocessing

Two common methods of dealing with bloat from CSS (and frameworks too) is using a CSS preprocessing language and also using a technique called minifying. 

#### Minifying

You are probably well aware of the concept of minifying. Minifying is the process of taking development code and making it production ready by removing unnecessary spaces in the code. This is often done through a minifying command line tool or some other application. Many modern CMSs and application frameworks even have a minifying agent built in. Minifying is also not limited to CSS but also applies to any front end file that is loaded into a browser.

For more information feel free to [read this article about minification](http://en.wikipedia.org/wiki/Minification_%28programming%29). 

One important note about minifying is that it should only be done when a file is ready to go into production. If you are presumptuous about minifying, it can lead to difficult in editing and modifying development level code. Making minifying part of your work flow is an important step though.

#### CSS Preprocessors (LESS/SASS)

CSS is a great language that is easy to use. However, it can become bulky and hard to manage on larger projects. Additionally, it is not the easiest to compartmentalize and there are some things aspects of other programming languages that could be implemented into CSS to make it easier to program.

This is where a CSS preprocessor comes into play. In many ways, using LESS or SASS (both popular CSS preprocessors) is an industry standard. I will not teach these in this course, but I urge you to become familiar with at least one of them and believe that they are valuable and useful tools. 

[SASS](http://sass-lang.com/):

Sass is an extension of CSS that adds power and elegance to the basic language. It allows you to use variables, nested rules, mixins, inline imports, and more, all with a fully CSS-compatible syntax. Sass helps keep large stylesheets well-organized, and get small stylesheets up and running quickly, particularly with the help of the Compass style library.
from [SASS Documentation](http://sass-lang.com/documentation/file.SASS_REFERENCE.html)

[LESS](http://lesscss.org/):

Less is a CSS pre-processor, meaning that it extends the CSS language, adding features that allow variables, mixins, functions and many other techniques that allow you to make CSS that is more maintainable, themable and extendable.

As you can see they basically do the exact same thing but have slightly different syntax. 

Being slightly familiar with both but focusing on using one is generally the standard for most web developers. Being comfortable with a CSS preprocessor can greatly speed up your development time and make you more marketable as a developer or project manager. 

### Tutorial: Adding the Basic CSS for a Template

After the interesting discussion about minifying and preprocessing, we are going to return to something more rudimentary - basic CSS for a template. Every template will need CSS so long as it is web based. Furthermore, as we discussed above, having standard and well thought out universal rules will make the template more effective, efficient, and speed up development time. 

This will involve the following:

- Pre-planning colors, spacing, and text
- Default text treatment
- Default headers treatment
- Some Utility classes
- Other Common Elements and Classes

As a note, much of this would become incredibly easy with the correct usage of a CSS preprocessor and I urge you, as an exercise, to attempt to learn one of the above preprocessors while you work through this tutorial.

#### Step 1: Pre-planning Colors, Spacing, and Text

We should already have an idea of what our site will look like and what our goals will be. Making sure we have a clear UI flow and visual direction at this point is key. Some important information to gather at this point includes:

- Colors
- Fonts
- Potential functional requirements that rely on CSS (jQuery style elements, layout issues, content handling like images, etc.)

*So first off, what are the colors you are using?*

*Have you chosen a font?* (Note: Use the Chapter 8 Tutorial: Custom Fonts to integrate custom font into your site)

*Can you make a short list of elements that will need styling?*

- Image thumbnails?
- Quotes?
- Metadata handling?

#### Step 2: Default Text Treatment

There are a few primary text elements we will use going forward. The paragraph is a common one. Also just having text handled for other uses as a base will prove beneficial going forward. 

Let’s add some CSS for our text.

<p class="file-name">style.css</p>
```css
* {
  font-size: 16px;
  line-height: 16px;
  font-weight: 400px;
  color: #000;
  font-family: XXX; 
}

p {
  font-size: 1.0rem;
}
```

The asterisk selector means the rules in there will apply to the entire site. Since CSS uses a top-down hierarchy for rules, using the asterisk as a means for communicating default rules can be handy. But remember that you will not want redundant CSS in your site, so be careful about how much you put in there and how you are using this selector. 

I also want to point out that our Skeleton framework does a LOT of what we are doing here so be careful that we aren’t being redundant (which we are - but I am showing you this as an example). 

#### Step 3: Default Headers Treatment

The `<h1>` - `<h6>` elements are extraordinarily useful from a SEO and UI perspective. However, controlling their emphasis and usage is a big part of a template. When using your headers elements you can control how pages display and present information in a hierarchical fashion. 

<p class="file-name">style.css</p>
```css
h1, h2, h3, h4, h5, h6 {
  font-weight: 600;
}
h1 {
  font-size: 3.0rem;
}
h2 {
  font-size: 2.4rem;
}
h3 {
  font-size: 2.2rem;
}
h4 {
  font-size: 1.8rem;
}
h5 {
  font-size: 1.4rem;
}
h6 {
  font-size: 1.2rem;
}
```

Because we used the asterisk selector to set a default font size, all of the ‘rem’s are relative to that size. Instead of setting a default size to these in pixels, we can use ‘rem’ to create a formulaic approach. This is useful for responsive design because we can change just the pixel size of a font at the top level of a CSS rule and all of the other text will adjust accordingly. 

#### Step 4: Utility Classes

The concept of a utility class is that you will need to use classes in certain situations that are more based on layout and functionality more than visual standards. I am going to include two here, though there probably are plenty of other ones you may use in your coding process. The two I use are good for responsive design, common usage, and javascript integration and functionality.

The first is a clear: both class which allows you to easily apply the clear both property to a layout without inlining styling or mucking up other CSS rules. 

The second is a hide class. The traditional `display: none` css rule is not actually the best way to hide something and has implications from an accessibility standpoint. We are going to use [this csstricks.com solution for an alternative to display:none.](https://css-tricks.com/places-its-tempting-to-use-display-none-but-dont/)


<p class="file-name">style.css</p>
```css
.clear { clear:both; }

.hide {
  position: absolute !important;
  top: -9999px !important;
  left: -9999px !important;
}
```

#### Step 5: Other Common Elements and Classes

So without having a specific design, what else could there be? Well the answer is not much at all. And additionally, there isn’t much we would need outside of some layout functionality adjustments either. When using a framework you have a lot of your styling and layout done for you. I am going to add a couple of small things here, but remember that you will want to make sure you are using as little CSS as possible in your site. 

<p class="file-name">style.css</p>
```css
.thumbnail-image {
  margin: 10px;
  padding: 5px;
  border: 1px solid #000;
}

.featured-text {
  font-size: 1.2rem;
  font-weight: 600;
  text-transform: uppercase;
}
```
*What other css styles would you put in here that I may have forgot?*

## <a name="javascript-and-adding-functionality">JavaScript and Adding Functionality</a>

As we discussed in a previous chapter, JavaScript is the “fun” language when it comes to web development. Of course this is a vast over simplification of the abilities of JavaScript. WordPress uses JavaScript for a bunch of different functions and using it to do what it is best at is one of the easiest ways to build on top of the WordPress framework. 

However, there are numerous considerations when you are working with a CMS and JavaScript. First off, you will want to consider the size of JavaScript files and how they could slow down your site. Second, you will want to make sure you are not adding potential errors or security issues to your site by adding additional JavaScript functionality. Third, you will have to make sure that there is not a conflict across the multiple JavaScript components that are scattered throughout the CMSs build. 

*Can you think of another issue with adding JavaScript?*

### The wp-includes Folder 

With WordPress there are additional, specific, concerns. Remember the wp-includes folder we discussed in earlier chapters? Well, we don’t want to mess with the contents of it, but let’s discuss how we can use it to our advantage (or how we might want to ignore its contents to our advantage). The wp-includes folder contains many files that WordPress uses (or may use) to perform specific behavior. Several of the files in this folder are JavaScript files (since JavaScript helps with how content behaves and displays). Some of the important components stored in this folder include jQuery, tinyMCE (a plugin for text editing in browser), and JSON support. There are also dozens of other JavaScript files which all do different and important things. 

### <a name="wordpress-dynamic-file-loading">WordPress Dynamic File Loading</a>

#### Tutorial: Linking to JavaScript and CSS Files Correctly in WordPress

WordPress uses a dynamic approach to linking to JavaScript files. Instead of linking to a js file in the header so that it loads on every page regardless of whether the code is being used, WordPress considers the context with which a JavaScript function is loaded to determine whether the dependent files need to be loaded. 

As a side note, we are going to link to JavaScript files that we are going to use in the next tutorial. 

The entirety of this tutorial is to load JavaScript files from our functions.php file using a custom WordPress function. 

We will use [wp_enqueue_script](https://codex.wordpress.org/Function_Reference/wp_enqueue_script) and [wp_enqueue_style](https://codex.wordpress.org/Function_Reference/wp_enqueue_style) in this tutorial. 

First, let’s download the dependent js files we will need for the next tutorial. For our slider we will use [bxslider, which is a responsive jQuery plugin](http://bxslider.com/). We could use pretty much any JavaScript library for this tutorial and the code would be the same with the exception of the file name. 

I don’t advocate for or against bxSlider, but the syntax is simple enough that I believe a novice programmer can implement this product. 

##### Step 1: Download Dependent Files

    Download the dependent bxSlider files (bxSlider.js and bxSlider.css)

##### Step 2: Move the Dependent Files into the Correct Folder

We already have a folder for our CSS, but we want to make sure we stay organized as much as possible in our theme so we should do the same thing for our JavaScript files. We are going to create a js folder where we will store any of our JavaScript files in the future. 

    Create a ‘js’ folder in your theme’s directory


    Copy bxslider.js into the ‘js’ sub-folder
    

    Copy bxslider.css into the ‘css’ sub-folder

##### Step 3: Enqueue the Files Using WordPress Functions

Now that we have the files in our theme folder, we should enqueue them properly. When I say “properly,” I mean in the manner that WordPress prefers. There is ultimately no difference from a performance standpoint when you link to the files in the header. However, WordPress has a built in mechanism for handling dependent files via the functions.php file. The purpose of doing it this way is to ensure that there are no duplicative files loading, such as multiple jQuery files - which is known to happen when adding plugins or different functionality. Additionally, WordPress handles the order of loading the enqueued files for you so that you don’t have to worry about a dependent file being loaded in the wrong place. Of course this is never perfect and will have to be monitored through production.

Let’s go into our functions.php file and add the enqueuing. First we will do our CSS files. 

<p class="file-name">functions.php</p>
```php
/*------------- Enqueue CSS Files-------------- */

function bxslider_css() {
    wp_enqueue_style(
        'bxslider-css',
        get_template_directory_uri() . '/css/bxslider.css'
    );
}
add_action('wp_enqueue_scripts', 'bxslider_css');
```

Notice how much like our other functions.php code this is? Let’s add our javascript files now. [wp_enqueue_scripts](https://codex.wordpress.org/Function_Reference/wp_enqueue_script)

<p class="file-name">functions.php</p>
```php
/*------------- Enqueue js Files-------------- */
function bxslider_js() {
    wp_enqueue_script(
        'bxslider-js',
        get_stylesheet_directory_uri() . '/js/bxslider.js',
        array( 'jquery' )
    );
}

add_action( 'wp_enqueue_scripts', 'bxslider_js' );
```

One major thing to note here is that we are adding an array at the end with `jquery` in it. This is because we want to use jQuery as a dependency for our bxslider plugin. This is WordPress’ way of handling this simply. 

##### Step 4: Save and Upload

Make sure to save and upload both the functions.php file AND the bxslider files and folders you added. 

After you save and upload, make sure you check to see if the files are loading correctly via the “Network” tab in Chrome’s developer tools. 

##### Step 5: Add the Rest of Our Dependent CSS Files to the Enqueue

We are already loading the skeleton and normalize css files to our site in the head, but let’s remove them from there and enqueue them in the same way we enqueued the bxSlider css files. 

<p class="file-name">functions.php</p>
```php
/*------------- Enqueue CSS Files-------------- */

function bxslider_css() {
    wp_enqueue_style(
        'bxslider-css',
        get_template_directory_uri() . '/css/bxslider.css'
    );
}
add_action('wp_enqueue_scripts', 'bxslider_css');

function normalize_css() {
    wp_enqueue_style(
        'normalize-css',
        get_template_directory_uri() . '/css/normalize.css'
    );
}
add_action('wp_enqueue_scripts', normalize_css);

function skeleton_css() {
    wp_enqueue_style(
        'skeleton-css',
        get_template_directory_uri() . '/css/skeleton.css'
    );
}
add_action('wp_enqueue_scripts', skeleton_css);
```

##### Step 6: Save and Upload

Make sure nothing broke and that the files load correctly.
