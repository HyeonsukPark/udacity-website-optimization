# Website Performance Optimization portfolio project

* To see the online portfolio page, open a index.html file. There are tree folders which are css, img, js for index.html. 
* Inside the folder views, you can see pizza.html and other folders for pizza.html. 


## Optimize PageSpeed Insights score for index.html

* The purpose of this project is to Optimize PageSpeed Insights score for index.html. PSI score of the page should be more than 90. 


### Critical Rendering Path - Solution 

1. Inline CSS
CSS is treated as a render blocking resource. The link of CSS takes time to render resources. Therefore, it's better to do inline CSS on html page. 

2. Media="print"
If the CSS stylesheet doesn't have media="print", it would apply in all cases. In this case, it takes time to render the page. So i added media="print" to the stylesheet - <link href="css/print.css" rel="stylesheet" media="print">. This is only applied when the page is being printed so it's not render blocking when the page is first loaded in the browser. 

3. Javascript 
Javascript is parser blocking. Adding the async keyword to the script tag <script async> tells the browswer not to block DOM construction while it waits for the script to become available. 

4. Javascript in the <Body> tag.
The script is placed in the end of <body>tag. 


## Optimize Frames per Second in pizza.html

*  The first purpose of this project is to do optimizations for pizza.html. The page should have a consistent frame-rate at 60fps when scrolling. In order to achieve that, I modified views/js/main.js. 
* The second one is reducing time for resizing. Time to resize pizzas should be less than 5 ms using the pizza size slider on the views/pizza.html page. 


### Solutions

1. Each variables in a loop is executed for each iteration of the loop. That makes the page load slow. Statements that is placed outside the loop will make the loop run faster. 

2. In for-loop, the length property of an array os iterated when it's inside the loop. For example, [ for (var i = 0; i < items.length; i++) ]. I made a variable like var pizzaLen = items.length. And then, i made a for-loop like 
[ for (var i = 0; i < pizzaLen; i++)]. 

3. querySelectorAll() -> document.getElementsByClassName('mover')
I chacked this website.[(https://jsperf.com/getelementsbyclassname-vs-queryselectorall/18)]
About operations per second, getElemenetsByClassName is higher than querySelectorAll. Thus, getElementByClassName is better than querySelectorAll. 


 


