---
date: "2019-02-11T19:27:37+10:00"
draft: false
title: Lesson 4 - Themes, Colors, Fonts
weight: 5
---

In the academic theme, you have the flexibility of creating your own color and font theme. Follow along to learn more. __params.toml__ is like your make-up kit, but instead of blush and mascara, you have theme, color, font, fontsize, etc.:smile: 

### Params.toml

The very first part of __params.toml__ sets some basic keys. In the code below, for example, I used dark as a theme and minimal as a font with font size L. 

![](/img/6_params.png)

There is also day/night mode. Try it does by clicking moon icon from the menu on the example website. (Update: You might have palette instead of moon.) 

<p align="center">
<img src="/img/6_daynight.png">
</p>

What is dark theme? Minimal font? Where are they coming from? There are some built-in themes stored in `themes/hugo-academic/data/themes/` and fonts in `themes/hugo-academic/data/fonts/`. The figure below shows the location of the folders. Remember that you are not supposed to change anything in this folder!!!

![](/img/6_theme_font.png)


You might notice that there are two `themes` in the first folder path, which might seem confusing. The first `themes` refers to the main theme we are using for the website: section, menu, etc. Our main theme is hugo-academic. The second `themes` in the path is for a theme within the hugo-academic theme. You will find the codes of built-in themes and fonts in these folders. You can see what they look like here: <https://sourcethemes.com/academic/themes/>. You can open one file from each folder to see what parameters are needed to create a theme and a font.

