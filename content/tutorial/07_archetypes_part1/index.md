---
date: "2019-02-11T19:27:37+10:00"
draft: false
title: Lesson 7 - Archetypes Part I
weight: 8
---

At last, how to create new posts, publications, etc. Now that we have covered widgets, it’s time for archetypes. Things might get complicated at this point. 

From this point on, you will want to choose the path that best suits you. You may find, for instance, that certain details are not needed for the website you are creating, or that you want to use different options than the ones presented here. That’s fine! But if you’re worried about getting lost, just be sure to read through each part so you don’t miss anything important.   

### Creating Content

Please go to your __menus.toml__ and change url="#posts" to url="post/"   so that it will create a new page from the `content/post/` folder  instead of landing on the homepage (`home/posts.md`). Publish your website locally using blogdown::serve_site() and then click Posts on the menu in order to see the page created.

<p align="center">
<img src="/img/18_blog0a.png">
</p>

Now go to the Files section of R and access the folder __`content/post/`__. Open the \_index.md file. As we discussed before, it tells blogdown that this page will create other pages (since it has an underscore).[^1] 

<p align="center">
<img src="/img/18_blog0b.png">
</p>

Just for your information, the options for "view" in \_index.md are (you saw them in __params.toml__ as well as in some widget .md files): 

 1: List
 
 2: Compact
 
 3: Card
 
 4: Citation (publications only)
 
Looking at the post folder, you will see that most of the posts are written in markdown (.md) format and are located in separate folders, while there is one file appears directly within the post folder with the extension .Rmd: 2015-07-23-r-markdown.Rmd. It is for the post that is titled “Hello R Markdown”. What is Rmd? 

### R Markdown files

It is time to introduce R Markdown. 

Markdown (.md) doesn't support/run R code. As I wrote before, markdown is independent from R. Rmarkdown (.Rmd), on the other hand, is an extension of the markdown syntax and is able to execute R code. The manual has a nice comparison of the file types you’ll encounter as you create your website: <https://bookdown.org/yihui/blogdown/output-format.html>.

No worries if you feel like you are lost, and you might! If this is your first project ever with R, “executing R code” might not mean anything to you at this time because this is your first project ever with R. To get more acquainted with Rmarkdown files, check out one of the many tutorials online. I recommend starting with the official one here: <https://rmarkdown.rstudio.com/lesson-1.html>. 

`content/post/` has examples of post created using both .Rmd and .md files. Take a look at the .Rmd file in R and compare it with the Hello R Markdown post on the website to get a sense of how the Rmarkdown file is used to create website content. I suggest creating a couple of posts with different options to find the method that works best for you. It is better to simply use markdown (.md) files if there is no need for the additional properties of Rmarkdown.  

I also suggest experimenting with other folders, such as courses, project, publication, talk. They have similar structures: a folder/file for each post/course/publication/talk. The project folder, for example, doesn't have an index file. You can try to add one and see what happens.

If the rest of this lesson feels like it requires too much programming, you can just copy-and-paste a folder from the example folders and change the content each time you want to add something new. 

But, if you want to create your content in a more organized and efficient way, you will like the rest of this lesson and the next one :raised_hands: !!

### Blogging using the Addins

Our aim is to add a new post. Go to Addins and choose New Post  . 

<p align="center">
<img src="/img/18_blog1.png">
</p>

Alternatively, you can also write the command below in order to open the New Post window [^2].

``` r
blogdown:::new_post_addin().  
```

Enter a post title and observe the changes in Filename and Slug. By default, the subdirectory is `post`. You can create a SUBsubdirectory :smile: by just adding a name, such as subdirectory = `post/NEWFOLDERNAME`. 

<p align="center">
<img src="/img/18_blog2.png">
</p>

The program will automatically create a path for you using your title: `/SUBDIRECTORY/:year-:month-:day-:title/`. 

### Some Advanced Stuff I:

