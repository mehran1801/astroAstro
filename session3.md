---
layout: ../layouts/Base/mdLayout.astro
title: 'Third Session Notes'
---

# Session 3 Notes

####    Normally I would like to have url something like blog/first-post, so I create a blog folder in pages. Now Let's create
#### a layout for blog posts, will just copy from mdLayout for now. Then I am using that layout in first-post.md and second-post.md
####    we define title and description, when you search in google .. the first line is title and text underneath is description

#### astro has astro seo plugin, It gives you SEO component and different propnames. Right now we have title and description, this title will showup in google and this title is in meta tag which is in head tag. Now title should be Changed on both blog posts.(you already learnt that)


#### I am noticing that if you want to use any variables in blog posts, you have define variables in the Base component and BlogPost component, so all the way up. e.g title and description is defined .In one component you will desctructure from Astro.props and in other astro.props.content... you can check.. This is pain in the butt, search spread attributes,  Astro Vs X (in documentation), In Base.astro frontmatter define props  = Astro.props, then you spread it in other files,  there is Head component in it, so put ...props} here. Dont' use these if not sure.

#### Also you can do the same in BlogPost.astro file, declare props and then spread it in other files which is Base component.
#### It is hard to debug description by just console logging, so in Base.astro I put under body tag.
#### so we basically wrote title and description in the head component for SEO purposes. Just have a look at the code written in meta tags. Most of the SEO stuff is done at this point.
#### what is cannonical url? It will give you URL of the page. Astro documentation has configuration reference (in Reference section) called site, which will  give you the URL of the site. add this in astro.config   .mjs file. Now what we can do is put that in Head.astro file as cannonical url tag. It is link rel="cannonical"  and href attribute.
#### Copy OG (open graph) tags for facebook and twitter.
#### Now we move towards blog.astro file.
####