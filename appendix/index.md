---
layout: page
title: Appendix
---
<p class="message">
The Appendix contains reference materials for the lessons.
</p>

### <a href="/appendix/links-resources/">Links & Resources</a>
#### <a href="/appendix/links-resources/#links">Links</a>

Contains relevant links for the course.

#### <a href="/appendix/links-resources/#resources">Resources</a>

Contains interesting resources that may be helpful for the course and beyond.

#### <a href="/appendix/links-resources/#articles">Articles</a>

Contains interesting articles that may be helpful for the course and beyond.

### PHP Lessons

A basic introduction to PHP and very basic programming principles which will help with WordPress and to advance the understanding of content management systems from a back-end perspective.

* [PHP Lesson 1: Introduction to PHP](#php-lesson-1)
* [PHP Lesson 2: Basic Building Blocks](#php-lesson-2)
* [PHP Lesson 3: Conditional Logic & Functions](#php-lesson-3)
* [PHP Lesson 4: Simple Contact Form](#php-lesson-4)
* [PHP Lesson 5: Putting it All Together](#php-lesson-5)
* [PHP Lesson 6: Database Integration and PHP](#php-lesson-6)
* [PHP Lesson 7: Object Oriented Programming](#php-lesson-7)
* [PHP Lesson 8: Tying JavaScript and PHP Programming together](#php-lesson-8)

## PHP Lesson 1: Introduction to PHP

### Basic Concepts:

If you are feeling stuck from my lectures, I recommend trying the Lynda PHP training, which I feel is a good supplement to my lectures. It may be useful to you to have two different perspectives to learning the basics of PHP. In fact, I suggest you have dozens of resources that you use to improve your coding ability. My method of teaching is to teach through example, but if your learning style is through memorization or watching others - then you may want to supplement my lectures. 

PHP means Hypertext Preprocessor - which should give you some guidance as to how PHP works. PHP was originally designed to be embedded in the HTML of a webpage, and that is how it is still often used to this day. So any code between the `<?php` `?>` tags is "preprocessed" and then parsed by the browser with the HTML. PHP can be included alongside the HTML or can be contained in separate files and "included" in the HTML code. 

The execution that a PHP file on the server is different than that of an HTML file. When an HTML file is parsed, the browser requests an HTML file, reads/parses the exact information that the coder put into the HTML file and delivers that to the user. However, when a PHP-driven site is visited, a different series of events occurs.

<p class="message">As a note, save these files to lesson1.php for submission in the WIE course</p>

### How a PHP Request Works

First, the browser sends a request to the web server. The web server then hands the request to the PHP engine, which is embedded in the server. The PHP engine processes the code that was queried and may query a database before building the page. The server sends the completed page back to the browser to display as a web page for the user.

PHP is a server side language, which means the files work and stay on the server. The user sees an HTML output of from the server, but is not served up the PHP functionality, just the output of the PHP functionality.  Because of this, you can inject logic into your php files to allow for versions of pages to be served to users depending on their particular queries or other information. 

#### Security
I will briefly mention that PHP is only as secure as the user programs it to be. Keeping up to date with the latest version and using proven safe coding practices are the easiest way to make sure you are programming in a secure manner. This advice applies to literally every language, but is something to take more seriously with any server side programming language as private information may be at stake.

### Quick rules:

For a file to be parsed as a PHP file, the file must have the .php extension (e.g., index.php)

You must enclose PHP code in the `<?php` `?>` tags. Having errant php tags will cause errors. 

When you are programming PHP, remember that it is parsed in the same way as HTML, from top to bottom. It is for this reason that you must make sure that your included files also follow this rule. For instance, if you have one index.php file that has some PHP code AND some includes to other PHP files, you must expect that the entire page will be parsed from top to bottom. That means that any included file will be parsed in its entirety before the server moves onto the next line of code within that primary file. 

Of course you can have several php code blocks on a page, but you can never have NESTED php tags. This is key to remember when including external php files. 

### Elements:

I am aware that many of you already have experience and knowledge of many of the terms and concepts in this chapter so I will keep the discussion of them concise.

Let's cover some of the vocabulary for programming PHP. It won't be extraordinarily useful to memorize terms, but becoming familiar with the terminology will help you be comfortable speaking the language of PHP (and any other programming languages for that matter). Furthermore, I find that talking through code as if you were reading it is the best way to understand (and to write) the code. You will hear me talk through the code in examples as we go forward.

#### Variables
From the Dictionary:

Variable: a data item that may take on more than one value during the runtime of a program.

Variables act as placeholders for unknown or changing values. Think of a variable as a common name for a specific value. 

For example, if the variable was "the date," then the value of this variable would change depending on what day it was. The name "date" stays the same, but the value associated with it may be unknown or change. 

```php
<?php 
$friday = "Friday"; //Variable assigned a value of a string

$todaysDate = date("Y.m.d"); //Variable assigned a value of a function

$friday = "Monday"; //Same variable defined above given a different value
?>
```

Variables begin with a `$` in PHP and no spaces or punctuation are allowed in the name of a variable. The value assigned to a variable in PHP depends on the circumstances of the programmer's use of that variable. The format for a variable will often look like this: `$variable = value`; (note the semicolon ending the statement). 

#### Strings
A string is merely the name given to a sequence of simple objects. In PHP, text is often referred to as a string. Of all of the types, strings are often the most static but can be modified in many ways using functions. 

```php 
<?php 

$stringTest = "I am assigning this variable the value of this string, which everything inside of this sentence would be considered in PHP."; // This sentence is a string

$stringTest2 = "string"; // A string doesn't have to be a whole sentence, just an simple objects

$stringTest3 = "a 1 ewj ..." // In Fact, a string can be anything as long as it is the type 'string'

?>
```

#### Arrays

Arrays allow the user to store multiple values in a special kind of variable called an array. It may be helpful to think of an array as a list. Let's think about it as a list of animals as we go forward  (dog, frog, elephant, cat, wolf, sheep). 

```php
<?php

$animals = array(
  "dog",      //key is 0
  "frog",     //key is 1
  "elephant", //key is 2
  "cat",      //key is 3
  "wolf",     //key is 4
  "sheep"     //key is 5
);

?>
```


Each item in an array is given a **key** (a.k.a. 'index'). A key (or index) in this case is the number in which the item appears within the array starting with `0`. These types of arrays are called *index arrays*. We will cover the key/value relationship more in the future. 

[php.net - Arrays](http://php.net/manual/en/language.types.array.php)

##### Associative Arrays
An associative array is a different type of array where the items in the array are given names instead of numbers.

##### Multidimensional arrays: 
Multidimensional Arrays are arrays within arrays. Feel free to get into that as much as you'd like, just know that you can embed arrays inside of arrays. 

#### Superglobals

PHP also has certain pre-existing arrays built-in called superglobals. PHP has a huge library of pre-existing functionality and values you can (and will) reference. There are a limited number of superglobals though. We will reference superglobals intermittently throughout the assignments. 

[php.net - Superglobals](http://php.net/manual/en/language.variables.superglobals.php)

#### Booleans

Booleans refer to any version of true or false (on or off/ I or O/ 1 or 0). In PHP, the boolean values are not put in quotation marks. If you put quotation marks around a boolean value, then it is a string. 

```php
<?php

$areWeHavingFun = true //boolean value is true
$areWeReally    = 'false' //not a boolean, this is a string

?>
```
[php.net - Booleans](http://php.net/manual/en/language.types.boolean.php)

Booleans are amazingly useful in a lot of programming situations. We will explore them repeatedly as we go forward. 

#### NULL: 

The "null" *value* acts like the boolean value, but represents a variable with no value. A variable will be set to the value `null` if it is left blank or is set to `null` manually.

 ```php
<?php

$var1 = $var2;  // var1 is a null value because we haven't set the value of var2

$var1 = 'null'; //var1 is no longer null because we have assigned it the value of a string 'null'

$var1 = NULL;   // var1 is again null, but is so because we have set it to be null.

?>
```
[php.net - NULL](http://php.net/manual/en/language.types.null.php)

#### Constants

A constant is an identifier (name) for a simple value. As the name suggests, that value cannot change during the execution of the script. A constant is case-sensitive by default. By convention, constant identifiers are always uppercase. You use constants to set up items in your PHP code that will not change. 

```php
<?php
define('FAVORITE_ANIMAL', 'Dogs');

//Now our favorite animal will always be 'Dogs'... always.
?>
```

[php.net - Constants](http://php.net/manual/en/language.constants.php)

#### Numbers

##### Integers

Whole numbers are referred to as 'integers' in PHP.

##### Floating Point number

Numbers that contain decimal points are referred to as floating point numbers. As you can imagine, a value can switch from being an integer to being a floating point number is some of the basic PHP math calculations are used. 

#### Conditional Statements: 
Conditional statements allow you to display different outputs according to different circumstances. Conditional statements are essentially logical statements which create an output from an input. 

##### If Statements
The "if" statement is the most common conditional statement. Something will occur "IF" a circumstance is met. This is based off of a boolean value of truthiness or falsehood. 

```php
<?php

if ($var1 = $var2) {
  echo "These variables are the same";
}
?>
```


[php.net - If Statements](http://php.net/manual/en/control-structures.if.php)

##### Else Statements
An "else" statement is a gap filler for an if statement and is coupled with an if statement. The logical statement containing both an if and else statement could look like this: IF the sky is blue, then it is sunny. ELSE, it is cloudy.

```php
<?php

if ($sky = "blue") {
  echo "Sunny";
} else {
	echo "Cloudy";
}
?>
```

[php.net - Else Statements](http://php.net/manual/en/control-structures.else.php)

There is also the else if statement which allows you to compound if statements. More on that later. 

##### Loops
Loops are used to perform repetitive tasks over and over again until a stopping condition is met. The "while" loop is the most common type of loop and the one we will look at the most. 

```php
<?php 

$number = 1; //base value of our variable

while ($number <= 10) { // Will continuously loop through the contained operation until this condition is no longer true
    echo $number; // echoes the value of $number
    $number++;  // Adds 1 to the existing number
} // Ends the while statement

?>

```
[php.net - While Loops](http://php.net/manual/en/control-structures.while.php)

#### Functions:
A function is defined to perform preset tasks. PHP has an exhaustive list of its own preset functions and it is possible to write custom functions. We will periodically use functions to perform tasks for us in our code. If there is something you need done, odds are there is a PHP function that can perform the task.

[php.net - Functions](http://php.net/manual/en/language.functions.php)

#### Object
An 'object' is a sophisticated data type that can store and manipulate values. It is often made by creating a variable with a function and some room for a value (string, array, etc.). This object can then be used intermittently throughout the code.

We will use objects often without explicitly stating they are objects. Much of the programming methodology we will use in this class will be "object oriented programming (OOP). "

##### Class
A class is the code that defines an object's features and can be regarded as a blueprint for making objects (think like in CSS). As with objects, we will use classes without stating they are classes. As an exercise, try to point out what constitutes an object and what constitutes a class. 

### Basic skills:

#### Formatting

The easiest way to understand the formatting of PHP is to practice it. Slashes, semicolons, commas, periods, parentheses, and other symbols all have distinct functions in PHP. Knowing where everything goes is important to creating error free code. 

A good thing about PHP is that if you have a semicolon out of place, the whole site will break and you will know you have a problem. The bad thing about PHP is that if you aren't aware of which symbol is out of place, you could have a frustrating time trying to fix it. 

In this case, practice and attention to detail will help you understand the 'syntax' more quicker.

#### Commenting

There are three ways to add comments in PHP and each has a specific use case. Commenting is a very important part of a programmer's process. It allows you to leave notes for yourself and other programmers. Some practical uses include directions for editing, preventing certain lines of code from executing, giving credit where it is due, any waivers or warnings, and just little tidbits that you need to remember when stopping for the night. Additionally, it allows you to quickly cut out chunks of code you may need later. 

##### Single line comments

two forward slashes between the php tags.

```php
<?php 

  // this is a valid comment for single line.
	$variable = "value"; //Setting the value of this variable

  # or using the hash sign...
	$variable2 = "valuable"; # this works too

?>
```

##### Multiline comments

You may have learned how to comment like this with CSS, but it also works for multiline comments in PHP:

```php	
<?php

/* this will comment out
	for multiple lines
	until you see this */
?>
```

Of course, when you are using just HTML (or if you want to comment outside of the php), use the `<!--` commenting method `-->`

```php
<?php
/* Setting Variable */
$var1 = "variable"; // Equals Variable
?>

<!-- back into HTML so we would set comments using HTML's syntax -->
<h1>Heading One</h1>
<p>The Variable equals <?php echo $var1; /* Echo value of var1 */ ?></p>
```

(I know the switching between HTML and PHP may seem confusing, but this is how seamlessly they work together).

#### Quotation Marks

Be conscious of which single or double quotation marks you use when programming. This makes a big difference in PHP. Also, do not use quotation marks in the middle of a string - as PHP will consider this to be a break. This is a more complicated conversation for a different day.

## <a name="php-lesson-2">PHP Lesson 2: Basic Building Blocks</a>

This week we are going to work through some basics of PHP programming to produce some very, very simple results.

First, let's make sure we have XAMPP installed and running before we go. Check out this link for help installing XAMPP:
[XAMPP] (https://www.apachefriends.org/index.html)

If you prefer using MAMP or WAMP then feel free to do so but I will not be able to support those applications if they are not working correctly. 

If you are unable to install XAMPP and still need help, feel free to email me and I will be glad to help.

#### Step 1: Start Up XAMPP

Now the first thing we are going to do before we go any further is to create a blank .php document. It is important that we save all of the files in the correct XAMPP folder so that when we attempt to view these files in our test environment we know they will work.

#### Step 2: Navigate to our XAMPP Directory

#### Step 3: Create a Blank HTML Document

The first step will be to create a blank HTML document. The content in the HTML file will very generic. Open your preferred text editor and type the code for a blank HTML file. We will also include some content for the purposes of demonstration.

```html
<!doctype html>
<html>
<head>
  <title></title>
</head>
<body>
<h1>Blank HTML Document</h1>
<p>This is a blank html document for learning PHP. I am just writing a paragraph long enough for us to be able to demonstrate some stuff.</p>
</body>
</html>
```

Now we will save this file to the XAMPP directory as blank.html. 

#### Step 4: Open Browser and Blank HTML File
The next step will be to open up our browser and double check that the files are working correctly. 

We can type of one two things to access our running XAMPP instance (assuming you did the default configuration when you set this up). You can go to http://127.0.0.1/ or http://localhost/ to access the xampp directory. Both of these mean the same thing, but for our purposes we are going to stick with the local IP address http://127.0.0.1./

By adding the filename to the end of the URL, we will be able to see the content we just created. 

#### Step 5: Change HTML to PHP

To demonstrate seamlessly PHP and HTML work together within the apache server, let's change the extension of the .html file to .php. We can also make some changes to the content of our newly found php file so that it makes more sense. 

What you should be learning now and will be reminded of repeatedly is that PHP and HTML work together without any problems. As long as the parser (in this case the Apache server) knows what is PHP and what is HTML, it will be able to send the correct code over the HTTP request. In this case, everything is HTML, so the server knows what to do with the file, even if the extension is .php. 

#### Step 6: Copy the File as Lesson2.php 

Let's first copy this file as "lesson2.php" so that we retain our blank file for future lessons.

#### Step 7: FINALLY Start Writing PHP

To begin our PHP programming careers, we are going to use the most tired example of all. Put this into our Lesson2.php file.

<p class="file-name">lesson2.php</p>
```php
<!doctype html>
<html>
<head>
  <title></title>
</head>
<body>
<h1>Lesson 2</h1>
<?php 
echo "Foo"; //echoes "Foo"
?> 
<?php 
echo "Bar";  //echoes "Bar"
?>
</body>
</html>
```
Right now we are using the **echo** function. This allows us to print text into the HTML file. The echo function is one of the most useful functions for a programmer and is universal to almost all programming languages. 

Note the structure here of the code we just typed. The PHP tag opens the process and then the function "echo" directs the server to parse the words you put in the following quotation marks. This syntax is defined in PHP. 

Note also that if you mess up the syntax -- remove a quotation mark-- then PHP will be quick to give you an error. Feel free to break the code so that you get accustomed to the automatic error handling in PHP. 

As a side note, comments (again, I know) are important to use because you, as programmers, should start using them to make notes in your code. It is the best practice and will be a useful tool for the remainder of your coding life. 

We are going to cover more about strings next. We have already "learned" about strings and we have already typed strings in this lesson. As a reminder, a string is merely the name given to a sequence of characters.

The portion of the previous echo command that was a string was the portion between the quotation marks. You use quotes to surround a string. Let's type out a sentence as a string.

<p class="file-name">lesson2.php</p>
```php
<?php echo "Web Interactivity and Engagement is the most fun"; ?>
```

The sentence here is what we call a string. This may not seem mind blowing (which is probably isn't), but we are going to throw another step into string construction with a concept known as concatenation which basically means we conjoin whatever items we are processing. This is a very useful technique for combining strings.

<p class="file-name">lesson2.php</p>
```php
<?php echo "Web Interactivity and Engagement" . "is the most fun"; ?>
```

Now since these are merging together, let's make sure that we are conscious of spacing and let's do this in a way that works better from a programmatic standpoint - using variables. 

<p class="file-name">lesson2.php</p>
```php 
<?php 

$stringTest = "Web Interactivity and Engagement" . " " . "is the most fun"; 
echo $stringTest

?>
```

This would be more useful if you had a constant and then loaded in something dynamic in the other side of the echo function. Let's set up this concept here:

<p class="file-name">lesson2.php</p>
```php 
<?php
$courseName = "Web Interactivity and Engagement";
$courseFun = " is the most fun";
$courseBad = " is the worst.";
echo $courseName . $courseFun;
?>
```

If you were loading the second part of the string dynamically, then you could change the opinion of my course based upon the user response, a conditional statement, or however you get the information into the php function.

Let's put this together so that it works as a whole webpage:

<p class="file-name">lesson2.php</p>
```php
<h2>Course Status</h2>
<p>
<?php 

$courseName = "Web Interactivity and Engagement";
$courseFun = " is the most fun"; 
$courseBad = " is the worst."; 

echo $courseName . $courseFun;

?>
</p>
```

### Basic Math using PHP

As a quick aside, let's discuss a common use case for PHP - which is math functions. Calculators generally tend to work better than PHP, so I will just touch on this briefly. 

#### Step 1: Add Math to the Lesson2.php File

<p class="file-name">lesson2.php</p>
```php
<h2>Basic Math</h2>
<p>Ten + Ten = <?php echo 10 + 10; ?></p>
<p>Ten x Ten = <?php echo 10 * 10; ?></p>
<p>Nine - Seven = <?php echo 9 - 7; ?></p>
<p>One Hundred / Six = <?php echo 100 / 6; ?></p>
```
As you can see, using the symbols above allow you to do simple math fairly easily. Using these will come up a lot more often than you might imagine. Let's extend this into something that will resemble a more common use case. 

#### Step 2: Add More Math to the Lesson2.php File

<p class="file-name">lesson2.php</p>
```php
<?php 
$var1 = 25 * 4; 
$var2 = 75 + 25;
$var3 = 14;
$var4 = ($var1 - $var3);
?>
<p>Out of Control Math: <?php echo ($var4 + $var2 - $var3 * $var1); ?></p>
```

The use of variables is more likely in a dynamically generated content situation so feel more comfortable using them in lieu of the actual numbers/strings/etc.

### Arrays

Let's review about arrays. A good resource to help get your head wrapped around Arrays is [w3school - PHP Arrays](http://www.w3schools.com/php/php_arrays.asp). 

Arrays - Allow the user to store multiple values in a special kind of variable called an array. Each item in an array is given a key/index. A key in this case is the number in which the item appears within the array starting with `0`. These types of arrays are called index arrays.

#### Step 1: Add Arrays to Lesson2.php

<p class="file-name">lesson2.php</p>
```php
<?php
$array1 = array("dogs", "hogs", "frogs", "clogs"); 
?>
```

Now what we have created here is an array with words that end with -ogs. Note that we assigned the array to a variable. This variable now holds the array as we have set it.

Let's also talk about the key/index value that we discussed earlier. In the array we created earlier, each item in the array was given an index value based on its placement in the array. Remember, the counting starts from 0 and goes up from there. So the key- value pair in the system would look like this:

<table>
<thead>
<tr>
<td>Key</td>
<td>Value</td>
</tr>
</thead>
<tbody>
<tr>
<td>0</td>
<td>"dogs"</td>
</tr>
<tr>
<td>1</td>
<td>"hogs"</td>
</tr>
<tr>
<td>2</td>
<td>"frogs"</td>
</tr>
<tr>
<td>3</td>
<td>"clogs"</td>
</tr>
</tbody>
</table>

You can test what item is located in an index space by using the code below:

<p class="file-name">lesson2.php</p>
```php
<p>
<?php 
echo $array1[0]; 
?>
</p>
```

#### Associative Arrays

Associative Arrays are a different type of array where the items in the array are given names instead of numbers. This means that instead of the first item in the array having a key of `0`, it could have a key of `"name"` or `"foo"` or `"location"`. 

You can use some information architecture to work through this in many ways, but let's pretend we want to create a price list for grocery items. 

#### Step 2: Add Associative Arrays to Lesson2.php

<p class="file-name">lesson2.php</p>
```php
<?php
$groceryArray = array(
  "milk"          => "$2.50",
  "bananas"       => "$0.39",
  "black beans"   => "$1.20",
  "sugar"         => "$6.45",
  "apple juice"   => "$2.45",
  "string cheese" => "$4.35"
);
?>
<p><?php echo $groceryArray["black beans"]; ?></p>
```

This array would be represented like this:

<table>
  <thead>
    <tr>
      <td>Key</td>
      <td>Value</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>milk</td>
      <td>$2.50</td>
    </tr>
    <tr>
      <td>bananas</td>
      <td>$0.39</td>
    </tr>
    <tr>
      <td>black beans</td>
      <td>$1.20</td>
    </tr>
    <tr>
      <td>sugar</td>
      <td>$6.45</td>
    </tr>
    <tr>
      <td>apple juice</td>
      <td>$2.45</td>
    </tr>
    <tr>
      <td>string cheese</td>
      <td>$4.35</td>
  </tr>
  </tbody>
</table>

We will revisit associative arrays later when we are creating our first little applet. 

#### Multidimensional arrays 

Multidimensional Arrays are arrays within arrays. This is a concept that is easy to understand in concept but a bit more complicated in practice. The true power behind Multidimensional Arrays is the ability to create a use complex data structures for your applications. When you have embedded data and parent/child relationships inside of your application you are able to use this data as a variable. You will always want to weigh where you are organizing your data though - in the database or in the application (hint: almost always in the database but with multidimensional arrays you have the option to do either).

[W3 Schools - Multidimensional Arrays](http://www.w3schools.com/php/php_arrays_multi.asp)


#### Step 3: Add Multidimensional Arrays to Lesson2.php

<p class="file-name">lesson2.php</p>
```php
<?php
$upcomingSale = array(
array("milk", "$2.50", "$2.00"),
array("bananas", "$0.39", "$0.33"),
array("black beans", "$1.20", "$0.99"),
array("sugar", "$6.45", "$6.35"),
array("apple juice", "$2.45", "$2.25"), 
array("string cheese", "$4.35", "$1.95")
); 
?>
<h3>Grocery Sale!</h3>
<p><?php echo $upcomingSale[0][0] . " (regular price: " . $upcomingSale[0][1] . ") is on sale for " . $upcomingSale[0][2]; ?></p>
<p><?php echo $upcomingSale[1][0] . " (regular price: " . $upcomingSale[1][1] . ") is on sale for " . $upcomingSale[1][2]; ?></p>
<p><?php echo $upcomingSale[4][0] . " (regular price: " . $upcomingSale[4][1] . ") is on sale for " . $upcomingSale[4][2]; ?></p>
```

This embedded data array allows us to map data inside of the application. 

## <a name="php-lesson-3">PHP Lesson 3: Conditional Logic & Functions</a>

During this class we are going to discuss conditional logic through two different methods: `if`/`else` statements and loops.

### If/Else statements:

To review, let's re-look at conditional logic. We are going to learn about `if` statements and else statements first. With an `if` statement, we're trying to find something that's true. If the thing we're testing is true, then we'll continue executing the section of the code. Let's do a simple `if` statement.

<p class="file-name">lesson3.php</p>
```php
<?php
$num1 = 100;

if ($num1 > 50) {
  echo "The number is larger than 50";
}
?>
```

If something is `true` then the body of the `if` statement (i.e., the code between the braces) will execute. This is convenient for situations where you want something to show up only if a condition is `true`. However, you will often want to have something execute for the instances where the item is `false`, and that's where `else` statements come into play.

<p class="file-name">lesson3.php</p>
```php
<?php
$num1 = 100;
$num2 = 200;

if ($num1 < $num2) {
  echo "The number one variable is smaller";
} else {
  echo "The number two variable is smaller or equal";
}
?>
```

To add a third dimension to this, there is also the statement `elseif` which allows you to add additional conditional statements (similar to an `if` statement) and then the `else` statement will output a result for any remaining options. Let's modify our previous conditional to include that option.

<p class="file-name">lesson3.php</p>
```php
<?php
$num1 = 100;
$num2 = 200;

if ($num1 < $num2) {
   echo "The number one variable is smaller";
  } elseif ($num1 > $num2) {
    echo "The number one variable is larger";
  } else {
    echo "They are the same number!!";
  }
?>
```

### Loops

Loops are conditional statements that perform tasks repeatedly. For instance, let's say you have a hundred blog posts. It would be a lot easier to output a repeating list of your posts instead of having to tell the PHP to output each post manually through strings and an echo command. Remember our list of sales earlier where we had to specify the key of each object? What if we could just have a loop do that for us automatically?

As you know already, WordPress's entire existence is essentially created through the PHP loop functionality. Let's type up a loop just so that we can see how it works.

[W3 Schools - Looping](http://www.w3schools.com/php/php_looping_for.asp)

#### For Loop

<p class="file-name">lesson3.php</p>
```php
<?php
for ($num = 1; $num < 100; $num = $num + 2) {
echo "<p>$num</p>";
}
?>
```

What is occurring here is a task being repeated over and over until it is satisfied. In this case, we are finding odd numbers from 1 - 99 and listing them. The syntax may appear weird, but if you think about how PHP works, each statement complements another to create a working function. Let's walk through the syntax and logic.

- We create a `for` loop to repetitively complete a task
- In this case, the task we are performing is echoing the value of `$num` in paragraph tasks
- The `for` statement first sets the value of `$num` to `1` (initial counter),
- Then asks for the truthfulness of `$num` to be less than `100` (test counter), and 
- Finally adds `2` to `$num` everytime the truthfulness is validated (increment counter).

The `for` loop will cycle through the statement until it is no longer `true`.

#### Foreach Loop

`foreach` is a different way to do a loop but with a vastly different approach from the `for` loop. It involves cycling through an array. 

<p class="file-name">lesson3.php</p>
```php
<ul>
<?php
  $dogs = array("Golden", "Dachshund", "Corgi", "Shetland Sheepdog", "Mutt");

  foreach ($dogs as $var) {
    echo "<li>$var</li>";
  }

?>
</ul>
```

The same concept of the for loop is being executed here, we are looping over a series of values so long as it remains `true` - which in this case means there are still objects in the array that haven't been looped over.

- We can create our array using the `array()` syntax or reference an already existing array
- Use the `foreach` keyword to start the loop, followed by parentheses and brackets
- Between the parentheses, we use the `($dogs as $var)` syntax to tell PHP: "For each thing in `$dogs`, assign that thing temporarily to the variable `$var`." 
- Finally, we put the code we want to execute between the curly braces. In this case, we just `echo` each element in turn wrapped in HTML syntax.

#### While Loop

The loop that is used the most and which WordPress relies is the `while` loop. It is called that because **while** statement is `true`, the loop will continue.

[W3 Schools - While Loop](http://www.w3schools.com/php/php_looping.asp)

Let's use a variation of the example included on the W3 Schools page:

<p class="file-name">lesson3.php</p>
```php
<p>
<?php
$x = 1;

while ( $x <= 10 ) {
	echo "X equals: " . $x . "<br />";
	$x++;
}

?>
</p>
```

What is happening here is this:
- We set the variable `$x` to have the value of `1`
- The `while` loop will continues to execute until the statement inside of the parenthesis are not `true`, in this case the value of `$x` is less than or equal to `10`.
- The loop then echoes the value of `$x` plus some HTML
- Then the value of `$x` is incrementally increased
- The loop starts over again until the statement is no longer `true`.

Looping is a functional tool that is included deep into the PHP language and is fundamental to its success. Many other languages have loops built in to the language but most aren't as specific or flexible as PHP. 

### Functions

Functions are defined to perform preset tasks. PHP has an exhaustive list of its own preset functions and it is even possible to write custom functions.

We have already dealt with the function `echo` which is a built in PHP function that outputs the string, variable, etc. that is being echoed. 

Let's start with the easiest to understand PHP building blocks (strings) and the functions to modify them. String functions allow you to output your string in different ways. This is the kind of function that would be useful for printing an excerpt of a string, or for printing out different versions of your string. Changing around the way data is displayed is a common and powerful tool. 

Let's start off by creating  a string and then walk through the ways we can modify it. 

<p class="file-name">lesson3.php</p>
```php
<?php
$string1 = "Web Interactivity and Engagement";
?>
```

Now lets try to add some functions to this string.

<p class="file-name">lesson3.php</p>
```php
<p>String Length: 
<?php 
$stringlength = strlen($string1); // tells us how long our string is.
print $stringlength;
?>
</p>

<p>Lowercase String: 
<?php 
$lowercase = strtolower($string1); // makes all of the letters lowercase
print $lowercase;
?>
</p>

<p>Uppercase String: 
<?php 
$uppercase = strtoupper($string1);  //makes all of the letters uppercase
print $uppercase;
?>
</p>

<p>First Letters of the String: 
<?php 
$characterlimit = substr($string1, 0, 7);  //return a piece of your string
print $characterlimit; 
?>
</p>
```

We have just used four unique functions which are included in the PHP language. They all do things that seem relatively minor, but it is important to note that when a use case arises to use these functions, you will be grateful to have them on hand. 

Note how the fourth function, the substring function, requires more input information for the function to work correctly. This is because the function is constructed (in the language itself) in such a way to require more parameters to function, while the previous uppercase and lowercasing functions are not built with extra parameters required. 

Knowing the functions that you are using is key to making sure that you are using the functions correctly. The php.net website has information about functions, so while you are learning which functions exist, you should look at the php.net site for more information about certain functions. For instance, [here is the PHP specification for the substr function](http://php.net/manual/en/function.substr.php).

Let's try another useful String function. This time we're going to pass the string directly into the function instead of worrying about the variable definition.

<p class="file-name">lesson3.php</p>
```php
<p>P in Elephant: 
<?php 
$positionP = strpos("Elephant", "p");   //finds the item in the string
print $positionP; 
?>
</p>
```

This is a string function that can allow you to locate a string or substring in another string.

Let's try it where there is no item in the string to find to see how a php function fails:

<p class="file-name">lesson3.php</p>
```php
<p>Q in Elephant: 
<?php 
$positionQ = strpos("Elephant", "q");   //finds the item in the string
print $positionQ; 
?> 
</p>
```

See how it returns nothing? That's php's way of returning a negative result.

Let's put this together with conditional logic to create something that resembles something useful.

<p class="file-name">lesson3.php</p>
```php
<p>Is there a 'P' in Elephant? 
<?php
$elephantstring = "Elephant"; //set variable value
$positionP = strpos($elephantstring, "p"); //set variable value
if ($positionP) { //test if variable value is true or false
	echo "Yes";
} else {
	echo "No";
}
?>
</p>

<p>Is there a 'Q' in Elephant? 
<?php
$positionQ = strpos($elephantstring, "q"); //set variable value
if ($positionQ) { //test if variable value is true or false
	echo "Yes";
} else {
	echo "No";
}
?>
</p>
```

Enough with strings for now. Let's create a random number generator. This is easily done with PHP because there is already a function built in to do this.

<p class="file-name">lesson3.php</p>
```php
<p>Random Number: 
<?php 
print rand(1, 1000);
?>
</p>
```

Now every time we refresh the page we get a new number. 

Let's work with an array function really quick just so we get a grasp of the diversity of types of functions.

Let's use the `array_push` function we can add items into our empty array. This allows us to keep a list of array items up to date and dynamic instead of static like we had before.

[php.net - array_push](http://php.net/manual/en/function.array-push.php)

<p class="file-name">lesson3.php</p>
```php
<?php

$dogs = array("Mixed Breed", "Labrador");?>

<p>List of Dogs (pre):<br /> <?php print_r($dogs); ?>

<?php
array_push($dogs, "Pitbull"); 
array_push($dogs, "Corgi"); 
array_push($dogs, "Shetland Sheepdog"); 
array_push($dogs, "Schnauzer"); 
array_push($dogs, "Golden Retriever");
?>

<p>List of Dogs (post):<br /> <?php print_r($dogs); ?>
```

## <a name="php-lesson-4">PHP Lesson 4: Simple Contact Form</a>

Now that we have a grasp of the core concepts behind the PHP language, let’s make a very simple application of the language. 

We are going to make a contact form. I am going to roughly use the [CSS Tricks Simple Contact Form](https://css-tricks.com/nice-and-simple-contact-form/) as a basis for our form. 

### Step One: Create the files we will need

	Create contact-form.php

	Create thank-you.php

	Create index.html

	Create style.css

Let’s place all of these files into a single folder. By pre-making the files we are going to be ready to add code as quickly as possible.

### Step Two: Setup the Form

Our index.html file will not have any PHP in it directly, but will use the HTML and HTTP form methods for passing values. Let’s set up the HTML page first and link to our style.css file. 

<p class="file-name">index.html</p>
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>PHP Lesson 4: Simple Contact Form</title>
	<link rel="stylesheet" type="text/css" href="style.css" />
	<link rel="stylesheet" type="text/css" href="/dependencies/skeleton.css">
</head>
<body>
<div class="container">
	<div class="row">
		<div class="twelve columns">
			<h1>PHP Lesson 4</h1>
			<h2>Simple Contact Form</h2>
		</div>
	</div>
</div>
</body>
</html>
```

Now that we have the basis for the simple HTML document, let’s add the form elements

<p class="file-name">index.html</p>
```html
<div class="twelve columns">
	<h1>PHP Lesson 4</h1>
	<h2>Simple Contact Form</h2>

	<form>
		<label for="Name">Name:</label>
		<input type="text" name="Name" id="Name" />
		
		<label for="Email">Email:</label>
		<input type="text" name="Email" id="Email" />
		
		<label for="Message">Message:</label><br />
		<textarea name="Message" rows="20" cols="20" id="Message"></textarea>

		<input type="submit" name="submit" value="Submit" class="submit-button" />
	</form>

</div>
```

Our form now has spaces for a name, an email, and a message. If you look at the form now, it appears to be sound - but nothing works correctly until we add an “action” or “method” into the form. 

The “method” we are going to add is “post” which is an HTTP method for sending data. The “action” we are going to add is a link to our contact-form.php file. The contact-form.php file is going to house the functionality of our form. 

<p class="file-name">index.html</p>
```html
<div class="twelve columns">
	<h1>PHP Lesson 4</h1>
	<h2>Simple Contact Form</h2>

	<form method=”post” action=”contact-form.php”>
		<label for="Name">Name:</label>
		<input type="text" name="Name" id="Name" />
		
		<label for="Email">Email:</label>
		<input type="text" name="Email" id="Email" />
		
		<label for="Message">Message:</label><br />
		<textarea name="Message" rows="20" cols="20" id="Message"></textarea>

		<input type="submit" name="submit" value="Submit" class="submit-button" />
	</form>

</div>
```

### Step Three: Setup the PHP Script

The basis of our PHP form is going to be through the [mail function](http://php.net/manual/en/function.mail.php) which is a PHP function. 

The way that this function works is by accepting some parameters inside of the parentheses after the function name. Here is the formatting for using this function:

```php
<?php
mail ( string $to , string $subject , string $message [, string $additional_headers [, string $additional_parameters ]] )
?>
```

So we know that we need to use the following parameters which we will represent as variables:

```php
$to
$subject
$message
```

We are also going to include an additional parameter so that we can include a “from” email address and the “name” from the form - though they aren’t required. 

```php
$from
$name
```

So the first thing we will do is set up the variables we need, and then add the “mail function”

<p class="file-name">contact-form.php</p>
```php
$to      = "";
$subject = "";
$name    = "";
$message = "";
$from    = "";

mail($to, $subject, $body, "From: <$from>");
```

Let’s add the sample values into the variables and then attach the output of the function into a variable. This will allow us to use the output elsewhere. 

<p class="file-name">contact-form.php</p>
```php
$to      = "your-email@your-domain.com";
$subject = "New Contact Form Submission";
$message = "MESSAGE GOES HERE";    //input from form
$from    = "FROM EMAIL GOES HERE"; //input from form
$name    = "NAME GOES HERE";       //input from form

$success = mail($to, $subject, $body, "From: <$from>");
```

Next, let’s’ build the $body variable so that it is sent in a proper way.

<p class="file-name">contact-form.php</p>
```php
$body  = "";
$body .= "Name: "    . $name    . "\n";
$body .= "Email: "   . $from    . "\n";
$body .= "Message: " . $message . "\n";
```

You may not be familiar with this syntax, but what is occurring is the $body variable is being built bit by bit from the values of the other variables through the `.=` operator. 

We will quickly add some data validation check. This will let us use a variable based system to return an error page if the data doesn’t work out how we want.

<p class="file-name">contact-form.php</p>
```php
$validationOK = true;

if (!$validationOK) {
  print "<meta http-equiv=\"refresh\" content=\"0;URL=error.html\">";
  exit;
}
```

We are almost done. The form will mostly work at this point, but we want to make sure there is an action after the form is submitted. In this case, we are going to use the `$success` variable and attach it to a conditional statement which will either:
Redirect the user to an error page, or Redirect the user to a success page with a “Thank You” message.

<p class="file-name">contact-form.php</p>
```php
if ($success){
  print "<meta http-equiv=\"refresh\" content=\"0;URL=thank-you.php\">";
}
else {
  print "<meta http-equiv=\"refresh\" content=\"0;URL=error.html\">";
}
```

You may notice that there are two “URL” parameters in our conditional statement: thank-you.php and error.html. If there is a truthful value for the `$success` variable, then the user will be served up the thank-you.php document. If there is a falsey value for the $success variable, then the user will be served with the error.html document. We haven’t made the error.html document but if we wanted to we could and then perhaps place some helper text for the user. 

The last step for the contact-form file is to add out `$_POST` superglobal variables into our various other variables. These `$_POST` superglobals will let us send data to our mail function which will let us send emails. 

<p class="file-name">contact-form.php</p>
```php
$to      = "your-email@your-domain.com";
$subject = "New Contact Form Submission";
$message = trim(stripslashes($_POST['Message']));
$from    = trim(stripslashes($_POST['Email']));
$name    = trim(stripslashes($_POST['Name']));
```

This may seem weird, but what we have done is used the following PHP functions to modify the data coming out of the “Message”, “Email”, and “Name” form elements:

[Trim](http://php.net/manual/en/function.trim.php)
[Stripslashes](http://php.net/manual/en/function.stripslashes.php)


Let’s piece together our entire contact-form.php file.

<p class="file-name">contact-form.php</p>
```php
<?php

$to      = "your-email@your-domain.com";
$subject = "New Contact Form Submission";
$message = trim(stripslashes($_POST['Message']));
$from    = trim(stripslashes($_POST['Email']));
$name    = trim(stripslashes($_POST['Name']));

$validationOK = true;

if (!$validationOK) {
  print "<meta http-equiv=\"refresh\" content=\"0;URL=error.htm\">";
  exit;
}

$body  = "";
$body .= "Name: "    . $name    . "\n";
$body .= "Email: "   . $from    . "\n";
$body .= "Message: " . $message . "\n";

$success = mail($to, $subject, $body, "From: <$from>");

if ($success){
  print "<meta http-equiv=\"refresh\" content=\"0;URL=thank-you.php\">";
} else {
  print "<meta http-equiv=\"refresh\" content=\"0;URL=error.htm\">";
}

?>
```

### Step Three: Setup the Thank You Page


We are going to copy the code from our index.html file first and then take away all of the form components. This gives us a headstart for finishing this page quickly.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>PHP Lesson 4: Simple Contact Form</title>
    <link rel="stylesheet" type="text/css" href="style.css" />
    <link rel="stylesheet" type="text/css" href="/dependencies/skeleton.css">
  </head>
  <body>
    <div class="container">
      <div class="row">
        <div class="twelve columns">
          <h1>PHP Lesson 4</h1>
          <h2>Simple Contact Form</h2>
        </div>
      </div>
    </div>
  </body>
</html>
```

Let’s add a little message and a link back to the form itself.

```html
<div class="twelve columns">
  <h1>PHP Lesson 4</h1>
  <h2>Simple Contact Form</h2>
  <h3>Thanks!</h3>
  <p>Thank you for filling out this form.</p>
  <p><a href="index.html">Return to the Form</a></p>
</div>
```

Now let’s try filling out the form to make sure it works.

### Step Three: Styling Our Form

Lastly, let’s add some styling to our form so that we have a good looking form that works. Part of the assignment will be that I expect you to add some styling of your own to make the form your own.

### Step Four: Save and Upload

Upload your files to your server, which must have PHP enabled, and then check to make sure your form works.


## <a name="php-lesson-5">PHP Lesson 5: Putting it all Together: Inputs and Outputs</a>

So we know a bit about the building blocks and we have come to use them as examples. However, learning about these building blocks in a concrete way requires application. 

The list of elements we are going to use in this tutorial is as follows:

* Variables
* Strings
* Arrays
* Functions
* Conditional Statements

You should feel comfortable with all of these going forward.

### Tutorial Concept

So let us imagine that we have a very, very basic content management system that we want to use. This content management system is so basic that it has no database connection for storing data and merely updates the values in the page (hope you don’t close it or refresh)!

However, this is a good place to start because we are going to need to build the portion of the application that works without a database before we integrate it with a database. This is a common thing to do when you are creating a prototype for an application.

In our application, we are going to imagine ourselves as a zoo. We need to keep track of our animals and might want more information about them.

### Step 1: Create The Structure for the Application

Every step of an application requires some design before any steps of coding are taken into consideration. Sometimes you may make changes to the design based on coding restrictions, but the design is key. Let’s create a sample data architecture and a front end for our application. 

#### Data Architecture/Model

* Animal
* Name
* Type
* Size
* Location
* Date of Acquisition

Looking at our data architecture, it is clear that there is an overarching value of the animal name with many other values associated with that animal name. This seems to work out for us, but how are we going to make this look?

#### Front End Structure

Let’s use one of the most basic HTML layout structures to lay this out - the table. Obviously tables are mostly useless nowadays, but their simplicity and syntactical hierarchy makes them a good example in this case. 

<p class="file-name">index.php</p>
```html
<!DOCTYPE html>
<html>
<head>
<title>Sample Zoo App</title>
</head>
<body>

<h1>Sample Zoo Application</h1>

<h2>Add an Animal</h2>
<form>
Name: <input type="text" name="name"><br />
Type: <input type="text" name="type"><br />
Size: <input type="text" name="size"><br />
Location: <input type="text" name="location"><br />
Date of Acquisition: <input type="text" name="doa"><br />
<input type="submit" name="submit" value="Submit">
</form>

<h2>Animal List</h2>
<table>
	<thead>
		<tr>
			<td>Name</td>
			<td>Type</td>
			<td>Size</td>
			<td>Location</td>
			<td>Date of Acquisition</td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Sample1</td>
			<td>Sample1</td>
			<td>Sample1</td>
			<td>Sample1</td>
			<td>01/01/0001</td>
		</tr>
		<tr>
			<td>Sample2</td>
			<td>Sample2</td>
			<td>Sample2</td>
			<td>Sample2</td>
			<td>01/01/0001</td>
		</tr>
		<tr>
			<td>Sample3</td>
			<td>Sample3</td>
			<td>Sample3</td>
			<td>Sample3</td>
			<td>01/01/0001</td>
		</tr>
	</tbody>
</table>
</body>
</html>
```

This simple HTML template should work to show you all of the data architecture as a sample. Using simple HTML we could easily envision a display of all of the animals if we hard coded it that way. In fact, there exist situations where this may be useful. But we are not talking about someone’s house pets - this is a big zoo and there are a LOT of animals - so we are going to need to build something that is dynamic.

I also want to reiterate that making the design of the data and the application makes the remaining design process a lot more simple. Make sure you are planning in detail the specifications of the project before you dive into the coding.

### Step 2: Use Baseline Data to Ensure Output

So ultimately we are going to want to generate some new entries from a form - but for now we are going to want to make sure we have our PHP code correctly set up to display some text. We have learned about multidimensional arrays briefly earlier, but let’s implement them to store our data.

<p class="file-name">index.php</p>
```php
<?php 

$animals = array(
  array("Elly", "elephant", "10", "0012", "02/07/2006"),
  array("Fred", "gorilla", "7", "0001", "03/08/2005"),
  array("Squeaky", "mouse", "2", "0008", "04/09/2004"),
  array("Sam", "cougar", "5", "0004", "05/11/2003"),
  array("Rib", "frog", "2", "0007", "06/21/2002"),
  array("Karen", "parrot", "3", "0009", "07/31/2001")
);
?>
```

### Step 3: Output the Sample Data

Now that we have some actual sample data to deal with, let’s talk about how this data exists. Back in Lesson 2 we talked about keys/indexes. As a reminder, the key refers to the placement of the item in the array. For example:

```php
echo $animals[0][1]; // echoes "elephant"
```

This is because the first array’s ([0]) second item ([1]) is the string “elephant”.

```php
echo $animals[3][4]; // echoes "05/11/2003"
```

This is because the fourth array’s (`[3]`) fifth item (`[4]`) is the string `"05/11/2003"`.

Our data model in a relational sense would look like this:

<table>
  <thead>
    <tr>
      <td>Key</td>
      <td>Name [0]</td>
      <td>Type [1]</td>
      <td>Size [2]</td>
      <td>Location [3]</td>
      <td>Date of Acquisition [4]</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Elly</td>
      <td>elephant</td>
      <td>10</td>
      <td>0012</td>
      <td>02/07/2006</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Fred</td>
      <td>gorilla</td>
      <td>7</td>
      <td>0001</td>
      <td>03/08/2005</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Squeaky</td>
      <td>mouse</td>
      <td>2</td>
      <td>0008</td>
      <td>04/09/2004</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Sam</td>
      <td>cougar</td>
      <td>5</td>
      <td>0004</td>
      <td>05/11/2003</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Rib</td>
      <td>frog</td>
      <td>2</td>
      <td>0007</td>
      <td>06/21/2002</td>
    <tr>
    <tr>
      <td>5</td>
      <td>Karen</td>
      <td>parrot</td>
      <td>3</td>
      <td>0009</td>
      <td>07/31/2001</td>
    </tr>
  </tbody>
</table>

I am spending a lot of time making sure you understand how data sits in the application because it is also how data sits in a database. **Having an understanding of data organizations allows you to map out complex applications more efficiently**. Being able to create stable and efficient applications is just as important than being able to build them at all

Now that we have a good understanding of the sample data, let’s output the sample data. Using a loop, we are able to go through and print all of the data. Think of the WordPress loop and how it works compared to how this loop works.

<p class="file-name">index.php</p>
```php
<?php

//if there is an $animals array then...
if ( $animals ) {

  $animalsVal   = 0; //set variable for iteration
  $animalsCount = count($animals);

  // we need to make sure there is a count of the items in the array so that we
  // don’t iterate over empty items in the array	
  while ( $animalsVal <=  $animalsCount ) { ?>
    <tr>
      <td>
        <?php echo $animals[$animalsVal][0]; ?>
      </td>
      <td>
        <?php echo $animals[$animalsVal][1]; ?>
      </td>
      <td>
        <?php echo $animals[$animalsVal][2]; ?>
      </td>
      <td>
        <?php echo $animals[$animalsVal][3]; ?>
      </td>
      <td>
        <?php echo $animals[$animalsVal][4]; ?>
      </td>
    </tr>

  <?php 

  //increase the value of animalVal and end while
  $animalsVal++ 

  } // end while
} // end if

?>
```

There is a lot happening here:

* We set a variable to be the value of `0`
* We are looping through the array
* We use the value of our variable inside of our array query. Since this value increases every time we loop through the array, the key that indicates which array to `echo` will ensure that the echoed array will change every time. This allows us to progress through the array one by one.
* We are also outputting the value of the array inside of a table structure. Make a note of how easily we jump from HTML to PHP without any effort. The HTML is even part of the looping PHP functionality. 

This looping of values from the array need to be put into our hardcoded table from Step One. 

<p class="file-name">index.php</p>
```php
<h2>Animal List</h2>
<table>
	<thead>
		<tr>
			<td>Name</td>
			<td>Type</td>
			<td>Size</td>
			<td>Location</td>
			<td>Date of Acquisition</td>
		</tr>
	</thead>
	<tbody>

<?php

  //if there is an $animals array then...
	if ( $animals ) {

		$animalsVal   = 0; //set variable for iteration
		$animalsCount = count($animals) - 1;

		while ( $animalsVal <=  $animalsCount ) { ?>
		<tr>
			<td>
				<?php echo $animals[$animalsVal][0]; ?>
			</td>
			<td>
				<?php echo $animals[$animalsVal][1]; ?>
			</td>
			<td>
				<?php echo $animals[$animalsVal][2]; ?>
			</td>
			<td>
				<?php echo $animals[$animalsVal][3]; ?>
			</td>
			<td>
				<?php echo $animals[$animalsVal][4]; ?>
			</td>
		</tr>

		<?php 

      //increase the value of animalVal
      $animalsVal++

		} // end while

		unset($animalsVal);

	} // end if
?>

</tbody>
</table>
```
Two important things to note that I added:

1. I subtracted 1 from the count variable value because the count function starts at 1 but the array key starts at 0 - so that's why you were probably getting an error.

2. I invoked the `unset` function on the `$animalsVal` variable so that it is not stored in memory even though we aren't using it anymore - plus this will prevent future issues. 

We now are iterating through our array one step at a time and outputting it into the table. This is a huge step in our process is our first step in creating dynamically generated web pages. 

### Step 3: Using Forms to Submit Data

Having a static list of objects is not very interesting and it can hardly be called an application. Let’s create a form that submits data to the array we have.

Remember in Lesson 2 when we used `array_push`? Well, that is going to be the basis for our form submission here.

Let’s start by looking at the form we created in Step One.

<p class="file-name">index.php</p>
```html
<form>
  Name: <input type="text" name="name"><br />
  Type: <input type="text" name="type"><br />
  Size: <input type="text" name="size"><br />
  Location: <input type="text" name="location"><br />
  Date of Acquisition: <input type="text" name="doa"><br />
  <input type="submit" name="submit" value="Submit">
</form>
```

This form doesn’t do anything because we haven’t wired it up to do anything. Forms are a very powerful part of the HTML language. It allows you to make submissions to both internal and external sources from the page. 

[Learn more about forms](http://www.w3schools.com/html/html_forms.asp)

<p class="file-name">index.php</p>
```html
<form method=”post” action=””>
Name: <input type="text" name="name" value=””><br />
Type: <input type="text" name="type" value=””><br />
Size: <input type="text" name="size" value=””><br />
Location: <input type="text" name="location" value=””><br />
Date of Acquisition: <input type="text" name="doa" value=””><br />
<input type="submit" name="submit" value="Submit">
</form>
```

In this code, we are doing three things (one of them not completely defined yet):

- We are giving it the method `post` which defines what happens when the form is submitted
- We are giving the form an action which tells the form how to behave. Our action is currently blank but we are going to define that action with PHP. 
- We are giving the inputs an empty value which will be used for the form submission.

The value parameter is used to pass a value to the `post` event. Please note that none of this is PHP but rather HTML. The next thing we will do is to create some blank variable placeholders for our PHP form submission.

<p class="file-name">index.php</p>
```php
<?php
// Define variables and set empty values
$animalName     = "";
$animalType     = "";
$animalSize     = "";
$animalLocation = "";
$animalDoa      = "";
?>
```

These variables are going to hold the information that is submitted through the form. Let’s place the variables dynamically into the inputs.

```php
<form method="post" action="">
  Name:                <input type="text" name="name" value="<?php echo $animalName;?>"><br />
  Type:                <input type="text" name="type" value="<?php echo $animalType;?>"><br />
  Size:                <input type="text" name="size" value="<?php echo $animalSize;?>"><br />
  Location:            <input type="text" name="location" value="<?php echo $animalLocation;?>"><br />
  Date of Acquisition: <input type="text" name="doa" value="<?php echo $animalDoa;?>"><br />
  <input type="submit" name="submit" value="Submit">
</form>
```

We are taking the variable and inputting it into value. When the variable changes, so will the value.

A major part of using forms in PHP involves the use of one of PHP’s most powerful and attractive features: `Superglobals`. 

Superglobals get their name because their scope is universal. They are built in variables that are used for receiving and sending data, often over HTTP. Even if that last sentence was gobbledegook for you, know that they are very powerful variables you can use to simplify the effort needed for sending and receiving data. The syntax for a superglobal is `$_POST` - which is to say it starts with a `$_` and then adds in the name of the global variable. 

We are going to use `$_POST` and `$_SERVER`. You can [learn more about superglobals at php.net](http://php.net/manual/en/language.variables.superglobals.php)

Let’s add some of these super powered variables into our code. The `$_POST` superglobal pushes the value it receives. The `$_SERVER` superglobal has many options it can accept so that it does different things. If you want to look into this in greater detail, I recommend you check out the pages for the appropriate superglobals:

* [$_POST](http://php.net/manual/en/reserved.variables.post.php)
* [$_SERVER](http://php.net/manual/en/reserved.variables.server.php)

<p class="file-name">index.php</p>
```php
<?php

// define variables and set to empty values
$animalName     = "";
$animalType     = "";
$animalSize     = "";
$animalLocation = "";
$animalDoa      = "";

// redefine variables if the form is submitted using the $_POST superglobal
$animalName     = animalValidation($_POST["name"]);
$animalType     = animalValidation($_POST["type"]);
$animalSize     = animalValidation($_POST["size"]);
$animalLocation = animalValidation($_POST["location"]);
$animalDoa      = animalValidation($_POST["doa"]);
?>
```


By adding the `$_POST` superglobal, we allow the variable to be redefined by the form field of the specified name.

Let’s set up our form so that it is functioning as a PHP HTTP form.

<p class="file-name">index.php</p>
```html
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">
	Name: <input type="text" name="name" value="<?php echo $animalName;?>"><br />
	Type: <input type="text" name="type" value="<?php echo $animalType;?>"><br />
	Size: <input type="text" name="size" value="<?php echo $animalSize;?>"><br />
	Location: <input type="text" name="location" value="<?php echo $animalLocation;?>"><br />
	Date of Acquisition: <input type="text" name="doa" value="<?php echo $animalDoa;?>"><br />
	<input type="submit" name="submit" value="Submit">
</form>
```

The superglobal we added is `$_SERVER` with the option of `'PHP_SELF'` which tells the `$_SERVER` superglobal that the server is existing in the same window frame. Which works for us since we want to update the page like a single page app. The weird thing you may not understand is the `htmlspecialchars` function we are putting in front of the superglobal. This is a PHP function that converts any special characters to HTML. 

This is the first step of preventing unwanted behavior from happening that we will do in this little application. Let’s add some more data validation and conditional steps into the application so that we aren’t letting the user mess anything up. 

<p class="file-name">index.php</p>
```php
<?php
// define variables and set to empty values
$animalName     = "";
$animalType     = "";
$animalSize     = "";
$animalLocation = "";
$animalDoa      = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  $animalName     = animalValidation($_POST["name"]);
  $animalType     = animalValidation($_POST["type"]);
  $animalSize     = animalValidation($_POST["size"]);
  $animalLocation = animalValidation($_POST["location"]);
  $animalDoa      = animalValidation($_POST["doa"]);
}

function animalValidation($data) {
   $data = trim($data);
   $data = stripslashes($data);
   $data = htmlspecialchars($data);
   return $data;
}
?>

<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">
  Name: <input type="text" name="name" value="<?php echo $animalName;?>"><br />
  Type: <input type="text" name="type" value="<?php echo $animalType;?>"><br />
  Size: <input type="text" name="size" value="<?php echo $animalSize;?>"><br />
  Location: <input type="text" name="location" value="<?php echo $animalLocation;?>"><br />
  Date of Acquisition: <input type="text" name="doa" value="<?php echo $animalDoa;?>"><br />
  <input type="submit" name="submit" value="Submit">
</form>
```

Here’s what we added:

* A conditional statement using the `$_SERVER` superglobal to ensure that a POST event occurs before it changes the variables
* A custom function (oh yeah, did you know you can define your own functions in PHP too?) that uses three built in PHP functions to output the input (algorithm). Do you see how the use of the `$data` variable works?
* Then we applied that custom function into the `$_POST` superglobal behavior we added earlier. 
* Lastly, we need to add the `array_push` behavior so that there is a new item added into the array.

<p class="file-name">index.php</p>
```php
<?php
array_push(
  $animals,
  array($animalName, $animalType, $animalSize, $animalLocation, $animalDoa)
);
?>
```

Let’s put our whole PHP functionality thing together:

<p class="file-name">index.php</p>
```php
<?php
$animalName     = "";
$animalType     = "";
$animalSize     = "";
$animalLocation = "";
$animalDoa      = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  $animalName     = animalValidation($_POST["name"]);
  $animalType     = animalValidation($_POST["type"]);
  $animalSize     = animalValidation($_POST["size"]);
  $animalLocation = animalValidation($_POST["location"]);
  $animalDoa      = animalValidation($_POST["doa"]);
}
function animalValidation($data) {
   $data = trim($data);
   $data = stripslashes($data);
   $data = htmlspecialchars($data);
   return $data;
}
?>

<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">
	Name: <input type="text" name="name" value="<?php echo $animalName;?>"><br />
	Type: <input type="text" name="type" value="<?php echo $animalType;?>"><br />
	Size: <input type="text" name="size" value="<?php echo $animalSize;?>"><br />
	Location: <input type="text" name="location" value="<?php echo $animalLocation;?>"><br />
	Date of Acquisition: <input type="text" name="doa" value="<?php echo $animalDoa;?>"><br />
	<input type="submit" name="submit" value="Submit">
</form>

<?php
	array_push(
    $animals,
		array($animalName, $animalType, $animalSize, $animalLocation, $animalDoa)
	);
?>
```

### Step 4: Put Everything Together and Try it Out

Let’s add the form function and the table function as start adding some new animals!

<p class="file-name">index.php</p>
```php
<?php
$animalName     = "";
$animalType     = "";
$animalSize     = "";
$animalLocation = "";
$animalDoa      = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  $animalName     = animalValidation($_POST["name"]);
  $animalType     = animalValidation($_POST["type"]);
  $animalSize     = animalValidation($_POST["size"]);
  $animalLocation = animalValidation($_POST["location"]);
  $animalDoa      = animalValidation($_POST["doa"]);
}
function animalValidation($data) {
   $data = trim($data);
   $data = stripslashes($data);
   $data = htmlspecialchars($data);
   return $data;
}
?>

<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">
	Name: <input type="text" name="name" value="<?php echo $animalName;?>"><br />
	Type: <input type="text" name="type" value="<?php echo $animalType;?>"><br />
	Size: <input type="text" name="size" value="<?php echo $animalSize;?>"><br />
	Location: <input type="text" name="location" value="<?php echo $animalLocation;?>"><br />
	Date of Acquisition: <input type="text" name="doa" value="<?php echo $animalDoa;?>"><br />
	<input type="submit" name="submit" value="Submit">
</form>

<?php
  array_push(
    $animals,
    array($animalName, $animalType, $animalSize, $animalLocation, $animalDoa)
  );
?>

<h3>Animal List</h3>
<table>
	<thead>
		<tr>
			<td>Name</td>
			<td>Type</td>
			<td>Size</td>
			<td>Location</td>
			<td>Date of Acquisition</td>
		</tr>
	</thead>
	<tbody>

    <?php
    if ( $animals ) { 
      $animalsCount = count($animals) - 1;
      $animalsVal   = 0;

      while ( $animalsVal <=  $animalsCount ) { ?>
      <tr>
        <td>
          <?php echo $animals[$animalsVal][0]; ?>
        </td>
        <td>
          <?php echo $animals[$animalsVal][1]; ?>
        </td>
        <td>
          <?php echo $animals[$animalsVal][2]; ?>
        </td>
        <td>
          <?php echo $animals[$animalsVal][3]; ?>
        </td>
        <td>
          <?php echo $animals[$animalsVal][4]; ?>
        </td>
      </tr>

      <?php 

      $animalsVal++; 
      } // end while

      unset($animalsVal);
    } // end if

    ?>
  </tbody>
</table>
```

### Step Five: Disappointment

Have you noticed that the form does not submit more than once successfully? Why is that?

Well, the post request that we are using sends data to the array, but if you attempt to send it again, it will just overwrite that portion of the array with the new information. The way to fix this is to do some database integration. Which leads us to the next lesson.

<!--
## <a name="php-lesson-6">PHP Lesson 6: Database Integration and PHP</a>
## <a name="php-lesson-7">PHP Lesson 7: Object Oriented Programming</a>
## <a name="php-lesson-8">PHP Lesson 8: Creating a CMS - coming soon</a>
-->