For example, we have __dark.toml__ file open in the figure below for the dark theme. All of those codes are for colors based on [html colors](https://htmlcolorcodes.com/). I am leaving it to you to google what color #fff is!

<p align="center">
<img src="/img/7_colors.png">
</p>

If you like one of the built-in themes, but want to simple touches like font or font-size, you can make many of these changes within __params.toml__, again from built-in options. Follow the instructions in __params.toml__. 

But what if you didn’t like any of the built-in themes? Or maybe you want a font that is not available in the hugo-academic theme? No worries, you can make a custom  theme or font if you do not mind a little bit of coding. Let’s walk through this process.(It is also nicely explained here: <https://sourcethemes.com/academic/docs/customization/#custom-theme>.)

It has three steps:

1. Creating a path: This is VERY, VERY important. If you want to change anything in the hugo-academic theme (or in any other theme), you should __NOT__ make changes in the original folders, i.e. `themes/hugo-academic/data/themes/` or `themes/hugo-academic/data/fonts/`. You need to create new folders at the root of your directory (for me this is my COOLWeb folder), called `data/themes/` for color themes and `data/fonts/` for fonts. You can create these files by using New Folder option under Files. See the image below. Once again, pay attention to the path!  


![](/img/8_custom_1.png)


2. Creating custom theme or font:  

- Themes: Copy the file of one of the built-in themes. Save it under `data/themes/` (avoid using spaces in filenames). Create your custom theme by deciding your colors from [html colors](https://htmlcolorcodes.com/) and entering their codes to the parameters.      

- Fonts: Create your custom font by following the steps at the webpage <https://sourcethemes.com/academic/docs/customization/#custom-theme>. Save it under `data/fonts/`  (avoid using spaces in filenames).

3. Tell your website to use your custom theme and/or font by setting theme and font parameters in `config/_default/params.toml`. (See the figure, I named my custom theme and font: denizcolor and denizfont). For this tutorial, I kept the built-in themes `dark` and `minimal` but I hope that this brief instruction gives you a basic outline for customization of website aesthetics. If this is too much coding, just go with one of the built-in options :grinning:.    

<p align="center">
<img src="/img/8_custom_3.png">
</p>

This was the THEME section of __`config/_default/params.toml`__.

<p align="center">
<img src="https://media.giphy.com/media/Ih7KOdwUzPACW8Njzu/giphy.gif">
</p>

The rest of __params.toml__ sets other parameters for the website. Let’s look at each section one by one.

__- Basic Info:__

<p align="center">
<img src="/img/9_basicinfo.png">
</p>

I changed only the description. If you are preparing this website for an organization or a lab, make the necessary changes. 

Notice that your name appears on the left upper corner of the website. If you would like to have a logo instead of your name, go ahead and save your logo in `static/img/` and refer the file in the logo option. You don’t need to write the whole path, just logo = "logo.png". (Update: I think there is some changes about logo in the new version. Follow the instruction in the new version.)

__- Site Features:__

<p align="center">
<img src="/img/10_sitefeatures.png">
</p>

If you plan to share some programming code, including R code, in your website, you can decide how they appear by editing highlight_languages and highlight_style. This will enable the website to present programming code with text highlighting that distinguishes different parts of the code from one another. As it states in the __params.toml__ document, be sure to check the availability from <https://cdnjs.com/libraries/highlight.js/>. For example, I added tex file, because I am planning to share some Latex code. You can find a demo of each supported style here: <https://highlightjs.org/static/demo/>. I chose "vs" for this tutorial.

If you would like to share some math formulas, equations or diagrams, you should tell R to render those kinds of code. You do not have to enable it for the whole website though. Later on, you will have front matters for other pages of your website. For example, if you remember from the previous lessons, `content/courses` created another page and you can enable math and diagram just for that page. If sharing math and diagram is not in your plans, then no worries :wink:.

Another key in the __params.toml__ under Site Features is privacy_pack. It warns users about the use of cookies on your website when they visit your website for the first time. If they chose "I got it", they never see that message again because the website remembers them! In order to better explain the function of privacy_pack, I have to jump towards the end of __params.toml__ and talk a little bit about Comments and Marketing sections before the next section, Contacts Details. By the way I don’t know how edit_page works for now, so I simply disable it :smile:. 

<p align="center">
<img src="/img/10_param_comments.png">
</p>

__- Comments:__
  
This is a static website so it doesn’t change in response to user actions. If you want your webpage visitors to comment, there is an external resources! You can use websites like [Disqus](https://disqus.com) or [Commento](https://commento.io/). You need to create an account and enter its credential in this section in order to use these external resources. However, there external resources use cookies. There are good and bad sides of cookies. You can learn more about it [here](https://www.cookiesandyou.com/about-cookies/). I think you also need to warn your visitors legally according to [The General Data Protection Regulation (GDPR)](https://en.wikipedia.org/wiki/General_Data_Protection_Regulation) if there are cookies. Being on the right side, it is better to set privacy_pack true. 

__- Marketing:__
  
This section is at the end of __params_toml__. If you would like to track your website traffic, you need to get an account and enter your credentials here. The other function of privacy_pack is to anonymize IP in Google Analytics (if enabled).    

Let’s go back to the normal order: Contact Details!

<p align="center">
<img src="/img/10_param_contact.png">
</p>

__Contact Details:__

See the note for this section: These details power the Contact widget (if enabled). It appears towards the end of the homepage. I will show you how to move it to another page other than homepage later. It doesn’t matter where you show that widget, the information used comes from this section of __param.toml__. You can disable any of them by putting # in front of the respective line.

Some more information about contact links options: I couldn’t figure out where they are exactly (somewhere in the hugo-academic file, perhaps), but apparently there are four types of packs: fab, fas, far and ai. They have lots of icons. You can find what is available from <https://sourcethemes.com/academic/zh/docs/page-builder/#icons> if you would like to use something else that is not illustrated in the example website.

__- Social:__

Don’t confuse this with the photo of your website. This photo is for your interactions in the social media and other websites when somebody shares your website. As instructed, save your avatar file, the photo you want to use on the homepage, under `static/img`. If you add your twitter account, whenever your site is shared on Twitter, your twitter account is also attached to the tweet :wink:.  

__- Regional Settings:__

This part is for regional settings about date and time. Change it accordingly.

__- Advanced:__

I like it when the menu is on the right, so I changed that in the “Main menu alignment” section.

There is also show_logo option here. Remember your name or logo, appearing on the left upper corner? It is the link to go back to homepage if a visitor is in another page of your website. If you don’t want it, then show_logo = false. In that case, I think it is better to have Home option in the menu. Its url should be the first WIDGET you have on your homepage. Once again, more about WIDGETS: Coming soon!

If you know javascript or css, you can make some changes to the appearance of your website in this section using plugins_js and plugins_css, but it is not a topic of this tutorial. If you do make changes with these plugins, however, note that the logic is the same with the custom theme and font. Do NOT make changes in the original folders, i.e. `themes/hugo-academic/assets/css/` or `themes/hugo-academic/assets/js/`. You need to create new folders at the root of your side, called `assets/css/` for custom css files and `assets/js/` for custom js files. 

You can also decide how your publications and projects appear here. Once you understand the WIDGETS, you can come back and change these options.

__- Search:__
  
I kept everything as it is. Visitors will be able to search your website for keywords.

__- Maps:__
  
I personally prefer no map option, engine = 0. Notice that the address information here domes from the Contact Details section.  

NEXT LESSON: Finally, Widgets :eyes: and how to change content.
