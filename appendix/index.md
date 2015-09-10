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
* [PHP Lesson 3: Arrays and Functions](#php-lesson-3)
* [PHP Lesson 4: Conditional Logic](#php-lesson-4)
* [PHP Lesson 5: Creating a Contact Form](#php-lesson-5)
* [PHP Lesson 6: Recapping What We’ve Learned](#php-lesson-6)
* [PHP Lesson 7: Object Oriented Programming](#php-lesson-7)
* [PHP Lesson 8: Creating a CMS - coming soon](#php-lesson-8)

## PHP Lesson 1: Introduction to PHP

### Basic Concepts:

If you are feeling stuck from my lectures, I recommend trying the Lynda PHP training, which I feel is a good supplement to my lectures. It may be useful to you to have two different perspectives to learning the basics of PHP. In fact, I suggest you have dozens of resources that you use to improve your coding ability. My method of teaching is to teach through example, but if your learning style is through memorization or watching others - then you may want to supplement my lectures. 

PHP means Hypertext Preprocessor - which should give you some guidance as to how PHP works. PHP was originally designed to be embedded in the HTML of a webpage, and that is how it is still often used to this day. So any code between the <?php ?> tags is “preprocessed” and then parsed by the browser with the HTML. PHP can be included alongside the HTML or can be contained in separate files and “included” in the HTML code. 

The execution that a PHP file on the server is different than that of an HTML file. When an HTML file is parsed, the browser requests an HTML file, reads/parses the exact information that the coder put into the HTML file and delivers that to the user. However, when a PHP-driven site is visited, a different series of events occurs.



### How a PHP Request Works

First, the browser sends a request to the web server. The web server then hands the request to the PHP engine, which is embedded in the server. The PHP engine processes the code that was queried and may query a database before building the page. The server sends the completed page back to the browser to display as a web page for the user.

PHP is a server side language, which means the files work and stay on the server. The user sees an HTML output of from the server, but is not served up the PHP functionality, just the output of the PHP functionality.  Because of this, you can inject logic into your php files to allow for versions of pages to be served to users depending on their particular queries or other information. 

#### Security
I will briefly mention that PHP is only as secure as the user programs it to be. Keeping up to date with the latest version and using proven safe coding practices are the easiest way to make sure you are programming in a secure manner. This advice applies to literally every language, but is something to take more seriously with any server side programming language as private information may be at stake.

### Quick rules:

For a file to be parsed as a PHP file, the file must have the .php extension (e.g., index.php)

You must enclose PHP code in the <?php ?> tags. Having errant php tags will cause errors. 

When you are programming PHP, remember that it is parsed in the same way as HTML, from top to bottom. It is for this reason that you must make sure that your included files also follow this rule. For instance, if you have one index.php file that has some PHP code AND some includes to other PHP files, you must expect that the entire page will be parsed from top to bottom. That means that any included file will be parsed in its entirety before the server moves onto the next line of code within that primary file. 

Of course you can have several php code blocks on a page, but you can never have NESTED php tags. This is key to remember when including external php files. 

### Elements:

I am aware that many of you already have experience and knowledge of many of the terms and concepts in this chapter so I will keep the discussion of them concise.

Let’s cover some of the vocabulary for programming PHP. It won’t be extraordinarily useful to memorize terms, but becoming familiar with the terminology will help you be comfortable speaking the language of PHP (and any other programming languages for that matter). Furthermore, I find that talking through code as if you were reading it is the best way to understand (and to write) the code. You will hear me talk through the code in examples as we go forward.

#### Variables
From the Dictionary:

Variable: a data item that may take on more than one value during the runtime of a program.

Variables act as placeholders for unknown or changing values. Think of a variable as a common name for a specific value. 

For example, if the variable was “the date,” then the value of this variable would change depending on what day it was. The name “date” stays the same, but the value associated with it may be unknown or change. 

```php
<?php 
$friday = “Friday”; //Variable assigned a value of a string

$todaysDate = date("Y.m.d"); //Variable assigned a value of a function

$friday = “Monday”; //Same variable defined above given a different value
?>
```

Variables begin with a $ in PHP and no spaces or punctuation are allowed in the name of a variable. The value assigned to a variable in PHP depends on the circumstances of the programmer’s use of that variable. The format for a variable will often look like this: $variable = value; (note the semicolon ending the statement). 

#### Strings
A string is merely the name given to a sequence of simple objects. In PHP, text is often referred to as a string. Of all of the types, strings are often the most static but can be modified in many ways using functions. 

```php 
<?php 

$stringTest = “I am assigning this variable the value of this string, which everything inside of this sentence would be considered in PHP.”; // This sentence is a string

$stringTest2 = “string”; // A string doesn’t have to be a whole sentence, just an simple objects

$stringTest3 = “a 1 ewj ...” // In Fact, a string can be anything as long as it is the type ‘string’

?>
```

#### Arrays

Arrays allow the user to store multiple values in a special kind of variable called an array. It may be helpful to think of an array as a list. Let’s think about it as a list of animals as we go forward  (dog, frog, elephant, cat, wolf, sheep). 

```php
<?php

$animals = array(
“dog”, //key is 0
“frog”,  //key is 1
“elephant”,  //key is 2
“cat”, //key is 3
“wolf”, //key is 4
“sheep”//key is 5
);

?>
```


Each item in an array is given a **key** (a.k.a. ‘index’). A key (or index) in this case is the number in which the item appears within the array starting with 0. These types of arrays are called *index arrays*. We will cover the key/value relationship more in the future. 

[PHP.net - Arrays](http://php.net/manual/en/language.types.array.php)

##### Associative Arrays
An associative array is a different type of array where the items in the array are given names instead of numbers.

##### Multidimensional arrays: 
Multidimensional Arrays are arrays within arrays. Feel free to get into that as much as you’d like, just know that you can embed arrays inside of arrays. 

#### Superglobals

PHP also has certain pre-existing arrays built-in called superglobals. PHP has a huge library of pre-existing functionality and values you can (and will) reference. There are a limited number of superglobals though. We will reference superglobals intermittently throughout the assignments. 

[PHP.net - Superglobals](http://php.net/manual/en/language.variables.superglobals.php)

#### Booleans

Booleans refer to any version of true or false (on or off/ I or O/ 1 or 0). In PHP, the boolean values are not put in quotation marks. If you put quotation marks around a boolean value, then it is a string. 

```php
<?php

$areWeHavingFun = true //boolean value is true
$areWeReally = ‘false’ //not a boolean, this is a string

?>
```
[PHP.net - Booleans](http://php.net/manual/en/language.types.boolean.php)

Booleans are amazingly useful in a lot of programming situations. We will explore them repeatedly as we go forward. 

#### NULL: 

The “null” *value* acts like the boolean value, but represents a variable with no value. A variable will be set to the value NULL if it is left blank or is set to NULL manually.

 ```php
<?php

$var1 = $var2; // var1 is a null value because we haven’t set the value of var2

$var1 = ‘null’; //var1 is no longer null because we have assigned it the value of a string ‘null’

$var1 = NULL; // var1 is again null, but is so because we have set it to be null.

?>
```
[PHP.net - NULL](http://php.net/manual/en/language.types.null.php)

#### Constants

A constant is an identifier (name) for a simple value. As the name suggests, that value cannot change during the execution of the script. A constant is case-sensitive by default. By convention, constant identifiers are always uppercase. You use constants to set up items in your PHP code that will not change. 

```php
<?php
define(‘FAVORITE_ANIMAL’, ‘Dogs’);

//Now our favorite animal will always be ‘Dogs’... always.

?>
```

[PHP.net - Constants](http://php.net/manual/en/language.constants.php)

#### Numbers

##### Integers

Whole numbers are often referred to as ‘integers’ in PHP.

##### Floating Point number

Numbers that contain decimal points are referred to as floating point numbers. As you can imagine, a value can switch from being an integer to being a floating point number is some of the basic PHP math calculations are used. 

#### Conditional Statements: 
Conditional statements allow you to display different outputs according to different circumstances. Conditional statements are essentially logical statements which create an output from an input. 

##### If Statements
The “if” statement is the most common conditional statement. Something will occur “IF” a circumstance is met. This is based off of a boolean value of truthiness or falsehood. 

```php
<?php

if ($var1 = $var2) {
  echo "These variables are the same";
}
?>
```


[PHP.net - If Statements](http://php.net/manual/en/control-structures.if.php)

##### Else Statements
An “else” statement is a gap filler for an if statement and is coupled with an if statement. The logical statement containing both an if and else statement could look like this: IF the sky is blue, then it is sunny. ELSE, it is cloudy.

```php
<?php

if ($sky = ‘blue) {
echo "Sunny";
} else {
	echo “Cloudy”;
}
?>
```

[PHP.net - Else Statements](http://php.net/manual/en/control-structures.else.php)

There is also the else if statement which allows you to compound if statements. More on that later. 

##### Loops
Loops are used to perform repetitive tasks over and over again until a stopping condition is met. The “while” loop is the most common type of loop and the one we will look at the most. 

```php
<?php 

$number = 1; //base value of our variable

while ($number <= 10) { // Will continuously loop through the contained operation until this condition is no longer true
    echo $number; // echoes the value of $number
    $number++;  // Adds 1 to the existing number
} // Ends the while statement

?>

```
[PHP.net - While Loops](http://php.net/manual/en/control-structures.while.php)

#### Functions:
A function is defined to perform preset tasks. PHP has an exhaustive list of its own preset functions and it is possible to write custom functions. We will periodically use functions to perform tasks for us in our code. If there is something you need done, odds are there is a PHP function that can perform the task.

[PHP.net - Functions](http://php.net/manual/en/language.functions.php)

#### Object
An ‘object’ is a sophisticated data type that can store and manipulate values. It is often made by creating a variable with a function and some room for a value (string, array, etc.). This object can then be used intermittently throughout the code.

We will use objects often without explicitly stating they are objects. Much of the programming methodology we will use in this class will be “object oriented programming (OOP). ”

##### Class
A class is the code that defines an object’s features and can be regarded as a blueprint for making objects (think like in CSS). As with objects, we will use classes without stating they are classes. As an exercise, try to point out what constitutes an object and what constitutes a class. 

### Basic skills:

#### Formatting

The easiest way to understand the formatting of PHP is to practice it. Slashes, semicolons, commas, periods, parentheses, and other symbols all have distinct functions in PHP. Knowing where everything goes is important to creating error free code. 

A good thing about PHP is that if you have a semicolon out of place, the whole site will break and you will know you have a problem. The bad thing about PHP is that if you aren’t aware of which symbol is out of place, you could have a frustrating time trying to fix it. 

In this case, practice and attention to detail will help you understand the ‘syntax’ more quicker.

#### Commenting

There are three ways to add comments in PHP and each has a specific use case. Commenting is a very important part of a programmer’s process. It allows you to leave notes for yourself and other programmers. Some practical uses include directions for editing, preventing certain lines of code from executing, giving credit where it is due, any waivers or warnings, and just little tidbits that you need to remember when stopping for the night. Additionally, it allows you to quickly cut out chunks of code you may need later. 

##### Single line comments

two forward slashes between the php tags.

```php

<?php 
// this is a valid comment for single line.
	$variable = “value”; //Setting the value of this variable
# or using the hash sign...
	$variable 2 = “valuable”; # this works too

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

Of course, when you are using just HTML (or if you want to comment outside of the php), use the <!-- commenting method -->

```html
<?php
/* Setting Variable */
$var1 = “variable”; // Equals Variable
?>
<!-- back into HTML so we would set comments using HTML’s syntax -->
<h1>Heading One</h1>
<p>The Variable equals <?php echo $var1; /* Echo value of var1 */ ?></p>
```

(I know the switching between HTML and PHP may seem confusing, but this is how seamlessly they work together).

#### Quotation Marks

Be conscious of which single or double quotation marks you use when programming. This makes a big difference in PHP. Also, do not use quotation marks in the middle of a string - as PHP will consider this to be a break. This is a more complicated conversation for a different day.

## <a name="php-lesson-1">PHP Lesson 1: Introduction to PHP</a>
## <a name="php-lesson-2">PHP Lesson 2: Basic Building Blocks</a>
## <a name="php-lesson-3">PHP Lesson 3: Arrays and Functions</a>
## <a name="php-lesson-4">PHP Lesson 4: Conditional Logic</a>
## <a name="php-lesson-5">PHP Lesson 5: Creating a Contact Form</a>
## <a name="php-lesson-6">PHP Lesson 6: Recapping What We’ve Learned</a>
## <a name="php-lesson-7">PHP Lesson 7: Object Oriented Programming</a>
## <a name="php-lesson-8">PHP Lesson 8: Creating a CMS - coming soon</a>