# 69 Objects
```
1 var plan1Name = "Basic";
2 var plan1Price = 3.99;
3 var plan1Space = 100;
4 var plan1Data = 1000;
5 var plan1Pages = 10;
6 var plan2Name = "Professional";
7 var plan2Price = 5.99;
8 var plan2Space = 500;
9 var plan2Data = 5000;
10 var plan2Pages = 50;
11 var plan3Name = "Ultimate";
12 var plan3Price = 9.99;
13 var plan3Space = 2000;
14 var plan3Data = 20000;
15 var plan3Pages = 500;
```
Having made all these variable assignments, you could then, for example, write this JavaScript statement...
```
alert("The cost of the " + plan2Name + "package is $" + plan2Price + " per month.");
```
...and an alert would display saying, "The cost of the Professional package is $5.99 per month."

A better way to handle the situation is to create objects with properties.<br>
The statement that creates the alert shown above, with object-property pairs replacing the simple variables.
```
alert("The cost of the " + plan2.name + " package is $" + plan2.price + " per month.");
plan2.name represents "Professional". plan2.price represents 5.99.
```
The most straightforward way to define an object and its properties is this.
```
1 var plan1 = {
2 name: "Basic",
3 price: 3.99,
4 space: 100,
5 transfer: 1000,
6 pages: 10
7 };
```
Things to notice:<br>
The code begins like any variable definition, with the keyword var, followed by the object name, and then an equal sign.<br>
But then, instead of a value, there's a curly bracket, whose twin comes at the end of the block.<br><br>
Each property begins with a name, followed by a colon, and then a value.<br>
Each property definition except the last ends with a comma.<br>
The closing curly bracket is followed by a semicolon, because of the equal sign in the first line.

# 70 Objects: Properties

To change the value of an object's number value, use a simple assignment statement, the same way you'd assign a value to a plain variable.
```
deal3.cost = 79.95;
```
To change the value of an object's number value, use a simple assignment statement, the same way you'd assign a value to a plain variable.
```
deal3.cost = 79.95;
```
You can also assign an array list to a property.
deal3.features = ["Guarantee", "Free Ship"];
Whatever the value of deal3.features was, now it's an array with the elements
"Guarantee" and "Free Ship."
You can also assign a Boolean value.
deal3.membersOnly = false;

you can create an undefined variable by not assigning it a value, you can create an
object without any properties.
var deal4 = {};
If you want to create a property now and assign it a value later, you can create it with a
value of undefined.
deal3.market = undefined;
You can delete a property of an object.
delete deal3.market;
You can check to see if a property of an object exists. The following statement tests
whether there is such a thing as deal3.market and assigns the result (true or false) to the
variable propertyExists.
propertyExists = "market" in deal3;
Things to notice:
You could use any legal variable name instead of propertyExists.
The keyword in asks, "The property market is in the object deal3—true or false?"
The property market is in quotes.
The object deal3 is not in quotes.

71
Objects:
Methods

1 var plan1 = {
2 name: "Basic",
3 price: 3.99,
4 space: 100,
5 transfer: 1000,
6 pages: 10,
7 discountMonths: [6, 7],
8 calcAnnual: function(percentIfDisc) {
9 var bestPrice = plan1.price;
10 var currDate = new Date();
11 var thisMo = currDate.getMonth();
12 for (var i = 0; i < plan1.discountMonths.length; i++) {
13 if (plan1.discountMonths[i] === thisMo) {
14 bestPrice = plan1.price * percentIfDisc;
15 break;
16 }
17 }
18 return bestPrice * 12;
19 }
20 };
Things to notice:
Except for the first line, every line of the method is identical to the code I used to create
the plain-vanilla function that we started with.
The method definition begins the same way a property definition begins, with the name
followed by a colon.
A comma ends every property definition and method definition except for the last
property or method. If you were to add a property or method below the calcAnnual
method definition, you'd need to insert a comma after the closing curly bracket of the
ca lcAnnual definition.
T he parentheses that indicate that a variable name is the name of a function come
 immediately after the keyword function. Parameters, if there are any, go inside the
parens, as in any function definition.

1 var plan1 = {
2 name: "Basic",
3 price: 3.99,
4 space: 100,
5 transfer: 1000,
6 pages: 10,
7 discountMonths: [6, 7],
8 calcAnnual: function(percentIfDisc) {
9 var bestPrice = this.price;
10 var currDate = new Date();
11 var thisMo = currDate.getMonth();
12 for (var i = 0; i < this.discountMonths.length; i++) {
13 if (this.discountMonths[i] === thisMo) {
14 bestPrice = this.price * percentIfDisc;
15 break;
16 }
17 }
18 return bestPrice * 12;
19 }
20 };
When you write this.whatever, JavaScript is smart enough to understand that you're
referring to a property of the object that's being defined—in this case, plan1.

