## Session 6 Notes
read that : https://www.sanity.io/docs/presenting-block-text 

### How to bring the rich text content into astro/html?? 
It is not very straightforward. 

When you query your Sanity project’s API your rich text content is returned as Portable Text. Portable Text is designed to be used in pretty much any format or markup where you want to render rich text content. 

-In schema type 'object' you can add many fields as you wish. 

If you read 'presenting block text' .. zell does not recommend 'Serializing Portable Text to plain text' pathway instead he used 
Portable Text to HTML

https://github.com/portabletext/to-html

### so if you scroll down further into this github page there is section called 'Customizing components', here we need to provide 'types' value and this 'types' would correspond to '_type' on our portable block which is in this case '_type: 'figure'.  
