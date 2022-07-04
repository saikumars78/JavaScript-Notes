# 58 The DOM

The first, getElementById, gives you access only to those components that have been assigned an id.<br>The second, getElementsByTagName, is good for wholesale changes, but is a bit cumbersome for fine surgical work.

Document Object Model,The DOM is an organization chart, created automatically by the browser when your web page loads, for the whole web page. All the
things on your web page—the tags, the text blocks, the images, the links, the tables, the style attributes, and more—have spots on this organization chart. 

```HTMl
1st level: document
2nd level: <html>
3rd level: <head>
4th level: <title>
5th level: Simple document
           </title>
           </head>
3rd level <body><br>
4th level <p>
5th level There's not much to this
         </p>
         </body
         </html>
```
      
      Document
          |
         html
          |
       ___|____
      |         |
    head       body
      |         |
    title       p

In the DOM organization chart, each box represents a node.<br>
The HTMLpage represented above, in its cleaned-up DOM form, has 8 nodes: the document node,
the html node, the head and body nodes, the title node,
one paragraph node, and two text nodes.

# 59 The DOM:Parents and children
```
1st level: document 
2nd level: <html> 
3rd level: <head>
4th level: <title>
5th level: Simple document
           </title>
           </head>
3rd level <body>
4th level <div>
5th level <p>
6th level There's not much to this.</p>  
5th level <p>  
6th level Nor to this.</p>
          </div>  
          </body>
          </html>
```

```
         document
            |
       _____|______
      |            |
    html          head
      |            |
    title         div
      |            |
   simple doc      |
                ___|____________
               |                |
  There's not much to this   Nor to this
                  
```

```
<p>This is <em>important</em>!</p>
```
If you made a chart for this paragraph, you might think that all the text is a child of the < p > node.But remember, every node that is enclosed by another node is the child of the node that encloses it. Since the text node "important" is enclosed by the element node < em >, this particular text node is the child of < em >, not < p >.

# 60 The DOM: Finding children
```
var eField = document.getElementById("email");
```
The statement above targets the element with the id of "email".
```
var eField = document.getElementsByTagName("p");
var eField = document.getElementsByTagName("p");
```
Having made a collection of paragraphs, you can target any paragraph within the collection.
```
var contents = p[2].innerHTML;
```
The statement above assigns the text string contained within the third paragraph of the document to the variable contents.
```
<body>
<div id="cal">
<p>Southern Cal is sunny.</p>
<p>Northern Cal is rainy.</p>
<p>Eastern Cal is desert.</p>
</div>
<div id="ny">
<p>Urban NY is crowded.</p>
<p>Rural NY is sparse.</p>
</div>
</body>
```
If you wanted to read the contents of the last paragraph in the markup, you could write...
```
1 var p = document.getElementsByTagName("p");
2 var contents = p[4].innerHTML;
```
# 61 The DOM: Junk artifacts and nodeType
```
1st level: document<br>
2nd level: <html><br>
3rd level: <head>
4th level: <title>
5th level: Simple document
           </title>
           </head>
3rd level  <body>
4th level  <div>
5th level  <p>
6th level  There's not much to this.
           </p>
5th level  <p>
6th level  Nor to this.
           </p>
           </div>
           </body>
           </html>
```
These extra text nodes create noise that makes it hard for your DOM-reading code to find
the signal. In one browser, the first child of the body node might be a div. In another browser,
the first child of the body might be an empty text node.

There are a number of solutions. As one approach, the Mozilla Developer Network
suggests a workaround that's almost comically desperate but does solve the problem without
any extra effort from JavaScript. You format the markup like this.

Here's the markup, with the text 
```
<div id="humpty">
<p>All the king's horses.</p>
<p>All the dude's crew.</p>
<p>All the town's orthopedists.
</p>
</div>

This is the code.
1 var d = document.getElementById("humpty");
2 var pCounter = 0;
3 for (var i = 0; i < d.childNodes.length; i++) {
4 if (d.childNodes[i].nodeType === 1 ) {
5 pCounter++; 
6 }
7 if (pCounter === 2) {
8 d.childNodes[i].innerHTML = "All his men.";<br>
9 break;<br>
10 }
11 }
```
Here's the breakdown:<br>
1 Assigns the div to the variable d<br>
2 Counts the number of paragraphs<br>
3 Goes through the children of the div looking for the next element node, i.e. Type 1,
which we assume is a paragraph<br>
4-6 Adds 1 to the counter. We're looking for the second paragraph.<br>
7-9 When the counter hits 2, we've reached the targeted paragraph. Change the text
Of course, if you know you might want your JavaScript to change that second paragraph,
it would be a lot easier to assign it an id, and go straight to it, like this.
