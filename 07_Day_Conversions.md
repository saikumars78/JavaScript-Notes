# 28 Converting strings to integers and decimals
```
1 var currentAge = prompt("Enter your age.");
2 var yearsEligibleToVote = currentAge - 18;
```
In the above code, the value assigned to the variable currentAge is a string, because it comes from a user's prompt response. But in line 2, when the variable appears in an arithmetic expression, the value is automatically (and temporarily) converted to a number to make the math work.
```
var profit = "200" - "150"; //50
var profit = "200" - "duck"; 
```
an alert will display saying "NaN" meaning "not a number." 

# 29 Converting strings to numbers, numbers to strings

The following code converts the string "24" to the number 24.
```
1 var integerString = "24"
2 var num = Number(integerString);
```
The following code converts the string "24.9876" to the number 24.9876.
```
1 var floatingNumString = "24.9876";
2 var num = Number(floatingNumString);
```
Converting a number to a string, perhaps so you can format it, is straightforward.
```
1 var numberAsNumber = 1234;
2 var numberAsString = numberAsNumber.toString();
```
The code above converts the number 1234 to the string "1234" and assigns it to the variable numberAsString.

# 30 Controlling the length of decimals
```
var prettyTotal = total.toFixed(2);
```
The statement above rounds the number represented by total to 2 places and assigns the result to the variable prettyTotal. The number inside the parentheses tells JavaScript how many places to round the decimal to.

Now add a dollar sign, and you're all set.
```
var currencyTotal = "$" + prettyTotal;
``` 
To shorten a number to no decimals, leave the parentheses empty.
```
var prettyTotal = total.toFixed();
```
# 31 Getting the current date and time
```
var rightNow = new Date(); //creates something called a Date object.
var dateString = rightNow.toString();
```
Below example extracts the day of the week, and assigns the day of the week to the variable theDay.
```
1 var rightNow = new Date();
2 var theDay = rightNow.getDay();
```
Example:
```
1 var dayNames = ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"];
2 var now = new Date();
3 var theDay = now.getDay();
4 var nameOfToday = dayNames[theDay];
```
Here's what's going on:

1. Creates an array of days starting with "Sun" and assigns it to dayNames.
2. Creates a new Date object and assigns it to now.
3. Extracts the day of the week as aa number and assigns it to theDay.
4. Uses the day number as an index to specify the correct array element, i.e. the day name.

# 32 Extracting parts of the date and time
```
1 var d = new Date();
2 var currentMonth = d.getMonth();
```
getDate gives you a number for the day of the month.
```
var dayOfMonth = d.getDate();
```
getFullYear gives you a 4-digit number for the year.
```
var currYr = d.getFullYear();
```
getHours gives you a number from 0 through 23 corresponding to midnight through 11 p.m.
```
var currentHrs = d.getHours();
```
getMinutes gives you a number from 0 through 59.
```
var currMins = d.getMinutes();
```
getSeconds gives you a number from 0 through 59.
```
var currSecs = d.getSeconds()
```
getMilliseconds gives you a number from 0 through 999.
```
var currMills = d.getMilliseconds();
```
getTime gives you the number of milliseconds that have elapsed since midnight, Jan. 1,1970.

var millsSince = d.getTime();

# 33 Specifying a date and time
```
1 var today = new Date();
2 var doomsday = new Date("June 30, 2035");
3 var msToday = today.getTime();
4 var msDoomsday = doomsday.getTime();
5 var msDiff = msDoomsday - msToday;
6 var dDiff = msDiff / (1000 * 60 * 60 * 24);
7 dDiff = Math.floor(dDiff);
```
or
```
1 var msDiff = new Date("June 30, 2035").getTime() - new Date().getTime();
2 var daysTillDoom = Mathfloor(msDiff / (1000 * 60 * 60 * 24));
```
# 34 Changing elements of a date and time

setFullYear sets the year of an existing Date object without changing any other element.
```
1 var d = new Date();
2 d.setFullYear(2001);
```
setMonth sets the month of an existing Date object without changing any other element.
```
1 var d = new Date();
2 d.setMonth(11);
```
setDate sets the day of the month of an existing Date object without changing any other element.
```
1 var d = new Date();
2 d.setDate(15);
```
setHours sets the hours of an existing Date object without changing any other element.
```
1 var d = new Date();
2 d.setHours(13);
```
setMinutes sets the minutes of an existing Date object without changing any other element.
```
1 var d = new Date();
2 d.setMinutes(05);
```
setSeconds sets the seconds of an existing Date object without changing any other element.
```
1 var d = new Date();
2 d.setSeconds(55);
```
setMilliseconds sets the milliseconds of an existing Date object without changing any other element.
```
1 var d = new Date();
2 d.setMilliseconds(867);
```
