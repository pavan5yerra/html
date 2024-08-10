

- HTML stands for hypertext markup language .
- It is used to describe the structure of the document displayed on web
- The whole structure works in the form of tree  nodes
- Each element is a node 
- It is written in form of tags
![image.png](https://eraser.imgix.net/workspaces/RHvayis7uYQNdrSqkxAk/2TpPe0m2nPZODyVZctbl8Rh7kLL2/TazxJavYpnIosXVDuSflZ.png?ixlib=js-3.7.0 "image.png")



### Types of HTML
- replaced elements 
`﻿<img> <video> <iframe> <audio>` 

- void elements
`﻿<br> <hr> <input> <link> <meta> <img>` 

- Non-replaced elements : Elements that contains opening and closing tags
      Some Examples : `﻿<div> <span> <p> etc...` 



### Anatomy:
```html
<div id = "hello" oncick ={handleClick()}> hello </div>
--> div is tag
--> id  , onclick: attributes
--> onclick : event handling
--> hello : text node

```


## Document Structure :


```html
<!DOCTYPE html> 
  -- This is special kind of node called doctype
  -- This will tell browser to render in standard mode
  -- If we omit it will run in Quirk mode
  -- Quick mode run without w3c standards 
  -- Standard mode runs with all satified requirements of w3c standards
  
  <html lang = 'en-US' >
    -- It is the root the element
    -- lang is a content language specifier.
    -- en means english & US means region based language(slang).
    -- It contains info about what need to done before redering the page
    
    <meta charset='utf-8'/>
       -- meta tag tell browser what need to be done.
       -- charset attr tell to load utf-8 format of char encoding
       -- other encoding - ASCII , ISO-8859 
       -- utf-8 is inherited above formats
     
    <meta name="description"
content="Register for a machine learning workshop at our school for machines who can't learn good and want to do other stuff good too" />
       -- named meta tags , it accepts diff kind of values
       -- description values usefull for SEO 
       -- description content value is often what search engines display under the page's title in search results.
   
    <meta name="robots" content="index, nofollow" />
       -- if you dont want to follow by robots of search engine
    
    <meta name="viewport" content="width=device-width" />
       -- page will become responsive.
       -- It means size of the elements will appear based on device width.
     
    <meta http-equiv="Content-Type" content="text/html"/>
       -- http-equiv is also known as pragma directive
       -- These will describe how to parse the page
       -- above valuse tell browser to parse it as text or html
       
    <meta http-equiv="refresh" content="60; https://machinelearningworkshop.com/regTimeout" />
       -- It tells browser to refresh the page every 60 sec
       
    <meta http-equiv="content-security-policy" content="default-src https:" />
       -- It is important directive
       -- It tells what type of content policy browser should use for a page.
       -- It helps with cross-site scripting attacks.
       
    <meta property="og:title" content="Machine Learning Workshop" />
    <meta property="og:description" content="School for Machines Who Can't Learn Good and Want to Do Other Stuff Good Too" />
    <meta property="og:image" content="http://www.machinelearningworkshop.com/image/all.png" />
    <meta property="og:image:alt" content="Black and white line drawing of refrigerator, french door refrigerator, range, washer, fan, microwave, vaccuum, space heater and air conditioner" />
       -- These are the social cards 
       -- mostly used for ad's
    
    <title> Machine Learning </title>
       -- It give page a title 
       
    <link rel='stylesheet' src='./sample.css'/>
    <link rel="icon" sizes="16x16 32x32 48x48" type="image/png" href="/images/mlwicon.png" /> 
    <link rel="alternate" href="https://www.machinelearningworkshop.com/fr/" hreflang="fr-FR" />
    <link rel="alternate" type="application/x-pdf" href="https://machinelearningworkshop.com/mlw.pdf" />
    <link rel="canonical" href="https://www.machinelearning.com" />
       -- Link element is the way to access diff kind of resources
       -- stylesheet relation will point to css files 
       -- icon relation will load favicons
       -- alternate is like linking to other version of page (locale based or pdf versions)
       
    <script src="js/switch.js" defer></script>
       -- Script tag is very imp ,bcz its give access to run javascript
    
   <head>
     -- It is Document meta data header tag
     
   </head>
    <body> 
    
    </body>
  </html>
  
```




## Semantic HTML:
- semantic means meaningful, concept is used HTML elements based on meanings
- using it increases Accessibility.
-  Browser build DOM , CSSOM and AOM (means Accessibility Object Model)
- Assistive devices, such as screen readers, use the AOM to parse and interpret content.
- It also give us  easy of navigating the page using keyboard , mouse , etc.


```html
NOT SEMANTIC 

<div>
  <span>Three words</span>
  <div>
    <a>one word</a>
    <a>one word</a>
    <a>one word</a>
    <a>one word</a>
  </div>
</div>


Getting Accessibility with out using sematic elements

<div role="banner">
  <span role="heading" aria-level="1">Three words</span>
  <div role="navigation">
    <a>one word</a>
    <a>one word</a>
    <a>one word</a>
    <a>one word</a>
  </div>
</div>


SEMANTIC ELEMENTS USE -- Correct way 

<header>
  <h1>Three words</h1>
  <nav>
    <a>one word</a>
    <a>one word</a>
    <a>one word</a>
    <a>one word</a>
  </nav>
</header>


```


## Images :
- Displaying images on animation  on page , is very GPU  intensive task for browser.
- HTML provide inbuilt support to render images in best possible way
- some of the tags are `﻿<img> <picture> <figure>` 


```html
<img src="images/eve.png" alt="Eve">
-- This is basic image tag

<img src="images/eve.png" alt="Eve"
srcset="images/eve.png 400w, images/eve-xl.jpg 800w"
sizes="(max-width: 800px) 400px, 800px" />

-- It also proivdes  ways to load the images based on device viweport
-- scrset will helps to load differnt images
-- sizes attr will help to fix the size of the image
-- apart from this attr html provide inbuilt methods for optimized rendering
-- lazy attr for lazy loading of images (image load when it appear on viewport)

--> Above thing can be done using picture tag as well

<picture>
  <source src="images/eve.png" media="(max-width: 800px)" />
  <source src="images/eve-xl.jpg" />
  <img src="images/eve.png" alt="Eve" />
</picture>



--> Usage of figure tag
 -- figure  tag can used as image , code snippet , diagram , illustartion , etc..
 -- it comes along with figcaption
 

<figure>
  <img src="/media/cc0-images/elephant-660-480.jpg" alt="Elephant at sunset" />
  <figcaption>An elephant at sunset</figcaption>
</figure>


--> using figure as code snippet
<figure>
  <figcaption>Get browser details using <code>navigator</code>.</figcaption>
  <pre>
    function NavigatorExample() {
      var txt;
      txt = "Browser CodeName: " + navigator.appCodeName + "; ";
      txt+= "Browser Name: " + navigator.appName + "; ";
      txt+= "Browser Version: " + navigator.appVersion  + "; ";
      txt+= "Cookies Enabled: " + navigator.cookieEnabled  + "; ";
      txt+= "Platform: " + navigator.platform  + "; ";
      txt+= "User-agent header: " + navigator.userAgent  + "; ";
      console.log("NavigatorExample", txt);
    }
  </pre>
</figure>
```




