---
date: "2019-02-11T19:27:37+10:00"
draft: false
title: Lesson 9 - Some Hints
weight: 10
---

This lesson will include an ongoing list of small changes I make to my website over time. I am hoping to add to this section as I go along. And if you discover any tips/tricks that might be helpful for others, please let me know and I can add them to this section! 

### Keeping up with the updates

If you are using the academic theme, you might want to track and keep up with the updates from <https://sourcethemes.com/academic/updates/v4.7.0/>. This can be helpful for a few reasons.

For example, if you need to update the version of Hugo, it can create compatibility issues. These issues are resolved in the newer versions of the academic theme, but might require some patch codes for the old version. 

In my case, for example, I had the BlackFriday setting. See the updates under “Breaking Changes” on <https://sourcethemes.com/academic/updates/v4.7.0/>. I followed the instructions to be able to use Hugo versions higher than 0.60.0.

Don’t panic. You will notice if something is wrong and it's very likely that somebody has already solved the problem :wink:.  

### Changing the website icon

If you notice, the academic theme's icon appears in web browser tab (see the image below). You can use your own icon but you need to save it in `assets/images/`.

![](/img/24_icon.png)


Please follow the instruction in <https://sourcethemes.com/academic/docs/customization/#website-icon>.

### Centering text in the widgets

You may want to center the text that appears in widgets on your website. Below is the trick to getting this done!

```r
[advanced]
 # Custom CSS. 
 css_style = "text-align: center"
```

### Changing the text in the footer

The academic theme has a lot of options, which means there are a lot of code files. 
`themes/hugo-academic/layouts/partials`, for example, has some of the codes related to the design of the website. 
 
Although it requires some html knowledge, I want to show you an example of how to change simple things. If you open site_footer.html, you will see that it is the code that takes the copyright information you initially entered in config.toml in the beginning of this tutorial. You can change the text here if you want. 

But, remember not to edit anything in `themes/hugo`!!! You should copy the file to the folder you created in the root - `layouts/partials/site_footer.html` - and make the desired changes to the copied file.

<p align="center">
<img src="/img/24_site_footer.png">
</p>

If you know html coding, or if you have somebody who can help you with it, you can modify the codes as you wish. For example, you can modify the appearance of the navigation bar from navbar.html.

### Other themes

- Most of the other themes are simpler than the academic theme. For example, their config.toml usually has all the necessary parameters needed to set the file, which means that there is no need for extra toml files such as menu.toml or params.toml. Similarly, other themes often do not require multiple files to create the homepage. Instead of the home folder, there may simply be an index file inside the content folder. 

- When you first create a website (Lesson 2), it is better to choose “add sample blog posts” and “add the example site of the theme” from the New Project Window. 

- You may see a warning in the console when you first create a website with another theme (see below). Copy-and-paste the ignoreFiles part to your config.toml. The config.toml of the example website for the academic theme already has this correction so we didn’t discuss it before. 

```r
  You are recommended to ignore certain files, set the option 
  ignoreFiles = ["\\.Rmd$", "\\.Rmarkdown$", "_files$", "_cache$"]
```


- If you cannot see the images, it is probably related to the paths. Look at the example website of each theme to be sure that you are writing it correctly. For example, in the academic theme, we didn't need to write the full path for the image files in the static folder. This might not be the case for the other themes.

