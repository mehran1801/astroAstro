---
layout: ../layouts/Base/mdLayout.astro
title: 'Third Session Notes'
---

# Session 3 Notes

####    Normally I would like to have url something like blog/first-post, so I create a blog folder in pages. Now Let's create
#### a layout for blog posts, will just copy from BlogPost for now. Then I am using that layout in first-post.md and second-post.md
####    we define title and description, when you search in google .. the first line is title and text underneath is description
## so we need title and description for each post. on Astro main page Explore => integrations.. check out the plugins.


### I want to give title and description for each post. How do I do this? Im md file I am writing title and description for each post as frontmatter. and the layout I am using has the title and description defined in it. e.g BlogPost.astro has title and description defined. and also <--Base  --> would have title and description, so it is all the way up.

### You must learn that what is happening here???

###### scenario is I have Base layout and I have BlogPost layout, In my md file I am writing title and description for each post as frontmatter. Now I need to define title and description in Base, and that will be used as attributes in BlogPost.astro file (in Base component) and its values will be equal to the title and description defined (JS values)in BlogPost.astro file. and then each individual values will be defined in each md files. GET MY POINT?


#### Layout that you are using in md file, you will use astro . props. content in that astro layout file.

### Now for SEO purposes you can use that title and description in meta tags.

#### astro has astro seo plugin, It gives you SEO component and different propnames. Right now we have title and description, this title will showup in google and this title is in meta tag which is in head tag. Now title should be Changed on both blog posts.(you already learnt that)


#### I am noticing that if you want to use any variables in blog posts, you have define variables in the Base component and BlogPost component, so all the way up. e.g title and description is defined .In one component you will desctructure from Astro.props and in other astro.props.content... you can check.. This is pain in the butt, search spread attributes,  Astro Vs X (in documentation), In Base.astro frontmatter define props  = Astro.props, then you spread it in other files,  there is Head component in it, so put ...props} here. ** Dont' use these if not sure.

#### Also you can do the same in BlogPost.astro file, declare props and then spread it in other files which is Base component.
#### It is hard to debug description by just console logging, so in Base.astro I put under body tag.
#### so we basically wrote title and description in the head component for SEO purposes. Just have a look at the code written in meta tags. Most of the SEO stuff is done at this point.

### Learn ==> Guides ==> configuring Astro   (documentation)
### Reference (Tab next to Learn in Documentation) ==> configuration  (Check all these configuration options in Astro)

### Zell talks about site configuration option ....

### For SEO your site requires few things, check his SEO tips.

### difference between relative path and absolute path. google it if not sure. How to put image in blog post md file. 

#### what is cannonical url? It will give you URL of the page. Astro documentation has configuration reference (in Reference section) called site, which will  give you the URL of the site. add this in astro.config   .mjs file. Now what we can do is put that in Head.astro file as cannonical url tag. It is link rel="cannonical"  and href attribute.
#### Copy OG (open graph) tags for facebook and twitter.


### Astro.cannonicalURL is an object (URL) Useful for interacting with individual properties of the request URL, like pathname and origin. origin is your site address (index file maybe)

## Now you have cannonicalURL which is href of your site, we need to add(concatenate) path of the image with this href. like we made it full image link.

## you defined imageURL in Head component but you will declare it in md post file. once done , inspect the post and see what is in meta tag. it should have image listed somewhere. if you have image folder in public folder, you don't need to write public in relative path.

#### Now we move towards blog.astro file. Now let's drag our blog posts from blog folder. 
#### ### Reference (Tab next to Learn in Documentation) ==> Runtime API .. find Astro.glob here. if you console log it, it returns an array and each post is an object with properties like frontmatter ,file , url(this one is important), content and couple more. and each one is an array.

## when you map posts, if you care about the order use slice method with map method.

## not sure what is causing this error , unable to fetch files with Astro.glob()

### he is doing gallery page. How can you accomplish this with map method.

#### we have a gallery page that contains the code itself, like we have an array of images as frontmatter data(variable), and then we just used that in component, but in component we have already written the code using map. How useful is the map method???