72
Objects:
Constructors

1 var plan1 = {
2 name: "Basic",
3 price: 3.99,
4 space: 100,
5 transfer: 1000,
6 pages: 10
7 };
But that only gets us an object that represents the first plan

constructor function.
1 function Plan(name, price, space, transfer, pages) {
2 this.name = name;
3 this.price = price;
4 this.space = space;
5 this.transfer = transfer;
6 this.pages = pages;
7 }

The function name is capitalized. JavaScript doesn't care whether you do this or not, but
it's conventional to do it to distinguish constructor functions from regular functions.

Each of the parameter values is assigned to a variable. But the variable is a property
attached to some object whose name hasn't been specified yet. But don't worry. Just as the
parameter values will be filled in by the calling code, so will the name of the object.
This is the calling code that creates the object for the Basic plan.
var plan1 = new Plan("Basic", 3.99, 100, 1000, 10);

Now it's easy to mass-produce as many objects as you want, using the same pattern.
1 var plan1 = new Plan("Basic", 3.99, 100, 1000, 10);
2 var plan2 = new Plan("Premium", 5.99, 500, 5000, 50);
3 var plan3 = new Plan("Ultimate", 9.99, 2000, 20000, 500);

73
Objects:
Constructors for methods

When you attach a variable to an object, it's
called a property of the object. When you attach a function to an object, it's called a method of
the object. 

1 function Plan(name, price, space, transfer, pages, discountMonths) {
2 this.name = name;
3 this.price = price;
4 this.space = space;
5 this.transfer = transfer;
6 this.pages = pages;
7 this.discountMonths = discountMonths;
8 this.calcAnnual = function(percentIfDisc) {
9 var bestPrice = this.price;
10 var currDate = new Date();
11 var thisMo = currDate.getMonth();
12 for (var i = 0; i < this.discountMonths.length; i++) {
13 if (this.discountMonths[i] === thisMo) {
14 bestPrice = this.price * percentIfDisc;
15 break;
16 }
17 }
18 return bestPrice * 12;
19 };
20 }
Things to notice about line 8, the beginning of the method definition:
Like the property definitions above it, the line begins with the keyword this, referring to
the name of whatever object is being constructed at any given time.
The next three pieces are the same: a dot, the name of the method, and an equal sign.
The next piece is different: the keyword function.
In this case, a single parameter is inside the parentheses, percentIfDisc. This is not a
parameter that's part of the constructor. It's a parameter of the method that the constructor
will create for each object. A value is passed to it not when a new object is created using
the constructor, but when the method, having already been created along with its object
via the constructor, is called.

74
Objects:
Prototypes

1 Plan.prototype.calcAnnual = function(percentIfDisc) {
2 var bestPrice = this.price;
3 var currDate = new Date();
4 var thisMo = currDate.getMonth();
5 for (var i = 0; i < this.discountMonths.length; i++) {
6 if (this.discountMonths[i] === thisMo) {
7 bestPrice = this.price * percentIfDisc;
8 break;
9 }
10 }
11 return bestPrice * 12;
12 };
Now, all objects created with the constructor Plan will share the same copy of the
method calcAnnual. There's no unnecessary duplication.

the name of the constructor function, in this case Plan
the keyword prototype
the name of the method that all objects created with Plan will share, in this case
calcAnnual

Objects can have prototype properties as well as prototype methods. Suppose you wanted
all objects created with the Plan to share the same property, cancellable, with a value of
true. You'd code the prototype this way.
Plan.prototype.cancellable = true;

75
Objects:
Checking for properties and methods

var gotTheProperty = "price" in plan1;
Here are the parts:
the property in question, enclosed in quotes—in this case, price
the keyword in
the object, in this case, plan1

1 var listOfProperties = [];
2 for (var prop in plan1) {
3 listOfProperties.push(prop);
4 }
Line 1 declares an empty array, listOfProperties. Lines 2-4 cycle through all the
properties of plan1, adding each property (push), including any methods, to the array
listOfProperties. Using the example we've been working with, the array
listOfProperties winds up with a value of
"name,price,space,transfer,pages,discountMonths,calcAnnual".

1 var listOfProperties = [];
2 for (var prop in plan1) {
3 if (plan1.hasOwnProperty(prop)) {
4 listOfProperties.push(prop);
5 }
6 }
