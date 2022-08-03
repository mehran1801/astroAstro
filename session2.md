---
layout: '../layouts/BlogPost.astro'
title: 'Second Session Notes'
---

Today Tuesdau 26th of Jusly 2022 I am writing about Astro and I am following Session 2 of the series.

#### Different ways to add css , I prefer (external styles)to create css folder in src and a file styles.css and import this file in Base Layout.
#### ../ means previous folder and one dot means same folder. there is also scoped css. 
##### How your css is created, when you build the project(npm run build), check in dist -> assets -> first file.

##### If you want to use reset.css or other css files, you can import at the top of styles.css file. using @  import '.    / reset.css ' Check in assets folder after build and you will see they all stacked in one css file.

** I faced a little problem in changing the body background color of each page, I had to add div and give it a class name. still don't know how to target body of each page.** other than targeting body I can just use scoped css.

##### You can also use sass but for now I have skipped this part.

##### If you have component and you can keep the styles scoped to this component using style tag. See what fits in your workflow.
##### Or you can put more global styles in styles.css file and specific styles in scoped styles. Play around..

# Make a component and use it, give some scoped styles. I tried Jumbotron from bootstrap.
# todo: Inspect the page --> elements and in html you should be able to see component embedded in the page.

# Question: I created navigation component to be shared across multiple pages, how do I make component aware of page it is on? so It can underline the navigation it is on? Interesting question here.....********************************

##### Zell is talking about his own blog post where he used vimeo componet, If you are interested in code it starts at 1:03:02 in session 2 video. He is showing how things are put in parts.

##### How to use components in Markdown file ? frontmatter property "setup" is used (Read the documentation for Markdown file)
# todo: Try that Jumbotron component that you created in Markdown file. setup is deprecated in Markdown file, use mdx now. Also how to embed multiple components in Markdown file.  *NOT Working for now.....


##### You can put components everywhere. Some code snippet of how blog posts are created (some advanced stuff which we will learn) .. Have a look at 1:25:00 of video 2. 
