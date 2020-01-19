---
date: "2019-02-11T19:27:37+10:00"
draft: false
title: Lesson 5 - Widgets Part I
weight: 6
---

WIDGETS :dart: are built-in designs for your website. Not every theme has widgets, but the academic theme has lots of them. 
We will look at them one by one and discuss how you can modify them in your website.                                                                                                                                                                                                                                                                                                                                               
### Introduction to Widgets

The codes of the widgets are written in html and located at `themes/hugo-academic/layouts/partials/widgets/`. 

<p align="center">
<img src="/img/11_codewidgets.png">
</p>

I displayed where the widget files are located in the image above, but there’s no need to look through all of those files right now. Let’s just talk about how those files work. Let’s say that you are at the doctor’s office, and the receptionist gives you a bunch of forms to fill out. The html files in the widget folder are like empty forms at the doctor’s office, with various fields for your information. You simply demand to use a widget in your code, which you will learn how to write in a second, and then you enter your information into the available fields. Let's say you want to use the “experience” widget. The program goes to the widgets folder, takes the experience.html file, fills it out with the info you provided, and returns it in html format, the format to be used in a website. If you know some html coding, you can modify your widgets in other ways, but there’s no need to go that far in this tutorial.[^1]

Before we start, open the source website for widgets in your browser: <https://sourcethemes.com/academic/docs/page-builder/>. If you would like, you can read more about the properties of each widget from there as we proceed (I highly recommend doing so!).  

The homepage of the example website, which locates at `content/home/` in the main directory, has almost all of the widgets in use. We will look at them one by one as they appear on the homepage. You will see which ones are in use from `content/home/` . Please open __index.md__, __hero.md__ and __demo.md__, (open all three of them).

### Index Files

__index.md__ tells blogdown that the files in `content/home/` will create a page that consists of widgets, hence __type = "widget_page"__. You will see an index.md file in nearly all folders. For now, think about this file as the most important guest who sets the tone of the party.

<p align="center">
<img src="https://media.giphy.com/media/feprbmA9EksPvqMcMS/giphy.gif">
</p>

Some of the index files have underscores: _index.md. As far as I understand, when there is an underscore, the page creates branches (that is, it creates other pages). Without an underscore, it creates just one page. This will make more sense when we talk about other folders under `content/`.

The homepage is a single page (index.md without an underscore) with a bunch of widgets. If you would like to create another page that consists of widgets, you should have an index file like this in that folder.  

### hero.md

Let’s take a look at the __hero.md__ file now. __hero.md__ appears first on the homepage. How do I know this? We have a _weight_ option here. This determines the order of appearance (lower values are shown first). If you check all of the other files' weights in `content/home`, you will see that hero.md has the lowest one. If you check demo.md and about.md, you will see that they are the next two.

![](/img/11_hero.png)

__hero.md__ uses the HERO widget. The name of the file doesn't actually have to match with the widget in use (for example, you could rename the __hero.md__ file and it would still use the HERO widget), but this definitely makes it easier for us to follow along :relieved:. 

If you don't want hero.md to appear on your homepage, all you need to do is to change _active_ from TRUE to FALSE. After you save the file, you will see that the hero widget disappears (Did you forget how to see your changes in the viewer? See Lesson 2 - a Quick Start to remember.) Alternatively, you can just delete __hero.md__ from `content/home/`, but I think it is better to keep it there in case you reconsider using it in the future. The same applies to every other file in `content/home/`. By the way, no worries if you delete a file and later want it back! A copy of the example website is present in `themes/hugo-academic/exampleSite/`. You can copy-and-paste any files you want from there later.

Let's continue to look at __hero.md__. _Title_ is self-explanatory = Academic. Next, there is a note: "Enter filename of an image in the `static/img/` folder." It is more organized to put certain types of files in one folder, and blogdown assumes that’s what you’ll do. The `static/img/` folder keeps your image files. To add an image here, you can just enter the name of the image file without writing the whole path. Just a warning, it might not work this way in other themes! You may have to enter the full path or, instead of img, you might have a different name for the folder! Be careful out there!!

In __hero.md__, hero_media and other image parameters use images that you save in `static/img/`. Feel free to create a new folder in `static/img/` to store all of your images for one particular widget. You’ll then need to add that folder name to your path when you add an image. For example, if the hero-academic.png was located in the HEADERS folder (which should already exist within your IMG folder), then, you would need to write hero_media = "headers/hero-academic.png". Don't add `static/img/` in front!

<p align="center">
<img src="/img/11_static.png">
</p>

Even if you don't want to use the hero widget, I suggest reviewing the code and even playing around with it a bit. You might discover some things. For example, I tried to change background color to red by activating _color_ option. Nothing changed :sweat:. Then I realized that the parameters for background gradient overwrites the color option. After I disabled them (by putting # in front of them), the background color became red. Yay! 

__hero.md__ also has these 'Call to Action' links. Compare the codes with the output you have on the viewer in order to understand the function of each parameter. For example, disable one of the [cta] parts (by putting # in front of it) and see what disappears on the website. 

### demo.md

Now let’s check out the __demo.md__ file. __demo.md__ uses the BLANK widget in order to exemplify how to use this type of widget. As you’ll probably notice, the structure of code is very similar to hero.md. You should review and edit each line one by one and see what it does to appearance of the actual website. One example in the ‘Background image’ section: image = "headers/bubbles-wide.jpg" (see the image below). This code takes an image from the source, `static/img/`, and applies this image as the background for this widget (a nifty tool for customizing your website’s appearance).   

![](/img/12_demo.png)

### Markdown files

I think this is a nice place to talk more about markdown files.

The .md extension included on all of the widget files refers to a markdown documentation file. It is basically a plain text file - independent from R - and uses the Markdown language (Later on, we will look at RMarkdown which is a file format for making dynamic documents with R. It uses the markdown format but requires R to run). You can create a markdown document from `File -> New File -> Text File` and name it with the .md extension. As you can see, all of the files in `content/home/` are markdown files.

Both in __hero.md__ and __demo.md__, the parameters and codes related to the widget’s design are written between the "+++" on line 1 and (initially, at least) line 51. You enter the content for the widget after the second “+++”. Let’s take a look at the content section near the end of __demo.md__ after the second “+++” (see the image below). We can, in fact, decode some markdown syntax (or rules for writing markdown code) by examining this text.

![](/img/12_markdown.png)

For example:

- **personal demo** appears in bold in the website because it is written between double stars in the code.

- *background* and *image parallax* appear in italics in the website because they are written between single stars in the code.

- When displaying a link, the website address is written in parentheses and the text of the link in square brackets.

- There is also an alert note, as you can see, "alert note" between percentage signs and curly parentheses start the note, and /alert ends it. When you write in between them, it creates a box with your content. Although it seems that this involves some html coding, it is just enought to know how to use alert note.[^2]

When you build your site, Hugo will convert all these markdown files into html codes and save them in the `public` folder. 

Take a look at [the markdown cheatsheet](https://www.markdownguide.org/cheat-sheet/) for some more basic syntax. And if you are eager to see some html codes, see the wikipedia page for some conversions from markdown to html in the Example section at <https://en.wikipedia.org/wiki/Markdown>.

NEXT LESSON: More WIDGETS :yum:


[^1]: Just in case you do go and modify widgets with html, don't forget that you are not supposed to change anything in `themes/hugo-academic`. If you are going to modify a widget, create a folder `layouts/partials/widgets` in the main directory. Copy-and-paste the widget html file you want to modify to this folder, then modify as you wish!

[^2]: The code for the alert note is located at `themes/hugo-academic/layouts/shortcodes/` if you are curious about some html codes, take a look. 
