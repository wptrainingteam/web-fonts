# Web Fonts

## Description

Why Web Fonts? They make a huge impact on the look and feel of your website, as well as the overall readability. You will learn how to use these to make your website stand out.

* * *

## Prerequisite Skills

*   Basic knowledge of HTML/[CSS](https://make.wordpress.org/training/handbook/theme-school/intro-to-css/)
*   Basic knowledge of [installing and activating WordPress themes](https://make.wordpress.org/training/handbook/lesson-plans/user-lessons/choosing-and-installing-a-theme/)
*   Understanding of how folders and files are structured
*   Ability to edit files with a text editor

* * *

## Objectives

After completing this lesson, you will be able to:

*   Define the purpose and advantages of using web fonts.
*   Embed web fonts to your website using Google Fonts library or using `@font-face`, while being able to explain the implications of this choice.

* * *

## Assets

*   WordPress installation
*   [Twenty Sixteen](https://wordpress.org/themes/twentysixteen/) theme
*   [Indie flower](https://www.google.com/fonts/specimen/Indie+Flower) font
*   [Meadowbrook](http://www.dafont.com/meadowbrook.font) font
*   [Squirrels @font-face generator](http://www.fontsquirrel.com/fontface/generator)

* * *

## Screening Questions

1.  Are you familiar with the concept of a theme in WordPress?
2.  Have you worked on a child theme/modified your installed theme before?
3.  Do you have a self-hosted WordPress website?

* * *

## Teacher Notes

*   **Time Estimate:** TBD.
*   The recommended way to approach the scenarios would be to demonstrate and explain the process first and then ask students to repeat the actions using their own devices, while you’re available for questions and troubleshooting if something doesn’t work out.
*   It is easiest for students to work on a locally installed copy of WordPress. Set some time aside before class to assist students with installing WordPress locally if they need it or, if possible, send them instructions before the class so they can come prepared. For more information on how to install WordPress locally, please visit our [Teacher Resources](https://make.wordpress.org/training/teacher-resources/) page.
*   The preferred answer to the screening questions is “yes.” Participants who reply “no” to question #1-2 might require a bit of explanation, and if they answer “no” to question #3 they may be grouped with other students to work in pairs on the task.
*   You may print out the Hands-On Walkthrough to use it as handouts or send it out as a .pdf file and preserve the links used throughout the document.
*   You need to have internet access or font files on a flash drive, etc., available for the participants.

* * *

## Hands-on Walkthrough

### Introduction: What are Web Fonts and why should you use them?

Web fonts are fonts that have been **_licensed specifically for web use_**. Traditionally, designers were limited to a small set of common system fonts that were already installed on a user's computer (think Times, Arial, Helvetica, and Verdana). Around 2008 or so, each of the major web browsers began to implement a version of `@font-face` linking which allows the designer to use a wide range of fonts which can drastically improve the design and/or readability of the website.

### So what is `@font-face`?

**`@font-face`** is a CSS rule which allows you to embed a particular custom font from your server to render a webpage even if it's not already installed on the site visitors computer. Not only is it cross browser compatible but it also means that a designer doesn’t have to rely on only “web safe” fonts. In addition, designers and '_type foundries_' (companies that design or distribute typefaces), do not want their raw (.ttf and .otf) fonts uploaded to websites where they can easily be downloaded (stolen). `@font-face` permits linking directly to the raw font file. "Raw," meaning an uncompressed, unprotected font file, just like you’d find in the font folder on your computer.

### Putting it all together: Using `@font-face`

**Scenario:** We want the headers encountered in the posts on our website to stand out by changing their font to something special. [tip]In real life, you would be:

*   Making a backup of your site before you proceed with any changes
*   Modifying your own child theme at this point. However, to make things easier for this lesson, you will be editing [WordPress Twenty Sixteen Theme](https://wordpress.org/themes/twentysixteen/)

[/tip]

#### Step 1: Find the font you want to use

1. We will be using the free [Meadowbrook](http://www.dafont.com/meadowbrook.font) font. Let's download it from the website by clicking the **Download** button. 2. Open the zip file. You'll see Meadowbrook.ttf file there. Keep in mind that there are different kinds of font formats and they aren’t all suitable for different platforms. TTF is a font format compatible with Internet Explorer version 9.0 and above, Chrome starting at 4.0, Firefox at 3.5, Safari since 3.1 and Opera beginning with 10.0. To make your website work on all cross-platform web browsers, we need to get the same font in multiple formats. 3. It is possible to convert a font yourself, however, a more simple way is to use [Squirrels @font-face generator](http://www.fontsquirrel.com/fontface/generator). Additionally, it will even generate the CSS code we'll need at the next step! 4. Upload the Meadowbrook.ttf file to the generator, choose "Optimal" and tick the agreement. [![Selection_036](https://make.wordpress.org/training/files/2014/10/Selection_036.png)](https://make.wordpress.org/training/files/2014/10/Selection_036.png) 5. Download the resulting kit. It should be a .zip file with the font formats required, a .css file and a .html test file.

#### Step 2: Place the font files in your theme directory

1. Make sure you've activated [WordPress Twenty Sixteen Theme](https://wordpress.org/themes/twentysixteen/). 2. Upload the fonts to the base directory of your theme. It is easier to keep your files organized if you create a _fonts_ folder in <your root WP folder>/wp-content/themes/twentysixteen and put the files there. [![Selection_037](https://make.wordpress.org/training/files/2014/10/Selection_037.png)](https://make.wordpress.org/training/files/2014/10/Selection_037.png)

#### Step 3: Add the `@font-face` declaration code into your css

1. Open stylesheet.css which resides in the .zip file you downloaded from Squirrel `@font-face` generator. 2. Copy its content. 3. Time to embed it to your theme's stylesheet: open the style.css file in Sublime/gedit/Notepad/any other text editor you're comfortable using. The theme's style.css file's path should be: <your root WP folder>/wp-content/themes/twentysixteen.

<pre>@font-face {
 font-family: 'meadowbrookregular';
 src: url('meadowbrook-webfont.woff2') format('woff2'),
 url('meadowbrook-webfont.woff') format('woff');
 font-weight: normal;
 font-style: normal;
}</pre>

4. Paste the `@font-face {...}` piece right before the `body {...}` part. 5. Since we made a fonts folder we now have to modify the code a bit. “fonts/” is to be added to the beginning of each font location:

<pre>@font-face {
 font-family: 'meadowbrookregular';
 src: url('fonts/meadowbrook-webfont.woff2') format('woff2'),
 url('fonts/meadowbrook-webfont.woff') format('woff');
 font-weight: normal;
 font-style: normal;
}</pre>

[![Selection_039](https://make.wordpress.org/training/files/2014/10/Selection_039.png)](https://make.wordpress.org/training/files/2014/10/Selection_039.png) 6. Save the file.

#### Step 4: Call the font using `font-family:`

1. Continue editing style.css file: find a section where all of the headers are described. You may search for '_h1,\nh2,\nh3,\nh4,\nh5,\nh6 {_'. Add the following line to the body of this attribute:

<pre> font-family: 'meadowbrookregular', Georgia;</pre>

Here 'meadowbrookregular' is a reference to the `font-family` name we initialized in the previous step and Georgia is a failover font that will be used in case 'meadowbrookregular' is not available. 2. Save the file. [![Selection_040](https://make.wordpress.org/training/files/2014/10/Selection_040.png)](https://make.wordpress.org/training/files/2014/10/Selection_040.png) 3. Create a new post with some headers or refresh an old one. Note the new styling. [![Selection_041](https://make.wordpress.org/training/files/2014/10/Selection_041.png)](https://make.wordpress.org/training/files/2014/10/Selection_041.png)  

### Alternative: Using Google Fonts library

Alternatively, you can use Google Fonts library, which contains a plethora (close to a thousand) of font families. We will take a look at how to embed fonts from Google Fonts library manually, but there are also plugins which do the trick. **Scenario:** to make our blog seem more approachable, we will be using Google Fonts library to set up our website to use a memorable "hand-written" style font for the headers of its entries. [tip]In real life, you would be:

*   Modifying you own child theme at this point. To make things easier, you will be editing [WordPress Twenty Sixteen Theme](https://wordpress.org/themes/twentysixteen/)
*   Making a backup of your site before you proceed with any changes

[/tip]

#### Step 1: Find the font you want to use

1. Go to [Google Fonts library](https://www.google.com/fonts) website. You will be using Indie Flower font. Type "Indie flower" into the search field. 2. When you have found the required font, click quick-use button. [![Selection_029](https://make.wordpress.org/training/files/2014/10/Selection_029.png)](https://make.wordpress.org/training/files/2014/10/Selection_029.png) 3. At the next screen, you're able to select the styles you want - there's only one style for Indie flower. Scroll a little bit to find **Add this code to your website** section. Click the embeddable code and copy it using **Ctrl + C** (or **Cmd + C** for Mac).

<pre><link href='https://fonts.googleapis.com/css?family=Indie+Flower' rel='stylesheet' type='text/css'></pre>

4. Save the file.

#### Step 2: Add the import code into your header.php

1. Make sure you've activated [WordPress Twenty Sixteen Theme](https://wordpress.org/themes/twentysixteen/). 2. Open its header.php file in Sublime/gedit/Notepad/any other text editor you're comfortable using. The file's path should be: <your root WP folder>/wp-content/themes/twentysixteen. 3. Add the code you've previously copied right after the <head> tag. [![Selection_033](https://make.wordpress.org/training/files/2014/10/Selection_033.png)](https://make.wordpress.org/training/files/2014/10/Selection_033.png) That’s all - you have successfully added a custom Google Fonts to your WordPress site.

#### Step 3: Call the added font

1. Now let's use this font in our theme’s stylesheet: Open your style.css file in Sublime/gedit/Notepad/any other text editor you're comfortable using. Add 'Indie Flower' to the `font-family `attribute of the `.entry-title` section like shown on the screenshot: [![Selection_034](https://make.wordpress.org/training/files/2014/10/Selection_034.png)](https://make.wordpress.org/training/files/2014/10/Selection_034.png) 2. Save the file, refresh your webpage and take a look at the entries headers! [![Selection_035](https://make.wordpress.org/training/files/2014/10/Selection_035.png)](https://make.wordpress.org/training/files/2014/10/Selection_035.png)

### **Which method should I choose?**

So what is the main difference between using `@font-face` and a set of embedded Open Type (EOT), Web Open Font Format (WOFF), True Type (TT), and Scalable Vector Graphics (SVG) files or Google Fonts? Google Fonts are handled through a content delivery network (CDN), but your font files embedded via `@font-face` would be stored locally. Some of the advantages of using the CDN are:

*   The font files may have been cached from any other site using the same font
*   Heavy font files will be downloaded from a different site, saving bandwidth on your server

However, when using locally-stored fonts you're not dependent on an outside resource. You will be fully covered in case the third-party site no longer hosts your font, modifies it or goes down (though it’s not really likely for a service as popular and widespread as Google Fonts).

* * *

## Conclusion

Using web fonts is a great way to make your site look good and appeal to its readers. You can also use it to make your commonly used WordPress theme look special with just a little effort. You can approach adding a custom web font to your site in the several ways, for example:

*   Selecting the font you like in the Google Fonts library and embedding it to your theme's header.php
*   Uploading the font files to your website and embedding them to style.css using the `@font-face` rule

* * *

## Group Exercises

Add an additional font to your site for the blog header using either one of the discussed methods.

* * *

## Quiz

**Where should you put the `@font-face` directive to make a downloaded font display on your site?**

1.  index.php
2.  functions.php
3.  header.php
4.  style.css

**Answer:** 4. style.css

**Which of the following properties is used to specify the font of a certain element?**

1.  font-family
2.  font-face
3.  font-style
4.  style-css

**Answer:** 1. font-family

**What is a possible drawback of using the Google Fonts library?**

1.  Visitors will need more bandwidth to access your site
2.  You have to pay to use it
3.  Relying on a third party to host your fonts
4.  Caching the font files may be disruptive for your website's security

**Answer:** 3. Relying on a third party to host your fonts

* * *

## Additional Resources

1.  Make sure to read [Playing with Fonts](http://codex.wordpress.org/Playing_With_Fonts) @ Codex, and note this article has an extensive Font resources/troubleshooting section.
2.  [CSS Web Safe Font Combinations](http://www.w3schools.com/cssref/css_websafe_fonts.asp) @ w3schools is a list of some commonly used font combinations, organized by generic family.``
