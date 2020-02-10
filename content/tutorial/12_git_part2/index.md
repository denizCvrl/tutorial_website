---
date: "2019-02-11T19:27:37+10:00"
draft: false
title: Lesson 12 - Git Part II
weight: 13
---

Although you learned how to open a shell window using Git Bash, you haven't done anything related to Git yet. In this lesson, you will create a LOCAL repository with Git.

### Git Part II

Open a terminal (MacOS) or a “Git Bash” shell (Windows).

* Let's start with learning which Git version you are using by typing

   ``` bash
    git --version
   ``` 

   It is good to know which version you have in your computer. 
    
   Git needs to know who is using the program. In order to introduce yourself to Git, there are two commands: 

  ```bash 
   git config --global user.name "YOUR FULL NAME"
   git config --global user.email "YOUR EMAIL ADDRESS"
  ```
   The email address must be the one associated with your GitHub account. If you already have a GitHub account, use the same email address you have there . If you don’t, use the same address you have here when you create one. (You will create one in the next lesson. Feel free to create one now if you want :wink:.)
   
  Check if your set-up is correct by typing:  

  ```bash 
     git config --global --list
  ```

   Don't panic over all of the things listed there. Just look at the last two lines!

   If you need more instructions, [here](https://www.youtube.com/watch?v=yDntCIs-IJM&list=PL6gx4Cwl9DGAKWClAD_iKpNC0bGHxGhcx&index=2) is the video I followed when I first set up my account.
   
* In the next step, we ask GIT to initiate a __LOCAL__ repository for your website project. You can either run `git init` in a SHELL, then restart RStudio and reopen your project 

  OR

  follow the steps shown below: 

  <p align="center">
  <img src="/img/26_deploy12.gif">
  </p>

  You will notice three changes (see the image below): 
     
  1. Git Pane 
     
  2. Git Dropdown 
     
  3. .gitignore file. 

  <p align="center">
  <img src="/img/26_deploy13.png">
  </p>

1. __Git Pane:__ You will see the list of files/folders in your project here. When you hover your cursor over yellow question marks under Status, <img src="/img/git-untracked.png" width="25px" height="25px">, it says "untracked/untracked". It means that Git hasn't seen that file/folder before. 

  + Since Git hasn't started to track any file yet in our project, all of them have <img src="/img/git-untracked.png" width="25px" height="25px">.
      
  + Tracking starts with a __Commit__, which takes a snapshot of your content at a specific point in time, allowing you to go back to that point if necessary. It is probably not efficient to commit every single change, so you will be the judge of which ones are crucial. You might think it is safe to record every single step, but it might be hard to find what you are looking for later and you might regret of so many unnecessary commits.
    
      <p align="center">
      <img src="https://media.giphy.com/media/OWJILXs8QpyiA/giphy.gif">
      </p>

  + Open the Commit Window by clicking <img src="/img/git-commit.png" width="70px" height="70px"> or by pressing Ctrl + Alt + M (see the image below). Commits have two steps:
      
       - Staging (Selecting): Simply check its box if you want to commit a file. Once you stage an untracked file, Git understands that you want to __ADD__ this file to the repository, so the status turns to <img src="/img/git-add.png" width="25px" height="25px">. For example, I chose `config.toml` to commit in the figure below and the staged status is now <img src="/img/git-add.png" width="25px" height="25px">.   

      - Commiting: After staging, you should write a commit note that describes why you have this commit and then click commit. The file disappears from the list once you start tracking.  
                  
        <p align="center">
        <img src="/img/26_deploy14.png">
        </p>
  
  + I decided to change the title of my website from Deniz Civril to Deniz Civril Civril. config.toml reappears and Git shows that the contents of the file have changed with __Modified__ symbol, <img src="/img/git-modified.png" width="20px" height="20px">. There are two columns under __Status__. The right one is for unstaged status and the left for staged status. <img src="/img/git-modified.png" width="20px" height="20px"> is on the right side as an unstaged status. If you check its Staged box, the __Modified__ symbol shifts from right to left. Try it yourself!
     
  + Open the Commit Window by clicking <img src="/img/git-commit.png" width="70px" height="70px"> or clicking <img src="/img/git-diff.png" width="45px" height="45px">, where "diff" refers to difference, I assume! Different ways, same destination! 
        
    <p align="center">
    <img src="/img/26_deploy15.png">
    </p>
    
  + The lower section of the Commit Window shows what you have changed in your document. Let’s review a couple of options you have before you actually commit your changes:
      
    - BEFORE you commit, you go over your modifications and decide to undo ALL of the changes you have done. Either select “revert” from the Commit Window OR right click on the file in the Git pane and select “revert”. This will return the version of the file in the previous commit.
        
    - BEFORE you commit, you go over your modifications and decide that you are not happy with some of the changes, not all. Use <img src="/img/git-chunk.png" width="120px" height="120px"> to discard changes in certain parts of your document. You can even undo lines by clicking on them.  

  + Are you satisfied with your changes? Then write a commit note and click commit. 
  
    - You can rewrite the commit history by clicking "Amend previous comment". I do not recommend it, especially if your commit includes multiple files. It is also not recommended when you work with others on the same project!
  
      <p align="center">
      <img src="/img/26_deploy16.png">
      </p>
        
  + Most of the time, you commit multiple files at the same time. For example, I decided to change my title to "Deniz Civril Civril Civril" and also start to track the config folder. I staged modified config.toml and config folder, and committed both of them at the same time. Then, you can see each file separately in the history section.  
      
      <p align="center">
      <img src="/img/26_deploy17.png">
      </p>
      
  + "Deniz Civril Civril Civril"? What was I thinking? But I already committed the change!? This is an easy mistake to change without a control version, but in reality we usually have complicated codes, long blog posts, etc. with many modifications.  
        
     - So, you have to go back in time and decide which version of your file to be restored. The easiest way to restore an entire file is to choose "View File" as shown below and use "Save as" to save the file in place  of the current version. Or you can copy-and-paste the part you want.     

        <p align="center">
        <img src="/img/26_deploy18.png">
        </p>

     - Another way is to use Shell. Notice that each commit has a unique SHA (secure hash algorithm).
        
       * In order to see what you have changed, you can use the code below. You need the file name rather than just a SHA because one commit can have multiple files.
       
         ```bash 
            git show <SHA> <filename>
          ```        
       * In order to copy the version you want directly, you can use:
        
        ```bash
          git checkout <SHA> <filename>
        ```
        
  - After finding the version you want and saving it, continue with staging and committing steps.
  
2. __Git Dropdown:__ Git Dropdown is a short-cut access for the active file. For instance, config.toml is active below and Git Dropdown lists some options we discussed above for this file. 

  <p align="center">
  <img src="/img/26_deploy19.png">
  </p>

3. __.gitignore file:__ There will be some files that you simply do not want to track. You can tell Git to ignore those files. Just right-click on the file in the Git pane and select Ignore! Git adds the file to the list in the .gitignore file.

    * Note: For example, the public folder doesn't need a version control. It is recreated every time you use blogdown::serve_site. Right-click the public folder and ignore it. 

    
    <p align="center">
    <img src="/img/26_deploy21.png">
    </p>

### Tips:

When you commit a large number of files, the program crashes. At least, that was the case for me when I tried to stage all the files for my COOLWeb project. It just freezes and doesn't let you tick the boxes. If that's the case for you, force the program to end from the task manager (Ctrl+Alt+Delete) and restart.  

A quick online search gave me [a solution](https://community.rstudio.com/t/blogdown-unable-to-stage-and-commit/6621). It is better to use Shell for the initial commit that is bringing all of the files under version control. I typed:

  ```bash 
   git add -A
  ```
Instead of -A, you can also write -all. As you can probably assume, this command stages all of the files. However, it gave me an error with a suggestion of deleting the "index.lock" file under .git folder. Apparently, when I tried to stage my files via RStudio, it created this file, which still continues to be active. Anyways, if you have the same problem, you can find the .git folder inside your project folder. If your computer doesn't show hidden files, then you might not be able to see the .git folder. Please find out how you can see hidden files in your operating system (just google it, you will find it!).  

After deleting the mentioned index.lock file and running the `git add -A` command again from the shell, I was able to stage all of the files. I then completed the committing process from the Git Pane.


  <p align="center">
  <img src="/img/26_deploy20.png">
  </p>

You can also complete committing from the Shell, but, at that point, this tutorial starts to turn into a GIT tutorial. Therefore, I am leaving it to you to learn those commands.

By the way, you can use version control for any project. Instead of saving different versions of your documents each time, Git keeps track of everything for you. I also suggest using it with the Netlify deployment option (the one without GITHUB) if you want to keep different versions of your files in your website project.   

NEXT: GITHUB!
  
