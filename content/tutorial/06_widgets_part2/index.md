---
date: "2019-02-11T19:27:37+10:00"
draft: false
title: Lesson 6 - Widgets Part II
weight: 7
---

More WIDGETS :dart: In this lesson we will cover all the widgets that appear on the homepage of the example webpage. All you need to do is to decide which ones you would like on your own webpage. Then we conclude with how to create a new widget page. 

### about.md

The next widget on the homepage is the __about__ widget. That's the part with the photo and the short biography on the webpage. The code is in __about.md__ in `content/home/`.

Once again, the code that determines the type of widget and the order of appearance is written between two "+++". The widget is active and we have "Biography" as a title. But where is the rest? :worried: Where is the part that includes the photo and the whole text under the title?! :cold_sweat: Don’t worry, it’s not supposed to be here – these parts of __about__ are kept somewhere else, but we can find them!

As you can see from the notes in __about.md__, author = "admin" uses information from `content/authors/`, in which you can find the "admin" folder. You have two files inside `content/authors/admin`: avatar.jpg and \_index.md. And now we have found what we are looking for! \_index.md is for the text part of the __about__ widget and avatar.jpg is for the image. 

For your own website, you need to modify the information in \_index.md and save your own photo as avatar.jpg. Or, if you want, you can create a new folder under `content/authors/`, name it whatever you want, let’s say OWNER. Save your avatar.jpg, copy \_index.md and modify for yourself. Then, write author = "OWNER" in __about.md__ in `content/home/`.

![](/img/13_about.png)

By the way, for those of you who don’t know, Nelson Bighetti is a character known as Big Head in The Silicon Valley of HBO :joy:.

<p align="center">
<img src="https://media.giphy.com/media/3og0IMdYUfEyYOqIZW/giphy.gif">
</p>

Looking again at `content/authors/admin/`, I want to take your attention to the "social" part in \_index.md. The "fab" icon pack appears here again (we mentioned packs in Lesson 4), from which we get the icons and link them to the addresses of our own profiles in various social media websites.  

You migh notice the link for "envelope" is '#contact'. We have exactly the same logic that we had in the menus.toml file. The link goes to __contact.md__ under `content/home/`. Why? Because it has # in front of it. Let’s take a closer look at how contact details are managed. 

### contact.md

Open __contact.md__ which locates at `content/home`. As you can understand from weight = 130, it appears toward the end of our homepage and, in fact, if you check the homepage of the example website, you see the form to send an email and other contact information. Once again, there is almost nothing in the code :confused:.  

<p align="center">
<img src="/img/14_contact.png">
</p>

Remember Contact Details in params.toml (Lesson 4)? "These details power the Contact widget (if enabled)". You can enter your contact information there and, by choosing autolink = true, that information is added to __contact.md__. I know this might seem a bit confusing, but it provides efficient programming and a consistent output. Instead of entering the same information again and again in different locations (making it more difficult to change it all when you update your site), you simply enter the information in one location and call on that information for various sections of the site.  

If you decide to opt-out from being contacted via email, choose 0 in the email_form. The example website uses basic form_spree.io. The other option requires hosting your website via Netlify. We will talk about Netlify later.

### skills.md, experience.md, accomplishments.md

By now, you have probably learned how to read the .md files of widgets in `content/home/`. The next three files as they appear on the homepage are __skills.md__, __experience.md__ and __accomplishments.md__ which use FEATURETTE, EXPERIENCE and ACCOMPLISHMENTS widgets respectively. I think that modifying these widgets is pretty straightforward using the notes in each file, so I am not going over them here. If you do not want to use these widgets, just change _active_ from TRUE to FALSE or delete the .md files. 

### posts.md and talks.md

The next on the webpage is __posts.md__ (once again, you can understand the order from "weight" option), which uses the PAGES widget. Although __talks.md__ appears later on the homepage, it also uses the PAGES widget. Go ahead and open both of those files so we can look at them together. You can drag one of them out of the RStudio window to see them side by side as I did below.   

![](/img/15_pages.png)

The PAGES widget gives you a chance to list some entries you have in other folders on the homepage. You might already have dedicated pages for those folders but it is nice to feature some of the entries on the homepage. 

`page_type` determines which folder it needs to look at under `content`. Accordingly, __posts.md__ and __talks.md__  go to the `content/post/` and `content/talk/` folders, respectively. Other parameters set the number of pages, filtering criteria, and design. For example, you can tag your posts according to their subjects. If you would like to show the posts about a certain topic you have tagged on your homepage, you can use filtering options. Try playing with the design options a bit by changing it from 2 to 1 or 3 and see how it looks :punch:.   

### projects.md

