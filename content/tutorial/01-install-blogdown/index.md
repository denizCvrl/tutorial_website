---
date: "2019-02-11T19:27:37+10:00"
title: "Lesson 1 - Install Blogdown"
weight: 2
---

You need both R and RStudio IDE. R is a programming language for statistical computing and graphics while R Studio is an integrated development environment (IDE) that provides a user-friendly platform.  

### Packages and Functions in R

Install R first (<http://www.r-project.org/>) and then RStudio (<http://www.rstudio.com/>).

For R, go to its website and click on [download R](https://cran.r-project.org/mirrors.html), you will see a list of countries with many links. As instructed, choose a location close to you and follow the directions for your operating system. (Or you can also find a YouTube video that demonstrates the installation process. It depends on your operating system so I am leaving you to find one). 

For RStudio, [download](https://rstudio.com/products/rstudio/download/) Free Desktop version and again follow the steps for your operating system.[^1]  

If you already have those programs installed, I am assuming that they are up-to-date, otherwise you might have some problems below.[^2]  

When you are all set, open RStudio. If this is the first time ever you are using RStudio: when you click on RStudio icon, you’ll see the 3 panels depicted below. 

![](/img/1_intro.gif)

Write the code below to your Console and hit enter to see what your current wd (_WORKING DIRECTORY_) is.

```r 
getwd()
```
This means if you create a file and save it, it will be saved to this working directory. We can easily change whatever that directory is but let’s keep it as it is for now and go back to building our website with the blogdown package.[^3]

### What’s Blogdown? 

R has built-in and user-written functions. For example, __getwd()__ is a function that asks R to give current directory information. When a group of functions are bundled together, they are called a __package__. Blogdown is one of these packages and it makes it much easier to prepare a website. Let’s first learn how to install a package. 

### Installation of a package: Blogdown (Section 1.1 in the manual)

There are two ways to install a package:

1. install.packages("<the package’s name>"): type this code to the console with the package name you want, in our case __blogdown__. This function takes the package from its source on the web and installs it to your computer (it’s enough to do this just once on a single computer or device).

```r 
install.packages("blogdown") 
```

2. The alternative way is to go to __packages__, choose __install__, type the name of the package and click install! 

![](/img/2_blogdown.gif)

### Libraries

The package is installed to your computer but you also need to __call__ it to your session. In other words, you need to activate the package so it can be used in this session. While the installation of a package needs to be done just once on a single computer or device, calling packages to your session has to be done whenever you open a new session.

I like to think that each package consists of a team of minions who are resting in my computer, waiting to be called to action. Each team is in charge of performing certain tasks. Installing packages adds new teams of minions to my computer (yay!), and calling packages lets the minions know which teams will be working on today’s projects. Since packages have be to called for each R session, we always start new sessions by letting our minions know to get ready to go to work!  

<p align="center">
<img src="https://media.giphy.com/media/6NOQuy1P6vF4s/giphy.gif">
</p>

Now, let’s call our installed blogdown package so we can use it in this project. The command to load a package to your session is __library()__. For the blogdown package:

```r 
library(blogdown)
```

Write this to your console and hit the enter. Your team is ready to work!

<p align="center">
<img src="https://media.giphy.com/media/10S4rk0J10AKlO/source.gif">
</p>

Now that you have the package in your computer, and you have called it to your session, you can deploy any function (minion :smile:) from __the blogdown package__. It is like asking one of the minions in the team to do a certain task. 

One of these functions is __install_hugo()__. Who is HUGO? What is HUGO?

Hugo is a static site generator. Althought it’s not a perfect analogy, building a website in R is kind of like making a cake: you mix eggs, flour, milk, and baking soda, then bake it in the oven. Hugo is like the oven. You create your content and pick a template, and Hugo renders (bakes!) them into an html website. You don't even need to code in html! Of course you are responsible for your content but fortunately for us, some super nice people have created website templates that you can use for free. Here are selections: <https://themes.gohugo.io/>. In order to use these templates, we need to install Hugo. The blogdown package has a function called __install_hugo__.[^4]

```r 
blogdown::install_hugo()
```

If you are a keen observer, you may be wondering why we have the package name, __blogdown::__, in front of our function name? This is just a way to tell R __where__ to look for the install_hugo() function. Including the package name before the function is not always necessary, and you will likely not want to write this out every time you use a function, but there are a couple of reasons to do so:

- Although we already loaded the blogdown package with  __library()__, we need to be careful when using functions from this package. There might be functions with the same names from different packages (like minions with the same names from different teams). For example, assume that there is another package called Postdown with a function called install_hugo. If you load both packages, it could result in unexpected (and aggravating) errors. In that case, it is safer to indicate the package name in front so that R knows which one you inted to use. 

- You can skip loading the blogdown package with __library()__ altogether when you write the package name in front of a function. This is the case in [the blogdown manual](https://bookdown.org/yihui/blogdown/). It doesn’t mention using library() at all so that __blogdown::__ accompanies each function mentioned in the manual. When you analyze a dataset, you use multiple functions from multiple packages. In that case, it is not practical to write package name for every single function. In this tutorial, we will skip loading the blogdown package using __library()__ like the manual and use __blogdown::__ in front of each function. 

Well, I hope this was a helpful explanation of the installation and usage of packages and functions in R :stuck_out_tongue_winking_eye:.

Installation? DONE! Now, let’s move forward with building our website!

[^1]: If you want to read more about installing R and RStudio, see 
<https://www.r-bloggers.com/how-to-install-r-and-rstudio/>.

[^2]:Since you have the programs I assume you know how to install packages so you can follow [these instructions](https://uvastatlab.github.io/phdplus/installR.html#updateR) to update your programs. If you don’t know what "package" means then it is better to uninstall everything and update to the latest versions. 

[^3]: You can manually set your working directory using __setwd("a path on your computer")__. However, it is not a very popular function. I will comment more on that later, but if you are curious and are already somewhat familiar with R, I suggest [this famous post](https://www.tidyverse.org/articles/2017/12/workflow-vs-script/) by [Jenny Bryan](https://jennybryan.org/). For future reference, I also suggest [this blog post](https://kdestasio.github.io/post/r_best_practices/) by [Krista L. Destasio](https://kdestasio.github.io/) about best practices with R. You will discover the practices that work best for you as you gain more experience with R. 

[^4]: There are other static site generators like Jekyll with different templates but they are not compatible with blogdown. There are ways to solve the compatibility problem but, if you are a beginner, it's better to keep it simple! :smile:

