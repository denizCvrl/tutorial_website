---
date: "2019-02-11T19:27:37+10:00"
draft: false
title: Lesson 10 - Netlify
weight: 11
---

So, how to deploy a website once you’re ready to go? Well, you can just use Netlify OR go pro with the Trio of Netlify, Git, and GitHub.
 Let's start with the easy one, but the trio does come with its benefits!

### Deployment of your website: Just Netlify VS the Trio of Netlify, Git, GitHub  

Now that you have an idea how to create a website using blogdown, we can talk about how to deploy it. 
You have many options, but we will follow the suggestions of the blogdown manual and use [Netlify](<https://www.netlify.com/>). Netlify takes the files you created and hosts them. 

Depending on your needs and your future plans, you can follow one of two options.

__1. Just Netlify:__ If you do not plan to update your website frequently, and if you are sure that you will not need Git or GitHub ever in your life, then this is the option for you. Follow the steps below.

   - Create a Netlify account
   - Restart your R session, and run `blogdown::serve_site()` from your website project[^1]
   - Drag and drop the `public` folder into the section Netlify suggests  
   - Whenever you update your website, repeat the last two steps  

  <p align="center">
  <img src="/img/25_deploy1.png">
  </p>

When you first drag and drop your website, Netlify will assign you a random subdomain, something like `SUBDOMAIN.netlify.com`. You can change SUBDOMAIN as you wish, as long as the domain you want is available. 
    
If you do not want a `*.netlify.com` domain, you can purchase a domain name online. There are various websites to buy from. I recommend that you simply Google it to find some options.   
    
Another option is to request a `*.rbind.io` domain name from <https://GitHub.com/rbind/support/issues>. Open a new issue and ask for a domain name you want. (See closed cases for examples.)

  <p align="center">
  <img src="/img/25_deploy2.png">
  </p>

If you go with a `*.rbind.io` domain name, it is better to redirect HTTP traffic to HTTPS. If you don't know the difference, go ahead and read about it from [the wikipedia](https://en.wikipedia.org/wiki/HTTPS). That's what I did! :smile: For example, let's assume your website address is `coolweb.rbind.io`. When you request this address, The rbind team assigns you both `http://coolweb.rbind.io` and `https://coolweb.rbind.io`. The TLS certificate (having that `s` in the http) is obtained via Cloudware. Now you have three addresses: the one with the netlify, another with http and one other with https. Simply create a file called `_redirect` and save under the `static/` folder. Redirect all of the urls to the one with https. See this [blog](https://yihui.org/en/2017/11/301-redirect/) from [Yihui Xie](https://yihui.org/) for examples. 

__2. Using Git and GitHub, and then Netlify:__ If you are hoping to update your website frequently, it is better to host it on GitHub and tell Netlify to pull your website info from GitHub. For this option, you need to choose "New site from Git" (See the figure above). This option will be explained in detail after you learn how to use Git and GitHub in the next lessons. 

Do you have no idea what Git and GitHub are? No worries! Here is a short introduction:
      
Git is a distributed version control system. What does this mean in the context of making a website (or in any context)? Assume that you made some changes in your website at 3am and thought to yourself, "This is perfect". But the next morning you hated all of the changes you made. It happens! If you use Git, you can just tell Git to go back to the version you had before your changes. Otherwise, you have to remember each and every single line you changed one-by-one.
    
Git creates a LOCAL repository. In other words, it tracks changes in your computer. In order to use Git, you need to install it. The next lesson will give you some basic instructions for installation. 
    
You can also create a REMOTE repository via GitHub.
      
GitHub is a platform to host projects online so that people can work together. Its system is setup such that any contributor can make changes to a project. Then, it is up to the owner of the project whether to accept or reject these changes. It was designed for software developers to allow them to share their codes, while at the same time use version control, i.e. Git. You might be thinking: Why not use Dropbox or simply send files via email instead of learning these programs? Well, if there are more than two people involved in a project, it becomes impossible to track down who sent what or who did what. Git and GitHub keep track of all the changes and who made them, show you the conflicts that arise, etc.
    
Here is how we use Git and GitHub for our websites. We will track the changes using Git, and then tell Git to send your updated files to GitHub. From there, Netlify will automatically receive the information to update your website. You do not need to drag and drop the `public` folder anywhere. In fact, you do not need the `public` folder at all. I highly suggest learning Git and GitHub, especially if you are a new graduate student. You might think that it is unnecessary at this point, but I am sure that it won't be a waste of time - trust me! You will need some practice though. For the first timer, it might be frustrating, what’s worth learning that isn’t? The next lesson will focus on how to set up Git and GitHub and use it to host your website.


[^1]: You might need other functions such as `blogdown::build_site()` or `blogdown::hugo_build` if you decide to host your website somewhere other than Netlify.  

