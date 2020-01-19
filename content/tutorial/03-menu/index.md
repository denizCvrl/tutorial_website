---
date: "2019-02-11T19:27:37+10:00"
draft: false
title: Lesson 3 - Menu of Your Website
weight: 4
---

In this lesson, there is a short discussion of "projects" in R. Then, we will be back to working on the website to learn how to create the menu of your website.  

### Projects in R

Sooo, in the last tutorial we had all those files open and we were working on them. Do we have to open them one by one again? Nah! 

If you go to the folder you created, you will see your project with blue hexagon R doodle and .Rproj extension (mine is called COOLWeb.Rproj because I named my project COOLWeb). When you open that file, you will be back to wherever you left off without bothering to open your files one by one. You will see all of the files we opened in the last tutorial: __config.toml__, __languages.toml__, __menus.toml__, __params.toml__ 

<p align="center">
<img src="/img/6_filelocation.png">
</p>

The greatness of using "projects" is not just that you don’t have to bother opening individual files again. It's also great because whatever you create within the project will be saved in the project folder. If you send your project folder to somebody else, they do not need to change anything in your code. This is why it is not recommended that you use __setwd("a path on YOUR computer")__ to change your directory. This function requires a path on your  computer. When you send your codes to somebody else, they have to manually change that path. So, avoid using setwd() as much as possible.

This tutorial is also about getting familiar with R so let's talk some more about the projects. What if this was not a website-building project but something else, like data analysis, writing a book, writing an article or both data analysis and writing a book. You can follow the same steps we had: from the menu `File -> New Project`. Instead of creating a blogdown website project, you will create a normal project. 

### Back to Our COOLWeb

Please run the serve_site() function again to see your website in the viewer.

```r
blogdown::serve_site()
```

We had three files open: __languages.toml__, __menus.toml__, __params.toml__.

Don't change anything in __languages.toml__ if you want your website in English but this is where you would go if you wanted to use a different language. 

__menus.toml__ contains the navigation links of the example website. If you go to the menu of your website in progress, you can see what they look like. You should decide on how many sections you need, how you want to name them and the order in which they appear. As it is written in the explanation, __weight__ determines the order that the links appear. These weights are simply ascending numbers, but it’s good to leave space between the numbers so you can add sections later. That's why the examples are multiples of ten.  Play with the names and order. For example, write 41 to Post's weight. It will appear after Publication in the menu.  

![](/img/6_menus.png)

Your website uses built-in WIDGETS. They are ready-to-use designs that you can easily employ. For example, look at the Experience section in the example webpage. All you need is to enter your information from your CV and tell the program use the _experience_ widget. More about WIDGETS coming soon!

In __menus.toml__, notice the difference in Course's url. Unlike the url for Courses, the other urls have __#__ in front of their parameters and do not have / after. The # indicates that those links target somewhere on the homepage. For example, click Posts on the website. It will show you the Posts section on the homepage. On the other hand, when you click Courses, it opens a new page. I mentioned this difference in a previous tutorial and now you will learn how to create those links.

It is all about urls in __menus.toml__. Using # in front of the link parameter creates a path to `content/home/` in your directory. Take a look at `content/home/`. You will see posts.md file (we will talk about .md extension in the next lesson).

In __menus.toml__, url = "#posts" refers to posts.md file inside `content/home/`.

![](/img/6_menus2.png)


Well, url = "courses/" refers to `content/courses/`. In short, if you want a separate page, then you need to create a new folder within the `content` folder. Let's try. There is also `content/post/` (See the figure). Why don't you write url = "post/" instead of url = "#posts". Save the file and you will see that Posts in the menu will open a new page. 

Don't worry about filling those sections with your content at this time. For now, you can organize your sections and choose how they will be displayed on your website.

NEXT: __GLAM TIME!__

<p align="center">
<img src="https://media.giphy.com/media/gfYXvjYB3ROSLpNo2D/giphy.gif">
</p>
