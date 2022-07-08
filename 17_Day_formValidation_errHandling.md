#82 Form validation: text fields
```
<form onSubmit="return checkForLastName();">
Please enter your last name.<br>
<input type="text" id="lastNameField">
<input type="submit" value="Submit Form">
</form>
```
When the user clicks the Submit button, the function checkForLastName is called.
Here's the function.
```
1 function checkForLastName() {
2 if (document.getElementById("lastNameField").value.length === 0) {
3 alert("Please enter your last name");
4 return false;
5 }
6 }
```
Line 2 asks whether the length of the value found in the field with the id "lastNameField"
is 0. That is, is nothing entered there? If so, an alert displays asking the user to enter her name.
And then in line 4 something else happens. The Boolean value false is returned to the calling
code. This prevents the form from being submitted. In order for the submission to be called off,
there has to be a matching keyword return in the markup that calls the function. Without this
return in the calling code, the return in line 4 of the function won't stop the form from being
submitted.
```
<form onSubmit="return checkForLastName();">
```
As a user-friendly touch, you can use the focus method to place the cursor in the field
that needs to be completed.
````
1 function checkForLastName() {
2 if (document.getElementById("lastNameField").value.length === 0) {
3 alert("Please enter your last name");
4 document.getElementById("lastNameField").focus();
5 return false;
6 }
7 }
````
Repeating the document.getElementId... designation gets pretty unwieldy, so let's put
it into a variable.
```
1 function checkForLastName() {
2 var targetField = document.getElementById("lastNameField");
3 if (targetField.value.length === 0) {
4 alert("Please enter your last name");
5 targetField.focus();
6 return false;
7 }
8 }
```
giving it a yellow background color
```
1 function checkForLastName() {
2 var targetField = document.getElementById("lastNameField");
3 if (targetField.value.length === 0) {
4 alert("Please enter your last name");
5 targetField.focus();
6 targetField.style.background = "yellow";
7 return false;
8 }
9 targetField.style.background = "white";
10 }
```
# 83 Form validation: drop-downs

When the user clicks the up or down arrow to the right of SELECT A STATE, a
menu drops down. 
```
<form onSubmit="return checkForSelection();">
<select id="states">
<option value="" selected="selected">
SELECT A STATE</option>
<option value="AL">Alabama</option>
<option value="AK">Alaska</option>
<option value="AZ">Arizona</option>
<option value="AR">Arkansas</option>
</select>&nbsp;&nbsp;
<input type="submit" value="Submit Form">
</form>
```
When the Submit button is clicked, the function checkForSelection is called. Note that
once again, the keyword return precedes the function call.
Here's the function.
```
1 function checkForSelection() {
2 if (document.getElementById("states").selectedIndex === 0) {
3 alert("Please select a state.");
4 return false;
5 }
6 }
```
In the function, if selectedIndex is 0 (line 2), it means the user hasn't made a selection.
Line 3 displays an alert asking her to select. Line 4 returns false, cancelling the form
submission.

Here's the function, revised two ways. First, it accepts the element ID as a parameter,
allowing it to process more than one form. Second, the element is assigned to a variable.
```
1 function checkForSelection(selecID) {
2 var target = document.getElementById(selecID);
3 if (target.selectedIndex === 0) {
4 alert("Please select a state.");
5 return false;
6 }
7 }
```
The function coded above needs the event-handler to include the ID as an argument.
```
<form onSubmit="return checkForSelection('states');">
```
# 84 Form validation: radio buttons
```
<form onSubmit="return validateRadios();">
<input type="radio" name="r1" value="cat"> Cat<br>
<input type="radio" name="r1" value="bat"> Bat<br>
<input type="radio" name="r1" value="hat"> Hat<br>
<input type="submit" value="Submit Form">
</form>
 ``` 
