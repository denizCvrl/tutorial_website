---
date: "2019-02-11T19:27:37+10:00"
draft: false
title: Lesson 8 - Archetypes Part 2
weight: 9
---

This lesson goes over each archetype one by one. If you understand Lesson 7 perfectly, feel free to skip this one. Otherwise, this is a nice recap of the previous lesson with more details.  

Let's remember the available options we have and how they appear in `themes/hugo-academic/archetypes/`. As discussed before, you can find some templates under their respective folders. For those templates, choosing archetypes from the New Post window doesn't produce the expected result. I solved this problem by moving some things around in our directory. You might not need these adjustments in the newer version of the academic theme. Also, you might have other archetypes in addtion to the ones listed below.   

![](/img/19_archetype2.png)

### Project

- Copy and paste index.md from `themes/hugo-academic/archetypes/project` to `archetypes/` at the root of your side (if not present, create the folder). 

- Rename index.md to project.md. 

- `Addins -> New Post`, subdirectory = project, archetype = project. 

You will now have a preconfigured front matter with your credentials. New Post basically uses the information from `/archetypes/project.md` and creates a new index.md file under a new folder (See the figure below). If you followed the steps in __Some Advance Stuff__ in the previous lesson, then the folder and index.md files will be created automatically. Otherwise, you might need to enter a subdirectory name. Feel free to change the name of folder as you wish.

Open the `/archetypes/project.md` file to see explanations of your options and where to enter your featured photo or slides. Play with the urls and see if you have broken links! For example, slug is created automatically. Depending on your preferences about permalinks, you might need to change or delete slug. 

![](/img/21_project.png)


### Publication

- Copy and paste index.md from `themes/hugo-academic/archetypes/publication` to `archetypes/` at the root of your side (if not present, create the folder). 

- Rename index_md to publication.md. 

- `Addins -> New Post`, subdirectory = publication, archetype = publication. 

Preconfigured front matter for publication lists more options. Open the `/archetypes/publication.md` file to see explanations of your options. Do you see the *featured* parameter? That's to be used in the featured widget, which you may remember from way back!

![](/img/22_publication.png)

### Slides

- Copy and paste index.md from `themes/hugo-academic/archetypes/slides` to `archetypes/` at the root of your side (if not present, create the folder). 

- Rename index.md to slides.md. 

- `Addins -> New Post`, subdirectory = slides, archetype = slides.

For the slides, you have parameters for themes and highlighting. Follow the instructions for your options. 

![](/img/23_slides.png)


### Talk

- Copy and paste index.md from `themes/hugo-academic/archetypes/talk` to `archetypes/` at the root of your side (if not present, create the folder). 

- Rename index.md to talk.md. 

- `Addins -> New Post`, subdirectory = talk, archetype = talk.

![](/img/24_talk.png)


### Docs

docs.md in `themes/hugo-academic/archetypes/` is not located inside a folder so you do not need to do anything with it. This archetype is great for courses/tutorials and you can see some examples in `/content/courses/`. As usual, if you want to see the content of this folder, you can simply change your menu and use blogdown::serve_side(). 

In a course or tutorial, you usually want to create multiple pages with table of contents. The key is to save your index.md as _index.md. Then create separate markdown files for each page of your course. `/content/courses/example` folder has examples. 

![](/img/24_docs.png)

By the way, don't forget to change the name of your documentation folder. It took some time for me to figure this out! In the figure above, for instance, I need to rename "example" to "2019-12-15-newcourse".

To be honest, I haven't yet figured out how to use .Rmd files in this format. I will explore docs more if I need it, but for now I am just using .md files. If you want, you can start exploring docs now by reading [the part about HTML documents](https://bookdown.org/yihui/rmarkdown/html-document.html) from the R Markdown book.     


That's ALL for the folders in `content/`. 

By now I hope that you have your website setup with some or all of your own content! We will cover how to publish it in the next lessons.   

