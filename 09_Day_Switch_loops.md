# 39 switch statements: How to start them
```
1 switch(dayOfWk) {
2 case "Sat" :
3 alert("Whoopee");
4 break;
5 case "Sun" :
6 alert("Whoopee");
7 break;
8 case "Fri" :
9 alert("TGIF!");
10 break;
11 default :
12 alert("Shoot me now!");
13 }
```
just focus on just the first three lines of the code above.

1. Begins with the keyword switch. Bumping up against it is the variable that's being tested,inside parentheses. Then there's an opening curly bracket.<br>
2. The first possibility, that the variable dayOfWeek has the value "Sat". Begins with the keyword case. Then the value that is being tried, "Sat". Then a space and a colon.<br>
3. The statement that executes if the test passes—if dayOfWeek does, in fact, have the value "Sat". This statement is indented. Any number of statements can execute if the test passes.

# 40 switch statements: How to complete them

just observe these lines in above example
```
11 default :
12 alert("Shoot me now!");
13 }
```
The keyword default works like else in an if...else statement. The code that follows it executes if none of the conditions above it are met.<br>
A do...while loop accomplishes almost the same task as a while loop.
```
1 var i = 0;
2 do {
3 alert(i);
4 i++;
5 } while (i <= 3);
```
# 42 do...while loops

The differences between the two types of loops:<br>
Instead of while, the keyword do leads off the statement.<br>
The while clause, including the loop-limiting code inside the parentheses, moves to the bottom—after the closing curly bracket.<br>
Note that the while clause ends with a semicolon.<br>
Functionally, the difference between a while loop and a do...while loop is that it's possible to code a while statement whose block of instructions never execute. 

# 43 Placing scripts

JavaScript code doesn't care where it lives.<br>
All of your JavaScript functions,for example, are loaded into memory when the page loads. Wherever the code maybe, the browser finds it and stores it by the time the page is finished loading. Once the page is loaded, all the JavaScript code stays in memory, ready to execute, for as long as the page is displayed.<br>
Generally, the best place for scripts, though, is at the end of the body section.enclose the JavaScript code between <script> and </script>.
```
1 <script>
2 function sayHi() {
3 alert("Hello world!");
4 }
5 function sayBye() {
6 alert("Buh-bye!");
7 }
8 </script>
```
What makes a JavaScript file a JavaScript file is its file extension: .js. The front end of the file name is up to you, as long as it's legal. Any of these would be fine.<br>

Examples: 
```
script.js
app.js
```
Include a JavaScript file in an HTML file the same way you include an external CSS file—with an opening and closing tag.
```
<script src="whatever.js"></script>
```
# 44 Commenting

Comments are for the human, not the machine.They help you and others understand your code when it comes time to revise.You can also use commenting to comment out portions of your code for testing and debugging.!<br>
In HTMLthere's only one way to mark text as a comment. You write <!-- to open and --> to close. And in CSS there's only one way to mark text as a comment. You write /* to open and */ to close.But in Javascript there are two ways mark text as a comment.<br>
The first way is to mark a single line as a comment, as in line 1 here.
```
1 // This is a comment, ignored by the browser
2 for (var i = 0; i
3 if (animals[i] === "bat") {
4 animals[i] = "cat";
5 }
6 }
```

You can write as many lines of comments as you like. Every line must begin with the two slashes.<br>
// Each comment line must begin with a pair<br>
// of slashes, like this. (Most code editors,<br>
// by the way, are smart enough to recognize<br>
// comments and render them in a different<br>
// color so they're easy for you to<br>
// distinguish from code.)

When you comment with slashes, there's no closing tag, because the end of the line closes the comment automatically.<br>
JavaScript multi-line comment tags are the same as CSS comment tags. Open with /*.Close with */.
