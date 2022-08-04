### how to sort the blog posts? (descending order)  To sort the post we need to add 'date' to the fontmatter of that post itself in yyyy-mm-dd format. I have given dates (fourth post (today's date)) and 3rd, 2nd and first post the future dates. however by just adding 'date' to the fontmatter of that post, order has no effect on order in blog.astro(where we fetched the posts), so How do we do it? we use sort function to sort the dates.

### Since Astro.glob() returns an array, all you have to do is call .sort() in that array and sort it by whatever data you want: in our case, date. However, we’re not working with simple numeric arrays, we’re working with an array of objects. So instead of just doing a - b, we need to pick the value we want to sort: a.date - b.date. for example. To complicate things further, we’re storing the date as a string, so we need to get a numeric representation of that date. Hence, Date.parse(a.date), which transforms the date like "2022-07-01" to the number of milliseconds since January 1, 1970. You can read more about Date.parse() on MDN. The Date.parse() method parses a string representation of a date, and returns the number of milliseconds since January 1, 1970, 00:00:00 UTC, you can see how zell did (little different way over what I found on a website), depending on 'ascending' or 'descending' you can change sort b-a or a-b. so it's straightforward.

### When you create an article, you also want to attach a date to it. so if we do post.frontmatter.date } , it is not in readable format. easier way is to import the library date-fns. install it with npm i date-fns -D. then just import it and create readable function. check format in documentation and then call that function where you want to insert the date. ERROR: if you get this error parseISO , put New Date() and wrap function's argument in it. 'YYYY' format is giving error , use 'yyyy' instead

### ** Now we move to navigation where we would like to highlight the page we are currently on. **

### There is a way to do it and the way is to do with cannonicalURL.pathname, remember that was a big URL object with lots of information in session 3. The key is if we are on 'About' page we need to show an active class. Question is How do I put this? Put all the pathways in an array and loop thorough it. using map and render the navbar, next thing is we want to find out whether state is active or not. After checking with map function if href is equal to pathPath, we still don't see any isActive equal to 'true' when we console logging, if you console log pagePath you can see path has / forward slash in the end. you can check for / slash in the map function but let's not make things more complicated and simply add / in the navItems array we created. Now which ever page you click on has 'active' state. When doing such stuff alway "inspect" and go to elements and see what's going on with html. It's a good way to debug something. atm I am having trouble adding bootstrap classes. Next step is just to define active state color in css.whatever navigation link you click on should be active and change color. 


### Next issue we are having is when we are in blog page and we click on some post, blog link is not active anymore. So what can I do if I am inside blog page internal link and still want to highlight blog navigation link. It is not working atm because we are checking the equality === in map function. so the solution is not to check equality and put some if conditions. 
Video @ 34:00 minutes 



### Let's talk about JS , it's little bit funky as far as Astro is concerned. I created new page JSTest. inside < script > tags if you console log anything , it does not show up in console until you restart server (npm run dev)

## hydration means interactive, opposite of static content.

### reading up on partial hydration in astro documentation. it is called "Astro Islands" now in documentation. (check nice blog here),  sometimes, client-side JavaScript is required for creating interactive UI. Instead of forcing your entire page to become an SPA-like (single page application) JavaScript application, Astro asks you to create an island.
### Zell tried to wrtie vanilla JavaScript in script tag and he also created js file and imported it but he is running into lots of errors. so the best way is skip the vanilla js and use framework instead. He created svelte component file , check if it is configured properly in astro.config.js.  first, install its integration and any associated peer dependencies:


### Guides ==> UI Frameworks ..read the documentation, I just noticed By default, your framework components will render as static HTML (remember you had problem.. try that too).. ok when using these components don't forget client directives. otherwise static. Can I Hydrate Astro Components? read the documentation so you know how to use script tag to send JS to browser. Essentially whatever variables you declare in script tag gets updated on DOM automatically when you call them. There is some more information about script tag in components ===> client side scripts in documentation.

### Task: you should be able to import component and click on the button and it should be interactive, changing information.
### basically you put the js in script tag and underneath used it and then call the component in the astro page making sure template directive is written next to it otherwise won't work. also explore other template directives. 


### can you make it work in md files? YES I did it, so firstly you install mdx integration to install it as page, (restart the server) and then import your components not in frontmatter fence, just outside of it, and then just use in file as many times as you want, don't put template directive to keep it static.

### you can put sort function in js file and put export next to it and then import where you want to use sort function. keep your code clean.


### One last important thing he talked about how to organize your project pulling out some information and put in separate files, definitely check it out. video @1:03
