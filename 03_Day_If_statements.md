# 10.if Statements

```
var x = prompt("Where does the Pope live?");
if (x === "Vatican") {
alert("Correct!");
}
```

The condition is enclosed in parentheses.<br>
If the condition tests true, something happens.<br>
The first line of an if statement ends with an opening curly bracket. An entire if statement ends with a closing curly bracket on its own line. Note that this is an exception to the rule that a statement ends with a semicolon.

# 11.Comparison operators
```
===
```
It's a type of comparison operator, specifically an equality operator.<br>
When you're comparing strings, the equality operator is case-sensitive."Rose" does not equal "rose."<br>
Another comparison operator, !==, is the opposite of ===. It means is not equal to.

Examples:
```
if (fullName === "Mark" + " " + "Myers") {
if (fullName === firstName + " " + "Myers") {
if (fullName === "firstName + " " + lastName) {
if (totalCost === 81.50 + 135) {
if (totalCost === materialsCost + 135) {
if (totalCost === materialsCost + laborCost) {
```
# 12 if...else and else if statements

if...else
```
1 var correctAnswer = "Vatican";
2 if (x === correctAnswer) {
3 alert("Correct!");
4 }
5 else {
6 score--;
7 userIQ = "problematic";
8 alert("Incorrect");
9 }
```
else if is used if all tests above have failed and you want to test another condition.
```
1 var correctAnswer = "Vatican";
2 if (x === correctAnswer) {
3 alert("Correct!");
4 }
5 else if (x === "Rome") {
6 alert("Incorrect but close");
7 }
8 else {
9 alert("Incorrect");
10}
```

# 13.Testing sets of conditions

Operator && (AND) checks all conditions and determines if all condition is true or not.

Operator || (OR) checks all conditions and determines if any condition is true or not.

Example:

weighs more than 300 pounds and runs 40 yards in under 6 seconds? You're going to invite him to try out
```
1 if (weight > 300 && time < 6) {
2 alert("Come to our tryout!");
3 }
4 else {
5 alert("Come to our cookout!");
6 }
```
# 14.if statements nested

Check out this code.
```
1 if ((x === y || a === b) && c === d) {
2 g = h;
3 }
4 else {
5 e = f;
6 }
```
In the code above, if either of the first conditions is true, and, in addition, the third condition is true, then g is assigned h. Otherwise, e is assigned f.<br>
There's another way to code this, using nesting.
```
1 if (c === d) {
2 if (x === y) {
3 g = h;
4 }
5 else if (a === b) {
6 g = h;
7 }
8 else {
9 e = f;
10 }
11 }
12 else {
13 e = f;
14 }
```
