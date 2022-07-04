# 62 The DOM: More ways to target elements
```
var targetNode = parentNode.childNodes[0];
```
...is the same as...
```
var targetNode = parentNode.firstChild;
<div id="div1">
<div id="div2">
<p>Chicago</p>
<p>Kansas City</p>
<p>St. Louis</p>
</div>
</div>
```
You want to know the parent of the div with the id "div2". The following code assigns the
parent of the "div2" div to the variable pNode.
```
1 var kidNode = document.getElementById("div2");
2 var pNode = kidNode.parentNode;
```
You can use nextSibling and previousSibling to target the next child and the
previous child in the collection of an element's children.
```
1 var firstEl = document.getElementById("div1");
2 secondEl = firstEl.nextSibling;
```
```
1 var firstEl = document.getElementById("div1");
2 var nonexistentEl = firstEl.previousSibling;
```
# 63 The DOM: Getting a target's name
```
1 var parent = document.getElementById("div1");
2 var target = parent.firstChild;
3 nName = target.nodeName;
```
Lines 1 and 2 target the first child of an element with the id "div1". Line 3 assigns the
node name of the target to the variable nName.
innerHTML is a property of the element node,< h2 >,in the above example.The node value is a property of the text node itself, not the parent element.
innerHTML includes all the descendants of the element, including any inner element nodes like < em > as well as text nodes. The node value includes only the characters that
comprise the single text node.

# 64 The DOM: Counting elements

The following code makes a collection of all the <li> elements and assigns the collection to the variable liElements.
```
var liElements = getElementsByTagName("li");
```
In the following code, the number of <li> elements in the collection represented by liElements
is assigned to the variable howManyLi.