__projects.md__ uses the PORTFOLIO widget which is very similar to the PAGES widget. One additional feature here is the filtering toolbar. When you enter your projects, you can tag them (coming soon!) and use these tags to filter them. The example website shows how these filters can be displayed (see the image below).  

![](/img/16_portfolio.png)

### Gallery Folder!

The next section on the homepage is __Gallery__, but this part is actually hidden under Gallery folder, `content/home/gallery/`. This is another example for the BLANK widget (the other one was in demo.md). If you open index.md under the gallery folder, you will see that it is actually no different than other .md files, with the parameters widget, headless, active, and weight. 

At the bottom, there is the `gallery` element between curly brackets. I was like "What the heck does that mean?" :eyes:. Turns out that this is another built-in html design that is located at `themes/hugo-academic/layouts/shortcodes/`. It takes the photos from the subfolder `content/home/gallery/gallery/` and presents them in this widget. 

Just change _active_ from TRUE to FALSE or delete the folder if you do not want it. If you are preparing this website for a lab, I think it is fun to share some lab photos as a galery on the homepage :satisfied:. 

### featured.md and publications.md 

We already covered __talks.md__, so the next two are __featured.md__ and __publications.md__.

Both have page_type = publication. This means that they receive the information they show from `content/publication/`. However, __featured.md__ shows only "the featured = true in their front matters" (line 4). 

Does that make any sense to you? It didn’t make much sense to me until I saw the codes in `content/publication/`. There are 3 folders in `content/publication/`: conference-paper, journal-article and preprint. Each folder contains the papers you present under "Recent Publications". Notice that each folder also has an index.md file with the parameter "featured". Only the index.md of the conference-paper folder has "featured = true". Therefore, you see only that paper under "Featured Publications" :wink:.  

![](/img/17_publication.png)

One more thing about __publications.md__: Have you noticed the alert note at the end? It states: "Quickly discover relevant content by filtering publications". We had an alert note in demo.md too. Similar to the gallery element, the alert note is also written between two curly brackets. Even though you do not necessarily know coding in html, you can just copy-and-paste the codes, change the content and use in another index.md file :wink:.   

### tags.md

The final two widgets that appear on the homepage are __tags.md__ and __contact.md__ (we already covered contact.md). When you use tags for your posts, talks, and/or publications, you can present them here so people can reach these topics easily using widget = "tag_cloud"! You will learn how to create these tags in the next class. 

Wait! There are two more files in `content/home/`: __slider.md__ and __people.md__. 

### slider.md 

__slider.md__ uses the SLIDER widget but we cannot see it on the homepage because active = false. Make it TRUE. It will appear at the top of your page because weight = 1. It is an animated slider. I think it might be very useful if you have some announcements and want your webpage visitors to see them at the top.

### people.md 

If you are preparing this website for a lab or an organization, you might want to introduce your team members. This is the widget you can use. Once again, make active = true and see how it appears on your example webpage.  

For your homepage, simply decide which widgets you want to use and set your parameters to determine how they are used. Turn “active” from TRUE to FALSE (or delete the files in the `content/home/` folder) and enter your content.

WIDGETS, UNDERSTOOD! HOMEPAGE, DONE! 

### Creating a New Widget Page

Assume that you want to use a widget in a separate page, not on the homepage. All you need to do is to declare that your page will be a widget page in the front matter of an index.md. Let’s try. 

 1. Create a new folder in the `content/` folder: I named mine EXPERIENCE.
 2. Create a new file, `File-> New File -> Text File`, and  save it as `index.md`. Copy(Cut)-and-paste experience.md from the home folder to the EXPERIENCE folder.  
 3. In the index.md file, declare that this page is a widget_page.
 4. Don’t forget to create an item in `menu.toml`.

<p align="center">
<img src="/img/17_widgetpage.png">
</p>

You can create really cool pages with widgets. For example, I used 2 blank widgets (demo.md) below. I deleted all of the text but title: one is titled "Experience" (demo1.md) and the other Accomplishments (demo2.md). I copied and pasted both experience.md and accomplishments.md from the `content/home` folder.

<p align="center">
<img src="/img/17_widgetpage.gif">
</p>

How about widget pages for projects, publications? 

- Similarly, create a separate folder in `content/` with its index.md file which has type = widget_page. 
- Let’s say the name of the this folder is PROJECTWIDGET. Create a link for this folder in the menu.toml.
- Copy(Cut)-and-paste the __projects.md__ file from the home folder. 
- Remember that this file has page_type="project" (see above). It means that it lists the content of `content/project/`. 

In summary, your menu refers to `content/PROJECTWIDGET` folder which has index.md and projects.md files, and projects.md uses files present in `content/project/`. They are all linked to each other!

NEXT: OTHER FOLDERS UNDER `content/`.
