# 55 Setting styles

The text inside the element gets bigger.

1 function makeBig() {

2 document.getElementById("p1").className += " big";

3 }

There's another way to specify style properties.

1 function makeBig() {

2 document.getElementById("p1").style.fontSize = "2em";

3 }

The function changes the default font size of an element with the id "p1".

This statement left-floats an image.

document.getElementById("pic99").style.cssFloat = "left";

This statement makes an element invisible.

document.getElementById("div9").style.visibility = "hidden";

This statement gives an element left and right margins of 10 pix.

document.getElementById("mainPic").style.margin = "0 10px 0 10px;";

# 56 Target all elements by tag name

var par = document.getElementsByTagName("p");

The variable, par, now holds an array-like collection of all the paragraphs in the
document.

<p>This bed is too small.</p>

<p>This bed is too big.</p>

<p>This bed is just right.</p>

par[0] is the first paragraph. par[1] is the second paragraph. par[2] is the third paragraph. par.length is 3, the number of items in the collection.

If you write...

var textInMiddleParagraph = par[1].innerHTML;

...the variable textInMiddleParagraph is assigned "This bed is too big."

If you write...

par[1].innerHTML = "This SUV is too big."; //the paragraph text changes to "This SUV is too big.

This statement makes a collection of all the images in the document and assigns it to the variable pics.

var pics = document.getElementsByTagName("img");

This statement makes a collection of all the divs in the document and assigns it to the variable divs.

var divs = document.getElementsByTagName("div");

This statement makes a collection of all the unordered lists in the document and assigns it to the variable ulists.

var ulists = document.getElementsByTagName("ul");

# 57 Target some elements by tag name

1 var e = document.getElementByID("rules");

2 var paragraphs = e.getElementsByTagName("p");

Line 1 assigns the div with the id "rules" to the variable e.

Line 2 makes a collection of all the paragraphs in the div and assigns the collection to the variable paragraphs.

1 var t = document.getElementById("table9");

2 var cells = t.getElementsByTagName("td");

3 for (var i = 0; i < cells.length; i++) {

4 cells[i].style.backgroundColor = "pink";

5 }

Here's the line-by-line breakdown.

1. Targets the table by its id

2. Assembles a collection of all the elements in the table with a td tag

3-5. Loops through all of them to change their background color
