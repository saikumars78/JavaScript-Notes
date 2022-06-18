# 15 Arrays

 Assigning some string values to some variables.

var cities = ["Atlanta", "Baltimore", "Chicago", "Denver", "Los Angeles", "Seattle"];

An array can be assigned any type of value that you can assign to ordinary variables. You
 can even mix the different types in the same array.
 
var mixedArray = [1, "Bob", "Now is", true];

Things to keep in mind:

The first item always has an index of 0, not 1. This means that if the last item in the list
has an index of 9, there are 10 items in the list.

The same naming rules you learned for ordinary variables apply. Only letters, numbers, $
and _ are legal. The first character can't be a number. No spaces.


# 16 Arrays:

Adding and removing elements

pop, you can remove the last element of an array.

pets.pop();

push, you can add one or more elements to the end of an array.

pets.push("fish", "ferret");

# 17 Arrays: Removing, inserting,and extracting elements

shift method to remove an element from the beginning of an array.

pets.shift();

To add one or more elements to the beginning of an array, use the unshift method.

pets.unshift("fish", "ferret");

the splice method to insert one or more elements anywhere in an array, while
optionally removing one or more elements that come after it.Now we can limit the number of loops to the count that JavaScript comes up with.

1 var numElements = cleanestCities.length;

2 var matchFound = false;

3 for (var i = 0; i < numElements; i++);

4 if (cityToCheck === cleanestCities[i]) {

5 matchFound = true;

6 alert("It's one of the cleanest cities");

7 break;

8 }

9 }

10 if (matchFound === false) {

11 alert("It's not on the list");

12 }


Now we can limit the number of loops to the count that JavaScript comes up with.

1 var numElements = cleanestCities.length;

2 var matchFound = false;

3 for (var i = 0; i < numElements; i++);

4 if (cityToCheck === cleanestCities[i]) {

5 matchFound = true;

6 alert("It's one of the cleanest cities");

7 break;

8 }

9 }

10 if (matchFound === false) {

11 alert("It's not on the list");

12 }

# 20 for loops nested

1 var firstNames = ["BlueRay ", "Upchuck ", "Lojack ", "Gizmo ", "Do-Rag "];

2 var lastNames = ["Zzz", "Burp", "Dogbone", "Droop"];

3 var fullNames = [];
0
5 for (var i = 0; i < firstNames.length; i++) {

6 for (var j = 0; j < lastNames.length; j++) {

7 fullNames.push(firstNames[i] + lastNames[j]);

9 }

10 }

# 21 changing case

toLowerCase

toUpperCase

1 var cityToCheck = prompt("Enter your city");

2 cityToCheck = cityToCheck.toLowerCase();

3 var cleanestCities = ["cheyenne", "santa fe", "tucson", "great falls", "honolulu"];

4 for (var i = 0; i <= 4; i++) {

5 if (cityToCheck === cleanestCities[i]) 

6 alert("It's one of the cleanest cities");

7 }

8 }