The automatically created path might be a problem because it includes the title of your post. If you change your title later, and somebody still has the previous link, they will not be able to reach your post. [2.2.2 Options](https://bookdown.org/yihui/blogdown/configuration.html#) of [the blogdown manual](https://bookdown.org/yihui/blogdown/) suggests setting up permalinks in __config.toml__ by adding:

```r 
# Permalinks
[permalinks]
  posts = "/:year/:month/:day/:slug/"

```
As you might notice, this means you should provide a “slug” for each post you create. The slug will remain consistent even if you change your post title, ensuring that the links to the post will remain consistent as you update titles. Beyond that, it is up to you how to design your posts' links. For example, personally I like `post` in the path  so that one can understand from the link that the entry is under post on my website:

```r 
# Permalinks
[permalinks]
  posts = "/post/:year-:month-:day-:slug/"
```

### What's Archetype?

In the drop-down menu of __Archetype__ in the new post window, you have many options: default, docs, home, post, project, publication, slides, and talk. They are content template files with preconfigured front matter. Since we already covered the `content/home/` folder, let me explain what preconfigured front matter is by comparing __default__ and __home__ options. 

__Home__ option creates a template that you can use for a widget. While we were managing widgets in the home folder, we copied and pasted .md files  to create new widgets . Well, you could also go to Addins, choose New Post and then select __home__ as an archetype.

__Default__ option, on the other hand,  gives you a template for a post similar to the ones in `content/post/`. 


![](/img/19_archetype1.png)

I was wondering if this method could be used to create other types of content for my website. So, I tried selecting other options from the Archetype dropdsown menu, hoping that it would have similar templates to those in other folders of the example website (`content/publication/`, `content/projects/`, etc). Nope, that didn’t work!

Then I realized that it's because of the structure of `themes/hugo-academic/archetypes/`, which is where these template files are present. The templates are there, but are located in their respective folders as index.md. Home and Default options work because they are not in separate folders (see the image below). 

![](/img/19_archetype2.png)

Remember that you are not supposed to change anything in `themes/hugo-academic/`! So, I created a folder called `archetypes/` at the root of my side (directly in my “COOLWeb ” folder). Then, I copied and pasted the index.md files into this folder and renamed them with their respective types. You are good to go after these steps  ! Also, feel free to make some custom changes to your archetypes :wink:. The next lesson will go over these steps again! 

### Some Advanced Stuff II:

There are some caveats in creating blog posts. With the current settings, you should save all images under `static/` folder. This is not optimal, especially if you have multiple images in one post. Also, it is so against the nature of programming if you have to enter your name each and every time you write a post. 

Thanks to [Alison Hill](https://alison.rbind.io/)'s blogposts about [page bundles](https://alison.rbind.io/post/2019-02-21-hugo-page-bundles/) and [archetypes](https://alison.rbind.io/post/2019-02-19-hugo-archetypes/), I learned how to overcome these problems. It is better to read her blog for more clearly-explained details, but here are the steps I followed based on her instructions. 

Once again, we have two aims:

1. Saving related images in the same folder where your post is located instead of saving under `static/`.
2. Automating some settings, such as creating Rmarkdown instead of markdown files, entering author's name, etc.  

We are going to create a .Rprofile[^3] file, which is a file that R reads whenever it starts. In this .Rprofile file, we can set some general settings. Depending on the location of this file, these settings can be global or project-specific.  

Before we start, we need to clear one technical issue: The last line has to be empty in an Rprofile file (source file). If you forget that and don't realize it, you might have some headaches. It is better to follow the suggestion of [Alison Hill](https://alison.rbind.io/post/2019-02-21-hugo-page-bundles/) and [Yihui Xie](https://yihui.org/en/2018/04/rprofile-trailing-newline/). Go to `Tools -> Global Options -> Code -> Saving` and choose "Ensure that source files end with newline"


<p align="center">
<img src="/img/20_newline.png">
</p>


In order to create an Rprofile file, install **the usethis package**. You can skip the first line below if you already have this package in your computer. The second line creates an .RProfile file in your directory and it automatically opens it. By setting scope = "project", we tell R to create .RProfile for your project. The last three lines are the messages you receive. Don't forget to restart your session (cmd/ctrl + shift + F10).

```r

install.packages("usethis") 
usethis::edit_r_profile(scope = "project")

✔ Setting active project to 'C:/Users/DC/Documents/COOLWeb'
● Modify '.Rprofile'
● Restart R for changes to take effect

```
Now, you can tell .Rprofile to allow bundles by entering TRUE in blogdown.new_bundle, which lets you save your image files to the same folder your post is. Copy and paste the code below to your .Rprofile and modify as you need.  

```r
if (file.exists("~/.Rprofile")) {
  base::sys.source("~/.Rprofile", envir = environment())
}

options(
  servr.daemon = TRUE,
  blogdown.author = "YOUR NAME",
  blogdown.ext = ".Rmd",
  blogdown.subdir = "post",
  blogdown.yaml.empty = TRUE,
  blogdown.new_bundle = TRUE,
  blogdown.title_case = TRUE
)

```

Here’s a brief explanation of each of the options in the code above:
- servr.deamon: Do you remember it from the second lesson? You can turn it off if you want by turning TRUE to FALSE (I tried and it didn't work. Maybe it is related to the new updates! I want to keep it on anyway!). 
- blogdown.author: So that you do not have to write your name each time you post something.
- blogdown.ext: You can set Rmd as default if you want. 
- blogdown.subdir: `content/post` is the default directory, change it as you wish.
- blogdown.yaml.empty: See [archetypes](https://alison.rbind.io/post/2019-02-19-hugo-archetypes/) by Alison Hill if you are curious.  
- blogdown.new_bundle: Allows bundles to keep images in the same file.
- blogdown.title_case: Corrects inconsistent capitalization.   

With page bundles, you do not need to create a SUBsubdirectory :smile:. It automatically creates a new folder (date+title as a name but you can change it) with its own index file at your choice of file type. I am not sure if you need to set permalinks in config.toml with page bundles. As long as you keep the name of the folder, you should be free to change the title in your index.md(Rmd) file, I think. I haven't tried though  .   

YOU ARE ALL SET for BLOGGING!


[^1]: The "project" folder doesn’t have any index file. Therefore, I have experimented with the index file of the "post" folder. For example, I deleted its underscore and the page didn't show me anything but the title. I deleted the file completely. I was surprised that I was able to see the content so \_index.md is not a must-have. However, I wasn't able to change the title or view.

[^2]: Notice the triple colons in the command. If I were you I would google the difference between two and three colons and what addin means in the code, etc. I don't explain it here to keep it short but please explore as much as you can.

[^3]: You can read more about .Rprofile [here](https://csgillespie.github.io/efficientR/3-3-r-startup.html#r-startup) from [Efficient R Programming](https://csgillespie.github.io/efficientR/) by Colin Gillespie and Robin Lovelace]

