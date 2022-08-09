# Session 5 NOTES

starting with Sanity
How to integrate sanity in your project?? and how to setup Sanity?

### in the documentation --> getting started -- you make the project and use that link to install sanity, atm I have trouble installing on Mac but it is working on Windows.

start thinking about schema , how you are going to structure your data. 

"fields" means what should be contained inside like what fields. 'type' is very important. 

## after creating schema .. next step is import into schema.js and also add it.  atm I can't add second schema for some reason.

auto save feature in sanity, click on three dots and 'inspect', if it has 'drafts' written there .. means it is not published.  You can create content here, Also read about "schema types" in documentation. that's how you can add different fields.

## Next Step is how to pull content from Sanity into Astro. The easiest way is using sanity client library. install Javascript one using npm.  

so the Question is "IS that a different project that Sanity created?? " If you want your client to access "sanity studio" it can be put as sub-domain as a separate project on netlify. but one thing is you have to install sanity as dependancy. then you can run sanity start. (we will do later).

CodewithHarry put frontend and backend two folders in same project and can run "servers" using cli by accessing that folder. so don't need to open two vscode windows.

- After installing JS client on astro project folder, create a js file (sanity.js) e.g . Next step is copy over the "API" code from documentaion for now. 
- so few things, Astro does not support common JS format, so we need to do import sanityClient from '@sanity/client' and remove the following code from API code otherwise it is gonna be duplicate declaration.

- const sanityClient = require('@sanity/client')
# Two pieces of information I am required here to connect with Sanity API 
-projectId and 
-dataset
for api version just use the current date. "token" we don't need right now (You may delete, if you wish so). "useCdn" leve "true" for now. 

I can find this informatiom in sanity.json file (in Sanity Project) or you can also find in project details on sanity website. find the relevant tabs. 
#
Let's move forward and we need to perform query now, check the sample code "performing queries" and copy over for now.
It is a lot of code but basically we need a fetch function that takes in 'query' and 'param' as you can see in the code (by default). It is like customizing our own 'api' here. and from this function just return client.fetch(query, param). Zell gave param default value of empty object {}. video@ 20:00

In the query variable you can see (_type==="bike" && seats e.g), not easy to understand as there is no real type, type can be found in three dots --> inspect (in sanity studio) you will see type is actually what we set "name", the value shown here for type is not what we set. so it is misleading . In 'query' variable we don't have parameters so we just leave *[_type==="blogPost"] because blogPost is our schema. Zell has not declared query variable in this .js file. Make sure you write 'export' with fetch function because we will use in astro pages. 



Now in 'pages' create an astro file and in the frontmatter section import {fetch} from that .js file which we cretaed earlier. after that define 'query' variable and then fetch that query using 'await'. console log underneath so you can see which data you pulled. In localhost you need to navigate to relevant 'astro' page. Check your console and you should be able to see data. 

So whatever fields you put in sanity can be fetched like this and now you can use these values. make sure you have slug because you need a unique address for the post.

## How slug works ... for that just create few more posts.

- better practice would be to create a folder in pages like 'blog' e.g , here we will use [] bracket notation to create the file. because we want to create multiple pages, In Astro documentation it is written in "Routing", read up on that, it allows you create dynamic page creation. to make that work you need to export getStaticPaths function , essentially you have to pass in various stuff, 'params' and 'props'. params will allow you create page itself. we are not passing any 'props' for now. Inside this function we have to use fetch request. then use map method on that data. 
### using map method you need to set params value (e.g {slug:post.slug}), he also set props: {post} using map method. 
Then you can get {slug} and {post} out from Astro.props, console log them too to check.
save this map to a variable (e.g paths) and return it in the end. 
- 
- Fetch the data here as you did before, you actually don't need that astro file because you are fetching posts here.

- Astro components that generate routes dynamically have access to an Astro.params object for each route. so just use {slug} = Astro.params;
### svelte component giving error while building (npm run build) , so will have a look later. 

after using that if you npm run build in astro project, you will see in "build" there are multiple index pages created. these pages can be accessed using slug.

### Does that work for you with slug , Can you open each page using slug address?? This is how you create the pages/files.

We need one astro page to put all sanity stuff otherwise it does not make any sense. say index.astro inside sanity or/blog folder. here we will create link to all our blog posts and we wanna be able to go to that page by clicking on it. so we fetch all the data using query and 'await fetch'. This time we don't have to use getStaticPaths function. we can use map method for that to create <li>s.
  
  - There is one caveat , don't forget to add folder name in slug, otherwise you will have wrong href. (e.g {'sanity/' + post.slug})
  ### Are you successful in listing all the blog post in lis?
  
  Zell suggests in schemas create different folders and put your relevant schemas in it. 
### Huge confusion atm is "rich text editor" so far my understanding is content type should be richText but for now I am getting error as it is not  schema type anymore. check "block schema type".Aslo read this... https://www.sanity.io/docs/configuration
  
  OK NOW Littlebit confusing part for me...
  
  ### he created another schema file (richText.js) in sanity and then added in fields of main schema (blogPost), YOU NEED to figure it out what's happening here???
  ## However I just want to tell you that codewithHarry used "reference" schema type to link one schema to another . (figure it out.. read documentation).
  
  ### Now Zell is talking about when you used rich text editor.. how you gonna use it in html as you can access that now. video@ 47:00
  
  he thinks rich text editor does not give you image option , so he created another schema figure.js (check that code for type of schema) and then just put type : figure in other schema (richText). check it out.
  
  How to use "portable text to html" in documentation. as he is trying to pull data from rich text to astro but he couldn't do it. 
  
  Searh "Sanity Plugins" . markdown e.g. if you don't want rich Text. 
  
  
  
  He created couple more schemas (contact, about) and he will talk about them later. 
  
































