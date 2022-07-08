# 76 Browser control: Getting and setting the URL

you can get the browser to tell you its current location.
```
var whereWeAt = window.location.href;
```
This statement gets just the domain name.
```
var theDomain = window.location.hostname;
```
To get the path.
```
var thePath = window.location.pathname;
```
As usual, you can reverse the order of things, telling the browser where to go instead of asking where it is.
```
window.location.href = "http://www.me.com/1.html";
window.location.href = "http://www.me.com";
window.location.href = "http://www.me.com";
```
```
1 var currentSite = window.location.hostname;
2 var destination = "http://" + currentSite + "/wow.html";
3 window.location.href = destination;
```
Here's the line-by-line breakdown:
1. Gets the domain name and assigns it to the variable currentSite. Example: www.me.com
2. Concatenates the string "http://" with the domain name plus the destination page and assigns the combo to the variable destination
3. Directs the browser to the destination

This is how to direct the browser to an anchor on the current page.
```
1 var currentSite = window.location.hostname;
2 var currentPath = window.location.pathname;
3 var destination = "http://" + currentSite + currentPath + "#humidifier";
4 window.location.href = destination;
```
Here's the breakdown:
1. Gets the domain name and assigns it to the variable currentSite. Example:
www.me.com
2. Gets the pathname and assigns it to the variable currentPath. Example: /1.html
3. Concatenates the string "http://" with the domain name, the destination page, and the
desired anchor and assigns the combo to the variable destination
4. Directs the browser to the destination

# 77 Browser control: Getting and setting the URL another way

In the last chapter you learned to direct the browser to a new URLby assigning a string to window.location.href. Here's another way to do the same thing.
```
window.location.assign("http://www.me.com");
```
The statement directs the browser to the home page of me.com.
As with the window.location.href statement, you can make the URL as detailed as you
like.
```
window.location.assign("http://www.me.com/lojack.html#guarantee");
```
The statement directs the browser to the anchor #guarantee on the lojack.html page of the site me.com.
Here's another alternative that has a slightly different effect.
```
window.location.replace("http://www.me.com/lojack.html#guarantee");
```
Once again, the statement directs the browser to a new URL. But by using replace instead of assign, you interfere with the browser history. When you use assign, the history is intact. The statement takes the user away from the original page, to the new page. If, afterarriving at the new page, she presses the Backspace key or clicks the browser's back button she goes back to the original page that she just came from. But when you use replace, the original page doesn't make it into the history. If the user presses Backspace after being taken to the new page, she's taken to the page that displayed before the original page since the original page is no longer in the history. If there is no page before the original page, nothing happens when she presses Backspace.

To reload the current page code one of these statements:
```
window.location.reload(true);
window.location.reload(false);
window.location.reload();
```
# 78 Browser control: Forward and reverse
You can make the browser go back one URL in the browser history, as if the user has
pressed the Backspace key or clicked the browser's back button.
```
history.back();
```
To make the browser go forward in the history, as if the user has pressed alt-right-arrow or clicked the browser's forward button...
```
history.forward();
```
You can tell the browser how many steps in the history you want to take, using negative
numbers to go back and positive numbers to go forward. The following statement is the
equivalent of pressing the Backspace key three times.
```
history.go(-3);
```
The following statement sends the browser forward two URLs.
```
history.go(2);
```
# 79 Browser control:
```
Filling the window with contentvar monkeyWindow = window.open();
```
The code above opens a blank window of maximum size and gives it a handle, a variable that refers to this particular window

There are three ways to fill a new window with content, You can use the write method to put HTML content on the screen...
```
1 var monkeyWindow = window.open();
2 var windowContent = "<h1>Capuchin monkey</h1><img src= 'monkey.jpg'><p>The word capuchin derives from a
group of friars<br>named the Order of Friars Minor Capuchin who wear<br>brown
robes with large hoods covering their heads.</p>";
3 monkeyWindow.document.write(windowContent);
```
Here's the line-by-line breakdown:
1. Opens a new window and assigns it the handle monkeyWindow
2. Assigns text to the variable windowContent
3. Fills the window with the text

