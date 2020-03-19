---
date: "2019-02-11T19:27:37+10:00"
draft: false
title: Lesson 2 - A Quick Start
weight: 3
---

In this lesson, you will build the example site of the academic theme. Later, we will modify the elements of this website. Our aim is to teach you the structure of folders so that you can apply a similar logic while using other themes. 

## Let’s Build a Website (Section 1.2 and 1.3 in the Manual)

[The blogdown manual](https://bookdown.org/yihui/blogdown/) describes two ways to begin creating a website: either by writing a command on the console, __blogdown::new_site()__, or by choosing blogdown website option from the menu. For its simplicity, we will follow the second method :smile: `File -> New Project -> New Directory -> Website using blogdown`. If you don’t see this option, try restarting your R session (cmd/ctrl + shift + F10). 

![](/img/3_creatingwebsite.gif)

First, provide a name for your project under __Directory name__. This is not the name of your website, just the name of the R project. Since you are learning how to make a very cool website, I am calling it "COOLWeb" :sweat_smile:. If you want to save your project in a subdirectory, click Browse and choose the directory. Otherwise, leave it as it is. Your project will be probably under `Documents`. You can check it with __getwd()__ later.

Second, decide on some options regarding your website. We already installed Hugo in the previous lesson. It was a nice opportunity to introduce functions :wink:. It is okay to uncheck that option if you completed the first lesson. You will see [lithium](https://themes.gohugo.io/hugo-lithium-theme/) as a theme. We will use [academic theme](https://themes.gohugo.io/academic/) in this tutorial. Paste gcushen/hugo-academic into the Hugo theme line. The documentation of the academic theme is massive. It also has relatively more options to modify your website. Basically choose everything as we have below and click "Create Project".

<p align="center">
<img src="/img/4_academictheme.png">
</p>

__A side note:__ I realize that you may prefer another theme. But, I think we should try to understand the logic of the blogdown package (and how to use R) first. Then you can play around with other themes if you want. If you just have to use another theme, be aware that two potential issues that might arise. First, not every theme has been tried with the blogdown package, so you might have compatibility issues. Second, although the logic is the same, file names or file paths might be different in each theme, which could get confusing in later sections of this tutorial.

__Another side note:__ Notice that you now have four panels in R! :smile:.

Now, you can see the files blogdown created at the right bottom corner of RStudio. They are all saved automatically in the directory you selected for your website projects. These are the files needed to make this example website: <https://academic-demo.netlify.com/>.

<p align="center">
<img src="/img/5_files.png">
</p>

I find it incredibly frustrating to have so many files and not know what they are for, so I am going to review as many of them as possible throughout this tutorial to help you understand their functions (well, at least as far as I know and understand them). We will discuss many of the files in more detail later on, but here is a quick introduction: 

- __config.toml__ and __config folder__: These are involved in setting certain global options and the appearance of your website. 

- __content folder__: This one is kind of obvious. It’s the folder that stores your original content. Before moving on, I want to provide some important structural information about this folder and how it relates to the website. Follow along with steps below. 

    1. If you look at the menu bar at the top of [the example website](https://academic-demo.netlify.com/), you will see Demo, Posts, Projects, Publications, Courses and Contact as the options. 
    2. Clicking on any of these options, except Courses, will land you into a different section of the homepage. Click `Projects` to see what I mean. Courses, on the other hand, opens a new page. 
    3. Now, click on `content` folder under Files on RStudio (See the figure above). You will see a number of folders: authors, courses, home, post, projects, publication, etc.
    4. For now, just focus on __home__ and __courses__. The __home__ folder consists of files that create the homepage of the website. 
    5. All options in the menu bar of the example website (except Courses, of course) refer to a file present in `content/home`. That's why they all land into homepage. 
    6. Courses, on the other hand, refers to `content/courses` and thus opens a new page when clicked. 

    Later on, we will talk about how to create links and organize  these folders/files, but it is important to simply understand the structure of these folders before we get to all that.

- __static folder__: Some static files, such as your profile photo, will be kept here. 

- __themes folder__: This folder stores the codes to set up the theme of your website. We are using the __academic theme__. The config.toml and files in the config folder take the theme information from this __themes__ folder. __DO NOT CHANGE ANYTHING IN THIS FOLDER EVER! :no_entry: :boom:__

Okay, we can now create the example website using another function from the blogdown package. Type the following function into the R console (By the way, do you remember why we need the package name in front of a function? If not, see the previos lesson): 

```r
blogdown::serve_site()
```

While you are typing, R gives you the possible package and function options. You can use up and down arrow to choose the ones you want instead of typing all the way. 

<p align="center">
<img src="/img/4_options.gif">
</p>


- __public folder__: When you hit the enter, the mobile version of the example website will be rendered in the viewer window (or the normal website in your browser). This action will create the public folder. Hugo renders our content and theme, and put everything in this folder. Similar to the themes folder, YOU WON’T BE CHANGING ANYTHING :no_entry: :boom: in the public folder. This is the folder I meant in the introduction of the tutorial :wink:. 

![](/img/4_examplewebsite.gif)

Let’s talk about __config.toml__ that is already open at the left corner. Information in __config.toml__ sets some global parameters of your website. You migh be wondering about what that toml extension is in the name. It is an acronym for "Tom’s Obvious, Minimal Language", a configuration file format that consists of `key = "value"` pairs. For example, the very first pair in config.toml sets the title of your website: `title = Academic`. You can create a toml file from `File -> New File -> Text File` and naming the file with toml extension. You do not need to create one for this tutorial though.   
Let’s play around a bit to see how we can begin to change the information on website. Notice the red notes in the console. These notes indicate that whenever you make a change in your website, you will be able to see the changes right away. Let's see if this is the case by modifying __config.toml__.

Write your name instead of Academic in title and type `&copy; YOUR NAME, {year}` for copyright.

title = "Academic"

copyright = " "

![](/img/5_changetitle.gif)

As soon as you save the config.toml, your website will be reloaded with the changes and you will see your name as the title! If you go to the end of the site, you will see a copyright on your name. Go ahead and try! :smirk:

Now, you have two options for how you view updates to your website as you work on it:

1. If you think that it is unnecessary to see changes each time you save a file, you can simply follow one of the instructions in the red note: __run servr::daemon_stop("number") or restart your R session__ (cmd/ctrl + shift + F10). Then, whenever you want to view all of your changes, use __blogdown::serve_site()__ function AGAIN to see the latest version of your website. Follow the instructions again if you want to stop updating. (Shortcut: Use up-and-down arrows from your keyboard in order to bring the codes you already wrote on the console.)   

2. If you like tracking your changes as you make them, then you’re all set! Just be sure to use serve_site() function again each time you restart your R session. (Tip: You can also see a desktop version of your website in your browser from the address of the local server. What address? It is there in the red notes, it starts with `__http://__`. Mine is `http://127.0.0.1:3655/` in the gif above. Paste that address into a browser to view your website in all of its glory!)

FYI: Out of curiosity I ran __serve_site()__ function for the second time without restarting my session and the website automatically opened in my browser. Then, things got complicated. It started to show my changes only in the browser version. I ran it a third time, fourth time... Occasionally, I was able to see changes both in my browser and in the viewer, but other times only in the browser. I am not sure if this is a bug, or there is some kind of logic I couldn’t figure out. Anyways, I might need to update this information in the future, but I wanted to warn you. Ultimately, if you are seeing your updates either in the viewer or in the browser, you are good to go.  

__Side note:__ You will probably see another function in other tutorials or in the manual: __blogdown::build_site()__. You can either write this code to the console or use the panel in RStudio at the right corner and click Build Website to call __blogdown::build_site()__ function. I want to discuss the difference between __serve_site()__ and __build_site()__. In __config.toml__ there is `baseurl="/"` in between title and copyright. When you have your own website address, you will enter the address in this key. I will show you how to get a website address later on in this tutorial. However, let’s assume I already have `baseurl="https://denizc.com/"`. __build_site()__ creates paths that includes this full address. For example, if I had a page referring courses folder, the path would be `https://denizc.com/courses.` __serve_site()__, on the other hand, creates paths referring to local files in your computer. In my case, the local path is `http://127.0.0.1:4321/` and so the path for the course folder is `http://127.0.0.1:4321/courses`. We will use __serve_site()__ for now.[^1]    

The rest of code in __config.toml__ might appear overwhelming at first (hang in there - you can do this!), but some of the code is, in fact, rather self-explanatory. Consider "enableEmoji", which determines if you allow using emojis on the website, and defaultContentLanguage, which sets the language (see, coding’s not so bad). For now, let’s just keep everything as it is. We will come back and change a couple of things later on in this tutorial, if nothing else, at least baseurl.    

Now go to the `config/_default` folder (the default folder is in the config folder) back in the Files section of R session and open all three files: __languages.toml__, __menus.toml__, __params.toml__. The next lesson will explain what these files for and further explain the __config folder__, but you have already learned a lot in this lesson. You deserve a break! 

Before we finish, I just want you to check where your project is located on your computer. If you don’t already know, use getwd().

Mine is in `C:/Users/DC/Documents/COOLWeb`. You should have something similar. Once you know exactly where your project is located, simply close the R window. There is NO need to close each file or section, just close the big window. 

You might be feeling a bit overwhelmed after this exhausting R session. All of these codes and files and paths can be intimidating, but I assure you that you do not need to be a master programmer to get through this tutorial and build a beautiful website. So, to lighten the mood and help you wind down, here is one of my all-time favorite sketches that I found extremely relevant. Right now, you might feel like the monk asking for help, but soon you will feel more like the medieval helpdesk! Enjoy, and see you next time!

{{< youtube pQHX-SjgQvQ >}}

[^1]: If you are interested, [the blogdown manual](https://bookdown.org/yihui/blogdown/) has some explanations in Section 1.3 where it says "see Section D.3 for details". 
