What do you want to get out of this course?
To make webpages which are fast to load. very lightweight on browser. Simple and easy user interface.

this is the url to check current website for speed and UI: by google.
https://developers.google.com/speed/pagespeed/insights/

Your site need not to be 100/100 but all stuff should be in green bars mainly.

things i do not understand yet:
how to remove:
- render blocking javascript
- asynchronous scripts.

-------

read about Locke's goal setting theory.
https://www.mindtools.com/pages/article/newHTE_87.htm

https://www.youtube.com/watch?v=dWOt2HyjCno

also the lift app link in the article is the coach.me app on iphone for goal achieving.

---

learn about github pages here to host stuff on github.
https://pages.github.com/

more stuff to read here: https://developers.google.com/web/fundamentals/

https://developers.google.com/web/fundamentals/performance/critical-rendering-path/page-speed-rules-and-recommendations

explore this page also:
https://www.udacity.com/wiki/ud884

really lots of stuff to read here. make sure I read this later.

---

i downloaded google chrome unstable from : http://www.chromium.org/getting-involved/dev-channel

and needs chrome in android for debugging. how to set android chrome for this :(remote debugging)
https://developer.chrome.com/devtools/docs/remote-debugging

new version of same page is here:
https://developers.google.com/web/tools/chrome-devtools/debug/remote-debugging/remote-debugging

good news it has a link for iphone too :)
yey. Now we should be able to move forward.

need iphone and android to test and move further.

---

well this is quite cool the android link is working finally. also it says to set stuff up on ios is also possible with safari but we need to use this link for that:
https://github.com/google/ios-webkit-debug-proxy

well maybe some day soon we will test this too.

---

well do not have a android phone? well not to worry we can emulate the phone also on your pc. I know that. here is a link to learn how to emulate your phone on your desktop.

https://developer.chrome.com/devtools/docs/device-mode

---

Lesson 1 Notes
=======

read this stuff fully:
https://developers.google.com/web/fundamentals/

most of the course is organised around these pages. This stuff if dope.

- this is the link we are using to learn about the dom in the course:
 - http://udacity-crp.herokuapp.com/cssom.html
 - view-source:http://udacity-crp.herokuapp.com/cssom.html

- what is dom?
 - https://www.w3.org/TR/DOM-Level-2-Core/introduction.html

- constructing object model
 - https://developers.google.com/web/fundamentals/performance/critical-rendering-path/constructing-the-object-model#document-object-model-dom

- notes on html5
 - https://www.w3.org/TR/html5/
 - prefer diving into html5 instead of the top one. already read most of it.
 - http://diveintohtml5.info/

- post on superuser about curl command:
 - http://superuser.com/questions/344927/powershell-equivalent-of-curl

 ---

 Code School course on chrome dev tools
 =======================================


take a good look at this resource also:
seems like a course on chrome dev tools. (can be useful).
 http://discover-devtools.codeschool.com/

---

- See Flushing the Document Early to learn more.
 - http://www.stevesouders.com/blog/2009/05/18/flushing-the-document-early/

- Also, check out Chunk Scatter, a fantastic tool for visualizing chunked HTTP responses.
 - http://blog.cowchimp.com/chunk-scatter-http-chunked-response-analysis-tool/

---

- how to read from timeline:
 - https://developers.google.com/web/tools/chrome-devtools/profile/evaluate-performance/timeline-tool

- another one for timeline.
 - https://developer.chrome.com/devtools/docs/timeline#timeline-event-reference

---

- again about cssom :
 - https://developers.google.com/web/fundamentals/performance/critical-rendering-path/constructing-the-object-model#css-object-model-cssom

- on render blocking stuff of css:
 - https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css

 ---

- so in css it from right to left that style applies. here is a discussion on it why it is so:
  - http://stackoverflow.com/questions/5797014/why-do-browsers-match-css-selectors-from-right-to-left

---

- so after the dom is ready and cssom is ready. the tree gets rendered:
 - https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-tree-construction

---

dom
cssom
render tree = dom + cssom.

- https://developers.google.com/web/fundamentals/design-and-ui/responsive/fundamentals/

- https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-tree-construction

---

web fundamentals:
================

https://github.com/google/WebFundamentals

its pretty much like a book should read this for sure. I can learn a lot about browser from these documents.

---

some notes on minifying css :
https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer#minification-preprocessing--context-specific-optimizations

interting stuff about how caching can make sites faster.
how caching can make sites faster:
- https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching  


how to optimize sites :
1 minify the site
2 compress the site
3 cache the site
(the above to links are on same topic)

---

review of render blocking css:
split css file into css for different media like: print, mobile etc and then only the file needed for device will be loaded and reduce file load which will reduce the time for render blocking css.

https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css

```
CSS “media types” and “media queries” allow us to address these use-cases:

<link href="style.css" rel="stylesheet">
<link href="print.css" rel="stylesheet" media="print">
<link href="other.css" rel="stylesheet" media="(min-width: 40em)">
```

read this blog post:
http://alistapart.com/article/responsive-web-design/

https://developers.google.com/web/fundamentals/design-and-ui/responsive/fundamentals/

---

how to optimize javascript on websites:

```
<html>
  <head>
    <meta name="viewport" content="width=device-width">
    <link href="style.css" rel="stylesheet">
  </head>
  <body>
    <p>
      Hello <span>web performance</span> students!
    </p>
    <div><img src="awesome-photo.jpg"></div>
    <script>
      var span = document.getElementsByTagName('span')[0];
      span.innerText = 'interactive'; // change DOM text content
      span.style.display = 'inline';  // change CSSOM property

      // create a new element, style it, and append it to the DOM
      var loadTime = document.createElement('div');
      loadTime.innerText = 'You loaded this page on: ' + new Date();
      loadTime.style.color = 'blue';

      document.body.appendChild(loadTime);
    </script>
  </body>
</html>
```

this is the simple page with a small script which shows how javascript can edit the dom and cssom.

---

javascript can be parser blocking if it is encountered within body of html.

as we can place <script></script> tags anywhere between the document.

read about how to mark script async. not sure if this is helpful as most of the scripts discussed in course are synchrounous.

https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript

---

an example of interactive design
http://www.themaninblue.com/experiment/ResolutionLayout/

also how to make the css inline ?
need to figure this out. it keeps talking in the course about this.

---

also learn about the defer attribute:
it stops a scripts from executing until dom is parsed completely.
https://hacks.mozilla.org/2009/06/defer/

and onload function which can run js functions when window finishes loading.
https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onload

and parser blocking and async scripts : (covered already)
https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript#parser-blocking-vs-asynchronous-javascript

---