Note that the radio buttons all have the same name, "r1".
This is the validating function that checks to see if the user has clicked one of the buttons.
```
1 function validateRadios() {
2 var radios = document.getElementsByName("r1");
3 for (var i = 0; i < radios.length; i++) {
4 if (radios[i].checked) {
5 return true;
6 }
7 }
8 alert("Please check one.");
9 return false;
10 }
```
Line 2 makes a collection of all the buttons with the name "r2" and assigns the collection
to the variable radios.

The function can be used to validate button sections for any number of forms if we specify
a parameter, allowing the event-handler to pass the button group name to the function.
```
1 function validateRadios(ename) {
2 var radios = document.getElementsByName(eName);
```
In order to use the function coded above, the event-handler would have to include the
button group name as an argument.
```
<form onSubmit="return validateRadios('r1');">
```
# 85 Form validation: ZIP codes
HTML gives you a way to keep her from entering too many digits: maxlength=5. But if
you want to make sure she hasn't entered too few digits, you need to use JavaScript. Here's the
function.
```
1 function validateZIP() {
2 var numChars = document.getElementById("zip").value.length;
3 if (numChars < 5) {
4 alert("Please enter a 5-digit code.");
5 return false;
6 }
7 }
```
```
1 function validateZIP() {
2 var valueEntered = document.getElementById("zip").value;
3 var numChars = valueEntered.length;
4 if (numChars < 5) {
5 alert("Please enter a 5-digit code.");
6 return false;
7 }
8 for (var i = 0; i <= 4; i++) {
9 var thisChar = parseInt(valueEntered[i]);
10 if (isNaN(thisChar)) {
11 alert("Please enter only numbers.");
12 return false;
13 }
14 }
15 }
```
The highlighted code loops through the five characters that have been entered, checking to
make sure that all the characters are string characters representing numbers. Because the five
characters in the field are string characters, each one has to be converted to a number if
possible before being tested. 

# 86 Form validation: email

Let's start by checking for spaces, which are illegal in an email address.
```
1 function validateEmail() {
2 var eEntered = document.getElementById("email").value;
3 if (eEntered.indexOf(" ") !== -1) {
4 alert("No spaces allowed in address");
5 return false;
6 }
7 }
```
Line 3 is the key here. If the index of the illegal space character is anything other than -1,
it means the character is in there somewhere, and an alert displays.

In an email address you want to see the @ sign at least one character from the beginning
of the string and no closer to the end of the string than 5 characters away. Here's a line that
adds this test to the example function.
```
1 function validateEmail() {
2 var addressIsLegal = true;
3 var eEntered = document.getElementById("address").value;
4 if (eEntered.indexOf(" ") !== -1) {
5 addressIsLegal = false;
6 }
7 if (eEntered.indexOf("@") < 1 || eEntered.indexOf("@") > eEntered.length - 5) {
8 addressIsLegal = false;
9 }
10 if (addressIsLegal === false) {
11 alert("Please correct email address");
12 return false;
13 }
14 }
```
About line 7: The first part, left of the pipes, tests whether the character is at the
beginning of the address, which would be illegal. The second part, right of the pipes, tests
whether there are fewer than 4 characters following the character. Since there must be at least
one character for the domain name plus a dot plus at least two characters for the extension,
fewer than 4 characters following the @ would be illegal.

Finally, I'll add a test for the dot that needs to be at least 1 character away from the "@"
and have 2 to 4 characters following it.
```
1 function validateEmail() {
2 var addressIsLegal = true;
3 var eEntered = document.getElementById("address").value;
4 if (eEntered.indexOf(" ") !== -1) {
5 addressIsLegal = false;
6 }
7 if (eEntered.indexOf("@") < 1 || eEntered.indexOf("@") > eEntered.length - 5) {>
8 addressIsLegal = false;
9 }
10 if (eEntered.indexOf(".") - eEntered.indexOf("@") < 2 ||
eEntered.indexOf(".") > eEntered.length - 3) {
11 addressIsLegal = false;
12 }
13 if (addressIsLegal === false) {
14 alert("Please correct email address");
15 return false;
16 }
14 }
```
Line 10: There must be at least one character between the dot and the @. The first part,
left of the pipes, tests whether that one character (or more) is missing, which would be illegal.
There must also be at least 2 characters following the dot. The second part, right of the pipes,
tests whether there are fewer than 2 characters following the character, which would be
illegal.
```
1 function greetWorld() {
2 try {
3 var greeting = "Hello world!";
4 aler(greeting);
5 }
6 catch(err) {
7 alert(err);
8 }
9 }
```
The original operational code is wrapped in the try block. The mis-formed aler causes
a JavaScript error, which is passed to the catch block. An alert displays the error that caused
the problem.

Note that try and catch are always paired. Without try, an error won't trigger catch.
Without catch, JavaScript won't know what to do when it throws an error.
Some more things to keep in mind:<br>
The code inside the try and the catch blocks is wrapped in curly brackets.
The functional code inside the try block is indented.<br>
The error parameter, in this case err, can take any legal variable name.<br>
In this example, an alert displays when an error occurs. But you could do something else.<br>
The try and catch pair have limited usefulness. For example, in the example above, if
you omit a parenthesis, bracket, or quotation mark, or if you have too many of them, no alert
will display. The code will just break, and nothing will happen. The try and catch approach
is useful mainly for spotting variables that haven't been defined or, as in this case, errors that
JavaScript interprets as variables that haven't been defined.

# 88 Exceptions: throw
```
<form onSubmit="return checkPassword();">
Enter a password<br>
(8-12 characters, at least 1 number, no spaces)<br>
<input type="text" id="f1">
<input type="submit" value="Submit">
</form>
```
This is the function that tests whether the user's input has met the requirements. If not, the
function displays an alert.
```
1 function checkPassword() {
2 try {
3 var pass = document.getElementById("f1").value;
4 if (pass.length < 8) {
5 throw "Please enter at least 8 characters.";
6 }
7 if (pass.indexOf(" ") !== -1) {
8 throw "No spaces in the password, please.";
9 }
10 var numberSomewhere = false;
11 for (var i = 0; i < pass.length; i++) {
12 if (isNaN(pass(i, i+1)) === false) {
13 numberSomewhere = true;
14 break;
15 }
16 }
17 if (numberSomewhere === false) {
18 throw "Include at least 1 number.";
19 }
20 }
21 catch(err) {
22 alert(err);
23 }
24 }
```
# 89 Handling events within JavaScript
  ```
<input type="button" value="Click" onClick="sayHello();">
  ```
We're going to remove the highlighted part of the markup above, and we're going to add
an id.
```
<input type="button" value="Click" id="button1">
```
Here's the JavaScript code that handles the event.
```
1 var b1 = document.getElementById("button1");
2 b1.onclick = sayHello;
```
Line 1 assigns the element to the variable b1. Line 2 watches for the element to be
clicked. When that happens, it calls the function sayHello.
Things to notice:<br>
Unlike the camelCase used for inline event-handling, the event name must be alllowercase or it won't work. It's onclick not onClick, onfocus not onFocus, onsubmit
not onSubmit<br>
Unlike inline event-handling, the function name following the equal sign isn't in quotes.
Unlike inline event-handling, there are no parentheses following the function name.<br>

If you wanted, you could condense it into a single statement by writing...
```
document.getElementById("button1").onclick = sayHello;
```
The function code is the same whether you use inline or scripted event-handling. For
example:
```
1 function sayHello() {
2 alert("Hi there.");
3 }
```
This code calls a function that swaps one image for another when the user mouses over
the original image.
```
1 var targetImg = document.getElementById("i12");
2 targetImg.onmouseover = swapPic;
```
This code calls a function that validates an email address when a form is submitted.
```
1 var emailFrm = document.getElementById("form5");
2 emailFrm.onsubmit = valEmail;
```

