# 35 Functions

A function is a block of JavaScript that robotically does the same thing again and again,whenever you invoke its name. It saves you repetitive coding and makes your code easier to
understand.
```
1 function tellTime() {
2 var now = new Date();
3 var theHr = now.getHours();
4 var theMin = now.getMinutes();
5 alert("Current time: "+ theHr + ":" + theMin);
6 }
```
The time-telling code—the code that creates the Date object, extracts the time, formats it,and displays an alert—is exactly the same code we started with, but is now packaged as a function. Here are the parts:

1. On line 1 an opening declaration statement that includes:<br>
• the keyword function<br>
• a name I made up for the function<br>
• parentheses that identify it as a function<br>
• an opening curly bracket to enclose the code that will execute<br>

2. On lines 2 through 5 the same block of code that you saw before executes, but it's indented for clarity. Opinions vary on how much to indent.Its better to indent 2 spaces.<br>
3. On line 6 a closing curly bracket on its own line to enclose the code that will execute<br>
Again, note that the calling code—the code that invokes the function—does nothing morethan state the name of the function including its parentheses.<br>
tellTime();

# 36 Functions:Passing them data
```
1 function greetUser() {
2 alert("Hello, there.");
3 }
```
If you put some data inside the parentheses, you can pass that data to the function that it'll use when it executes.<br>
Suppose, instead of writing greetUser(); you write..
```
greetUser("Hello, there.");
```
Now, instead of just calling the function, you're calling it and passing data to it.The string inside the parentheses, i.e. the data you're passing, is called an argument
```
1 function greetUser(greeting) {
2 alert(greeting);
3 }
```
So now we've filled the parentheses of both the calling code and the function definition.The parentheses of the calling code contain an argument. In the example, the argument is the string "Hello, there." And, as you can see in the example above, the parentheses of the function definition now contain a variable, greeting.<br>
A variable inside the parentheses in a function statement is known as a parameter.<br>
First, here's the function.
```
1 function showMessage(m, string, num);
2 alert(m + string + num);
3 }
```
Now here's the statement that calls the function.
```
1 var month = "March";
2 showMessage(month, "'s winner number is ", 23);
```
# 37 Functions:Passing data back from them
```
1 function calcTot(merchTot) {
2 var orderTot;
3 if (merchTot >= 100) {
4 orderTot = merchTot;
5 }
6 else if (merchTot < 50.01) {
7 orderTot = merchTot + 5;
8 }
9 else {
10 orderTot = merchTot + 5 + (.03 * (merchTot - 50));
11 }
12 return orderTot;
13 }
```
# 38 Functions:Local vs. global variables

A global variable is one that's declared in the main body of your code—that is, not inside a function.<br>
A local variable is one that's declared inside a function. It can be either a parameter of the function, which is declared implicitly by being named as a parameter, or a variable declared explicitly in the function with the var keyword.<br>
The difference between global and local variables. Some variables have global scope, which makes them global variables.
Other variables have local scope, which makes them local variables. 

Global variables:<br>
Declared in the main code.<br>
Known everywhere,useable everywhere.

Local variables:<br>
Declared in a function.<br>
Known only inside the function,useable only inside the function.

First, in the main code:
```
1 var theSum = 1000;
2 addNumbers();
```

Then in the function:
```
1 function addNumbers() {
2 var theSum = 2 + 2;
3 }
```
