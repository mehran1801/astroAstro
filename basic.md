---
layout: ../layouts/Base/mdLayout.astro
title: 'First Blog Post'
---

<!-- <Base>
Home Page
<!-- {title} -->
<!-- </Base> --> 

### I just figured out that in .md file you cannot write 'componet' as you would write in .astro files. It means if you can't
### write component then how are you going to define props values like 'title'.

## So solution is to make its own layout and declare properties there. To define those properties we need to define at the top in --- this area. So I am going to create a layout for md files. 

## Another point I just thought about is layout for md file should be separate because it defines title in astro . props . content. while your other layout component has title from astro . props.  it is nested under content property.

# views about style tag, 
# If same property and value, then there is shortcut way to define.