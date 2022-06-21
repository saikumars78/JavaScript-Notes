# 28 Converting strings to integers and decimals

1 var currentAge = prompt("Enter your age.");

2 var yearsEligibleToVote = currentAge - 18;

In the above code, the value assigned to the variable currentAge is a string, because it comes from a user's prompt response. But in line 2, when the variable appears in an arithmetic
expression, the value is automatically (and temporarily) converted to a number to make the math work.

var profit = "200" - "150"; //50

var profit = "200" - "duck"; //an alert will display saying "NaN" meaning "not a number." 

# 29 Converting strings to numbers, numbers to strings

The following code converts the string "24" to the number 24.

1 var integerString = "24"

2 var num = Number(integerString);

The following code converts the string "24.9876" to the number 24.9876.

1 var floatingNumString = "24.9876";

2 var num = Number(floatingNumString);

Converting a number to a string, perhaps so you can format it, is straightforward.

1 var numberAsNumber = 1234;

2 var numberAsString = numberAsNumber.toString();
 
The code above converts the number 1234 to the string "1234" and assigns it to the
variable numberAsString.


# 30 Controlling the length of decimals


var prettyTotal = total.toFixed(2);

The statement above rounds the number represented by total to 2 places and assigns the result to the variable prettyTotal. The number inside the parentheses tells JavaScript how
many places to round the decimal to.

Now add a dollar sign, and you're all set.

var currencyTotal = "$" + prettyTotal;

To shorten a number to no decimals, leave the parentheses empty.

var prettyTotal = total.toFixed();

# 31 Getting the current date and time

 
                   
