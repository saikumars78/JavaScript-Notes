# 45 Events: link

A good website is a responsive website.<br>

Clicking a button, moving the mouse, moving from one field to another in a form, selecting a different option—are known as events. JavaScript code that
responds to an event—for example, displaying a guarantee or swapping an image when the pointer hovers over it—is called an event handler.<br>
most straightforward approach to event-handling—inline event-handling.<br>

Inline event-handling means that you combine bits of JavaScript with HTML markup.Here's a line that displays a link and then displays an alert when the user clicks it.
```
<a href="#" onClick="alert('Hi');"> Click </a>
```
As an HTML coder, you're familiar with the beginning and end of this markup,< a href = and > Click </a>.

Let's break it down.<br>
When the user clicks the link, you don't want a new webpage to be loaded in this case, so,instead of a URL, you place a # inside the quotation marks. This tells the browser to reload the current page.

onClick= says, "When the button is clicked, execute the following JavaScript." onClick isn't case-sensitive. You could write onclick, ONCLICK, or OnClIcK and it would work.But the convention is onClick, so we'll stick with that.

A JavaScript statement (or more than one), enclosed in quotes, follows. When the user clicks the link, it executes.

# 46 Events: button
```
<input type="button" value="Click" on Click="alert('Hello world!');">
```
The event handler is the same, whether you're coding a link or a button:
onClick="alert('Hello world!');"

As an HTML coder you know that you can use an image as a hot link. The markup would
look something like this.
```
<a href="summary-page.html"> <img src="button-sum-pg.png"></a>
```
when the user clicks an image, an alert pops up. This is the code. Note that the code for the inline event handler is the same as before.
```
<img src="button-greet.png" onClick="alert('Hello world!');">
```
# 47 Events: mouse
```
<img src="before-pic.jpg"  onMouseover="src='after-pic.jpg' ">
It begins as a plain vanilla image tag: <img src="before-pic.jpg"> <br>
```
Then comes the event-handling keyword. The keyword is in camelCase—optional but widely used: onMouseover.<br>

An equal sign follows the keyword onMouseover, just as it does with onClick. Then comes the response to the event, which is in quotes: "src='after-pic.jpg'">
inline code that displays an alert when a heading is moused over.
```
<h1 onMouseover="alert('Be sure to get your shopping done today.');">World Ends Tomorrow</h1```>
```
CSS color-change on hover.
```
<a href="index.html" onMouseover="this.style.color='green';">Home Page</a>
```
combining the onMouseover event handler with the onMouseout event handler.
```
<img src="before-pic.jpg"  onMouseover="src='after-pic.jpg'"  onMouseout="src='before-pic.jpg'">
```
# 48 Events: fields

When the user clicks in the field to type her entry, the field turns yellow.<br>
Email:<br>
```
<input type="text" size="30" onFocus="this.style.backgroundColor='yellow';">
```
Once again, I'm showing you the not-recommended inline way to handle an event, using it as a stepping stone for learning more professional event-handling later in the book.<br>

The keyword here is onFocus.The syntax is the same as for other event handlers that you've already learned to code: a keyword, followed by an equal sign, followed by JavaScript or HTML in quotes.<br>

when this field no longer has the focus—you want it to revert to a white background. You do this with the onBlur keyword, which is the opposite of onFocus.<br>
Email:<br>
```
<input type="text" size="30" onFocus="this.style.backgroundColor='yellow';"onBlur="this.style.backgroundColor='white';">
```