Things to notice:<br>
Inside the main quotes that enclose the whole string, any quoted text must be in single
quotes, as in < img src='monkey.jpg'>.<br>
Using the document.write method, you place the HTML string on the page. You
designate the window by its handle, the variable that you declared when you opened the
window.<br>
The document.write method in this example is used to fill an empty window with
content. You could also use it to write to a window that already has content. But it will
overwrite all the HTML of the original document, replacing its content entirely.<br>
Instead of assigning the HTML string to a variable and specifying the variable inside the
parentheses, you could just put the HTML string inside the parentheses, enclosed in
quotes of course. But this would be even more unwieldy than the example code.<br>

The second way to fill the window with content is to assign a document to it, as you
learned to do in previous chapters.<br>
```
monkeyWindow.location.assign("http://www.animals.com/capuchin.html");
```
...or...
```
monkeyWindow.location.href = "http://www.animals.com/capuchin.html";
```
The third and most common way to fill the window with content is to include the
document assignment in the statement that opens the window.
```
var monkeyWindow = window.open("http://www.animals.com/capuchin.html");
```
If the document you're opening in the popup shares the same host and directory as the
original document, you can just write...
```
var monkeyWindow = window.open("capuchin.html");
```
This is how you close a window.
```
monkeyWindow.close();
```

# 80 Browser control: Controlling the window's size and location

You also learned to open a window with a single parameter—a URL.<br>
A second parameter that you can include is a window name.
```
var monkeyWindow = window.open("monk.html", "win1");
```
In the statement above, the second item in the parentheses, "win1", is the name.

Things to know:<br>
The name, used in HTML, is not the handle. The handle is used in JavaScript statements
that write to the window, assign a URL to it, or close it. The handle is the variable that
precedes the equal sign.<br>
The name is in quotes.<br>
The name is separated from the URL by a comma followed by a space.<br>
The name itself can't have spaces in it.<br>

You can specify a URLparameter without a name parameter, but you can't specify a name
parameter without a URL parameter. But it is okay to specify an empty URL parameter, like
this.
```
var monkeyWindow = window.open("", "win1");
```
Often, you'll want to specify a window size.
```
var monkeyWindow = window.open("monk.html", "win1", "width=420,height=380");
```
Things to know:<br>
Both parameters, width and height, are enclosed by a single set of quotation marks.
The absence of spaces within the quotation marks isn't a mere style preference but a
requirement. Any spaces here will break JavaScript.<br>
The numbers refer to pixels. In the example above, the window will be 420 pixels wide
259
and 380 pixels high.<br>
Width and height must be a minimum of 100.<br>
Unlike the URL and name parameters, the order doesn't matter. Width can come before
height, height can come before width. But the width-and-height set must come third, after
URL and name.<br>
In order to specify these parameters, you must specify a URL and name, even if you
specify empty strings.<br>
A window that's smaller than the screen will display in the upper-left corner of the
screen. But you can optionally tell the browser where to place the window.<br>
```
ar w = window.open("", "", "width=420,height=380,left=200,top=100");
```
Things to know:<br>
Again, the numbers are pixels—number of pixels from the left edge of the screen and
number of pixels from the top of the screen.<br>
The positioning parameters are included within the same set of quotation marks as the
size parameters, and, like the size parameters, are separated by a comma and no space.
The parameter order within the quotation marks doesn't matter.<br>
You can specify window size without specifying window position, but if you specify
window position without size, it will be ignored since it will be a full-size window that
fills the whole screen.<br>

# 81 Browser control: Testing for popup blockers

Popup blockers are now a standard feature of browsers, with some level of popup
blocking usually built in as a default
```
1 function checkForPopBlocker() {
2 var testPop = window.open("", "","width=100,height=100");
3 if (testPop === null) {
4 alert("Please disable your popup blocker.");
5 }
6 testPop.close();
7 }
Here's the line-by-line breakdown:
2 Attempts to open a tiny window
3-4 If the handle is assigned null, meaning the window couldn't open, an alert displays
6 Closes the window
```
```
1 function checkForPopBlocker() {
2 var testPop = window.open("", "","width=100,height=100");
3 if (testPop === null || typeof(testPop === "undefined") {
4 alert("Please disable your popup blocker.");
5 }
6 testPop.close();
7 }
```
Normally, you'd run the test when the page loads.
```
<body onLoad ="checkForPopBlocker();">
```
