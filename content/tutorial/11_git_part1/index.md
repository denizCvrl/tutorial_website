---
date: "2019-02-11T19:27:37+10:00"
draft: false
title: Lesson 11 - Git Part I
weight: 12
---

Ready for a crash course for Git and GitHub? Full disclosure: This is actually the first time I am using either of these myself. If any part of this instruction is confusing or seems incorrect, please refer to the sources, but I will do the best I can!

### Git Part I

For this section, I am basically following [Jenny Bryan](https://jennybryan.org/) and [Jim Hester](https://www.jimhester.com/)’s [Happy Git and GitHub for the useR](https://happygitwithr.com/) and [Hadley Wickham](http://hadley.nz/)’s [Git and GitHub instructions from R Packages](http://r-pkgs.had.co.nz/git.html#git-init). 

Let’s kick things off:       

- Start by installing Git from <https://git-scm.com/downloads>. Follow the directions for your operating system. Don’t forget to pay attention if you have a 64-bit or a 32-bit processor.

- There is this thing called "Shell" on computer operating systems. When you use it as a non-programmer person, you feel like you are a badass hacker. Woohoo, :satisfied:! A shell is a command-line interface (CLI - just for your information, the other interface is graphical user interface, or GUI), which helps you interact with your computer with commands. Your operating system interprets those commands and performs what you ask the computer to do.    

   + There are multiple ways to open a shell window but we will talk about a couple of them under "with" and "without" RStudio titles.   I don’t use MacOS, so if you have any trouble while using a Mac please refer to [Appendix of Happy Git and GitHub for the useR](https://happygitwithr.com/shell.html#shell), but overall the commands are the same. It is enough to use just one of the shell windows, but I would like to show you different options while introducing some commands. 

__Without R studio :__

Maybe you won’t be using Git without RStudio but I think you should learn that Git is not a part of RStudio. You can use it for other projects without RStudio.
  
__MacOS:__ Terminal is the name used for shell on macOS. Open a Spotlight Search by pressing Command + Space. Then type "terminal" and you should see an icon of a black screen (since I am not on MacOS myself, I can’t provide a screenshot – sorry!). Click on it.    

__Windows:__ Once you install Git, you can open a shell window from Git. Go to the "Git" menu on the Windows menu and click "Git Bash". That’s it, you have a shell window open now.

  <p align="center">
  <img src="/img/25_deploy5.png">
  </p>

__With R Studio:__ 

`Tools -> Terminal -> New Terminal` 

  OR

`Tools -> Shell` 

  <p align="center">
  <img src="/img/25_deploy6.png">
  </p>

What’s the difference? The first one launches a shell within RStudio and the latter opens a new window.

  <p align="center">
  <img src="/img/25_deploy7.png">
  </p>

To be honest, I have no idea if there are things you can do with one shell window, but not the other. I guess it is just a matter of preference. 

Let’s learn some commands and see what they do. In the figure below, you see two shell windows I opened side by side: one from RStudio (RStudio Shell, `Tools -> Shell`), and the other from the Windows menu (Windows shell). (By the way, please feel free to try these commands in a shell launched within RStudio, `Tools -> Terminal -> New Terminal` as well.) 

  <p align="center">
  <img src="/img/25_deploy8.png">
  </p>

Notice that the directory, i.e. the folder the shell refers to, of Windows shell is different from the directory of RStudio shell. You can understand it from the titles of windows. You can also understand it by using a command, your first command:

- `pwd`: print working directory (funny, I always thought that it was present working directory)

 <p align="center">
<img src="/img/25_deploy9.png">
</p>

Windows shell has `Documents` as a directory. Since I opened RStudio shell from my COOLWeb project, COOLWeb folder was assigned as a working directory. Here is your second command to change assigned directories: 

- `cd`: change directory 

I will change the working directory of Windows shell by typing `cd /c/Users/DC/Documents/COOLWeb`. You need to write the path you have in your computer. Do you feel like this is a super long path to write? There is a shortcut. I am already in `/c/Users/DC` on Windows shell. Therefore it is enough to write `cd ~/Documents/COOLWeb`.

  <p align="center">
  <img src="/img/26_deploy10.png">
  </p>
  
Let’s be clear. You don’t need to use both shells normally. I am just showing the different options you have. You can just use one or the other. The last command in this lesson:

- `ls`: list files. 

It will show you all of the files COOLWeb folder has.

  <p align="center">
  <img src="/img/26_deploy11.png">
  </p>

I think it is enough for this lesson. You can type `exit` and hit enter to close each window. I hope that this provides you with some very basic familiarity with the shell environment. We have some more shell commands to learn in the next lesson. 

How is it going so far?

  <p align="center">
    <img src="https://media.giphy.com/media/MHTYoP3edbbfW/giphy.gif">
  </p>
