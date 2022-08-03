---
layout: '../layouts/BlogPost.astro'
title: 'First Session Notes'
---

��网？？？？？？？？？？？？？？�

- Copied the common data and put it into the layout (Base layout)
- Changed the title on all the pages using Props
- Made the markdown pages, and learnt why to create separate layout
- put import statements on the top. otherwise you get an error.
- Component will have different object(Astro . props) but in markdownit is slightly different (Astro . props . content).
- Astro uses a code fence (---) to identify the component script in your Astro component. 
- Head component is merged into Base component so I figured out how to use title property value, as you can see all pages have 
    different title values.
- When you place a style tag inside of an Astro component, Astro will detect the CSS and handle your styles for you, automatically.
- If same property and value, then there is shortcut way to define.just like this     title} else use it like this       {---title={title  }}, here title is just like normal attribute but it is a variable declared in other astro component file, and its value is J.S. so we write that in braces.

Task: All pages should have different title including md pages. can you do it?

- How can you write some markdown in your component (import markdown from) import  Markdown} from 'astro/components', UPDATE: It is no longer built into Astro built-in components. Check documentation for more built-in components.




��网？？？？？？？？？？？？？？�
