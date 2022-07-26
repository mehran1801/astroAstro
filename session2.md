---
layout: ../layouts/Base/mdLayout.astro
title: 'Second Session Notes'
---

Today Tuesdau 26th of Jusly 2022 I am writing about Astro and I am following Session 2 of the series.

#### Different ways to add css , I prefer to create css folder in src and a file styles.css and import this file.
#### ../ means previous folder and one dot means same folder.
##### How your css is created, when you build the project(npm run build), check in dist -> assets -> first file.

##### If you want to use reset.css or other css files, you can import at the top of styles.css file. using @  import '.    / reset.css ' Check in assets folder after build and you will see they all stacked in one css file.

##### You can also use sass but for now I have skipped this part.

##### If you have component and you can keep the styles scoped to this component using style tag. See what fits in your workflow.
##### Or you can put more global styles in styles.css file and specific styles in scoped styles. Play around..


# Question: I created navigation component to be shared across multiple pages, how do I make component aware of page it is on? so It can underline the navigation it is on? Interesting question here.....********************************

##### Zell is talking about his own blog post where he used vimeo componet, If you are interested in code it starts at 1:03:02 in session 2 video.

##### How to use components in Markdown file ? setup (Read the documentation for Markdown file)


##### You can put components everywhere. Some code snippet of how blog posts are created .. Have a look at 1:25:00 of vodeo 2. 