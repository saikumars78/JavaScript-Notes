# 58 The DOM

The first, getElementById, gives you access only to those components that have been assigned an id. The second, getElementsByTagName, is good for wholesale changes, but
is a bit cumbersome for fine surgical work.

Document Object Model,The DOM is an organization chart, created
automatically by the browser when your web page loads, for the whole web page. All the
things on your web page—the tags, the text blocks, the images, the links, the tables, the style
attributes, and more—have spots on this organization chart. 

1st level: document

2nd level: <html>
  
3rd level: <head>
  
4th level: <title>
  
5th level: Simple document
  
</title>
  
</head>
  
3rd level <body>
  
4th level <p>
  
5th level There's not much to this.
  
</p>
  
</body>
  
</html>

      Document
          |
         html
          |
       ___|____
      |         |
    head       body
      |         |
    title       p
      |         |
simple doc  Ther's not much to this.


In the DOM organization chart, each box represents a node.

The HTMLpage represented above, in its cleaned-up DOM form, has 8 nodes: the document node,
the html node, the head and body nodes, the title node,
one paragraph node, and two text nodes.

# 59 The DOM:Parents and children

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
  
6th level There's not much to this.
  
</p>
  
5th level <p>
  
6th level Nor to this.
  
</p>
  
</div>
  
</body>
  
</html>

         document
            |
       _____|______
      |            |
    html          head
      |            |
    title         div
      |            |
  
