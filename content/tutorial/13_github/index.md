---
date: "2019-02-11T19:27:37+10:00"
draft: false
title: Lesson 13 - GitHub
weight: 14
---

The other option in Netlify is "New site from Git". As explained before, Git creates a LOCAL repository. In this lesson, you will create a REMOTE repository via Github. Netlify updates and compiles your source files from Github and builds your website automatically. No need of dragging and dropping the public folder :smirk:.   

  <p align="center">
  <img src="/img/27_deploy21.png">
  </p>

### GITHUB

* If you don’t have a GitHub account, create one on <https://github.com/>. Don’t forget to use the same email address you had in your git configuration.

* Create a new repository

  <p align="center">
  <img src="/img/27_deploy22.png">
  </p>

* Give a name to your repository. It doesn’t have to be the same name as your project’s. Leave all the other options empty and click "Create repository". 

  <p align="center">
  <img src="/img/27_deploy23.png">
  </p>
  
* The new page will give you several options. You already have a LOCAL repository for your website in your computer. Therefore, you will __PUSH__ your local repository to Github to create a REMOTE repository: “push an existing repository from the command line”. 

  <p align="center">
  <img src="/img/27_deploy24.png">
  </p>

* Back in RStudio, go to `Tools -> Terminal -> New Terminal` (this is another way to operate with codes if you remember; see Lesson 11 if you forgot) and copy-and-paste the two lines under “…push an existing repository…”

  <p align="center">
  <img src="/img/27_deploy25.png">
  </p>
* Enter your Github user name. Then it will ask "Password for 'https://github.com':". Enter your password. Note that you will not see what you write while entering your password.

* If you have zero time to waste (I mean, who does??) and don’t want to enter your name and password each time, check how you connect github with SSH from [here](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh).

* If everything is correct, you will have some notes that your local repository is added to your GitHub account, something similar to below. (I forgot to record the one for COOLWeb, so I took the screenshot of the website you are using right now while I was uploading it.)

  <p align="center">
  <img src="/img/27_deploy25b.png">
  </p>

* Your REMOTE repository is ready to use. 

  <p align="center">
  <img src="/img/27_deploy26.png">
  </p>
  
### Deployment of your website with The Trio of Netlify, Git, Github


* You can go ahead and click "New site from Git" on Netlify. Connect to GitHub and pick a repository.

  <p align="center">
  <img src="/img/27_deploy27.png">
  </p>

* I thought that I had to enter the website address in the baseurl parameter in config.toml. There was no need for that with Netlify! Fine by me :smiley:.

* Follow the steps and DEPLOY! If you want a custom name, you can take one from online and enter it as instructed. If you go with a `*.rbind.io` domain name, follow the steps in [Lesson 10](/tutorial/10_netlify) to redirect all of the urls you have to the one with https.

### Updating your website

* Whenever you make a change to your website, Git will show you the updated and/or new files.
* You need to commit these changes to your LOCAL repository as you learned in the previous lesson.
* There is one more step to see your changes in your REMOTE repository: You have to PUSH them to GitHub. 
  - There is a PUSH option under Git tab in RStudio. All you need to do is click it. If you didn’t set up the automatic connection with ssh, you will also need to enter your credentials for GitHub.   
  - Of course, there is also a way to do this using Shell, and Git has many more commands. I hope you take your time and learn more from other resources. 

### Hugo!

It is wise to tell Netlify which version of Hugo you are using while compiling your files. One way to notify Netlify is to create __netlify.toml__ file in the main directory. You can use `blogdown:: hugo_version()` command to check which version you have.    

  <p align="center">
  <img src="/img/27_deploy28.png">
  </p>

### That’s all! Hope that you have a website now and you can go out to celebrate :tada:. 

  <p align="center">
    <img src="https://media.giphy.com/media/DbIKDy2Pb1d4c/source.gif">
  </p>

  <p align="center">
  <b>THE END</b>
  </p>

