Websites have two sides to them:
Front-end: Client side
Back-end: Server side.

Webpages are created using HTML(Hyper Text Markup Language), CSS, and JavaScript.

HTML uses block-type elements to define different components of the page. These elements are defined with tags. Some common tags include:
<!DOCTYPE HTML>: This declares that the page is an HTML5 document.
**<html>: Root element of the HTML page.
<head>: Contains information about the page.
<body>: defines the body.
<h1>: defines a large heading.
<p>: Defines a paragraph.
And many more like the button tag<button>, image tag<img>, anchor tag<a href> etc.

JavaScript is added within the page source code and can be either loaded within '<script>' tags or can be included remotely with the src attribute: '<script src="/location/of/javascript_file.js"></script>'

The following JavaScript code finds a HTML element on the page with the id of "demo" and changes the element's contents to "Hack the Planet" : 'document.getElementById("demo").innerHTML = "Hack the Planet";'

HTML elements can also have events, such as "onclick" or "onhover" that execute JavaScript when the event occurs. The following code changes the text of the element with the demo ID to Button Clicked: `<button onclick='document.getElementById("demo").innerHTML = "Button Clicked";'>Click Me!</button>` - onclick events can also be defined inside the JavaScript script tags, and not on elements directly.