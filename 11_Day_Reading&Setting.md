# 49 Reading field values
```
<form>
Email:
<input type="text">
<input type="submit" value="Submit">
</form>
```
So now in our stripped-down form markup, we've got these three elements:<br>
1.The text "Email"<br>
2. The text field for the user's email address<br>
3. The submit button<br>

I'm going to give the email field an id.<br>
```
<form>
Email:
<input type="text" id="email">
<input type="submit" value="Submit">
</form>
```
Next,add an event-handler, using the keyword onSubmit.
```
<form onSubmit="checkAddress('email');">
Email:
<input type="text" id="email">
<input type="submit" value="Submit">
</form>
```
Now, when the user clicks the submit button, the function checkAddress executes. Note that, even though the action is a click on the submit button, the onSubmit event handler is in the form tag, not in the submit button tag. That's because the submission is an event that
applies to the whole form, not the submit button.

The code for the function.
```
1 function checkAddress(fieldId) {
2 if (document.getElementById(fieldId).value === "") {
3 alert("Email address required.");
4 }
5 }
```
This is the sequence you need to memorize:
1. The keyword document, followed by...
2. a dot, followed by...
3. the keyword getElementById, followed by...
4. the parameter, in parens, received from the calling code, fieldId,followed by...
5. another dot, followed by...
6. the keyword value

# 50 Setting field values

When the user clicks out of the ZIP field, the onBlur event triggers the fillCity function. This is the code.
```
1 function fillCity() {
2 var cityName;
3 var zipEntered = document.getElementById("zip").value;
4 switch (zipEntered) {
5 case "60608" :
6 cityName = "Chicago";
7 break;
8 case "68114" :
9 cityName = "Omaha";
10 break;
11 case "53212" :
12 cityName = "Milwaukee";
13 }
14 document.getElementById("city").value = cityName;
15 }
```
# 51 Reading and setting paragraph text
```
<p id="slowLoris">Slow lorises are a group of several species of strepsirrhine primates which make up the genus Nycticebus.
<a href="javascript:void(0);" onClick="expandLoris();"><em>Click for more.</em></a></p>
```
An id is assigned to the paragraph, which will be used by the function. When the user clicks the link, a function, expandLoris, is called.

This is the function.
```
1 function expandLoris() {
2 var expandedParagraph = "Slow lorises are a group of several species of trepsirrhine primates which make up the genus Nycticebus. They have a round head, narrow snout, large eyes, and a variety of distinctive coloration patterns that are species-dependent. The hands and feet of slow lorises have several adaptations that give them a pincer-like grip and enable them to grasp branches for long periods of time.Slow lorises have a toxic bite, a rare trait among mammals.";
3 document.getElementById("slowLoris").innerHTML = expandedParagraph;
4 }
```
Line 2 assigns the long version of the text to a variable. Then, identifying the paragraph by its id, line 3 replaces the original content, the innerHTML, with the text stored in the variable.<br>

This is the function that loads the list markup into the div, which has been given an id of"lorisList".
```
1 function placeAList() {
2 var listToPlace = "<ol><li>Slow loris</li><li>Fast loris</li><li>Just-right loris</li></ol>";
3 document.getElementById("lorisList").innerHTML = listToPlace;
4 }
```
Line 2 assigns all the HTML for the list to a variable. Line 3 places the HTML into the div that has been assigned the id "lorisList".

document.getElementById(element id).innerHTML to read as well as "write" the contents of an element. 

# 52 Manipulating images and text

lets begin by giving the image an id.
```
<img src="Blobfish.jpg" id="ugly"...
```
Then add an event handler.
```
<img src="blobfish.jpg" id="ugly" onClick="makeInvisible();">
```
We have a CSS class for invisibility.

.hidden {display:none;}

The function called by the event handler gives the image a class of "hidden," so it disappears.
```
1 function makeInvisible() {
2 document.getElementById("ugly").className = "hidden";
3 }
```
Some things to keep in mind:

This is just a variation on things you've already learned,document.getElementById(theElementId).value (for form fields) and
document.getElementById(theElementId).innerHTML (for paragraphs, divs, and other HTML elements).

It's className, in camelCase, not class.

Assigning a class to an element this way replaces any classes that the element has been assigned in the static markup.
```
1 function makeBig() {
2 document.getElementById("p1").className += " big";
3 }
```
Compared with the code that replaces all the existing classes with a new one, this code has two small differences.

It's += instead of just =.

A space before the class name is required.

# 53 Swapping images
```
<img src="before-pic.jpg" onMouseover="src='after-pic.jpg'">
```
Another way to do it is to call a function that makes the swap. This is the markup:
```
<img src="before-pic.jpg" id="before" onMouseover="swapPic();">
```
This is the function code.
```
1 function swapPic() {
2 document.getElementById("before").src = "after-pic.jpg";
3 }
```
# 54 Swapping images and setting classes
```
1 function swapPic() {
2 document.getElementById("before").src = "after-pic.jpg";
3 }
```
A more common way to code the function is to break it into two steps, first assigning document.getElementById("before") to a variable. Then you combine that variable with
.src. Let's call it the verbose approach.
```
1 function swapPic() {
2 var pic = document.getElementById("before");
3 pic.src = "after-pic.jpg";
4 }
```
