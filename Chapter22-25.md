# 22 Strings:Measuring length and extracting parts

Things to be aware of:

A string is indexed like an array. Only, instead of each index number referring to an element, it refers to a character.Like array indexing, string indexing begins with 0.

In the slice method, the first number inside the parentheses is the index of the first character in the slice. The second number is not, however, the last character in the slice.
It's the first character after the slice. If you subtract the first index from the second index,you'll always get the length of the slice.

Here's another example.

var someChars = cityToCheck.slice(2, 5);

1 var firstChar = cityToCheck.slice(0, 1);

2 var otherChars = cityToCheck.slice(1);

3 firstChar = firstChar.toUpperCase();

4 otherChars = otherChars.toLowerCase();

5 var cappedCity = firstChar + otherChars;

Here's what happens in the code above, line-by-line:

1. Copies the first character of the string and assigns it to the variable firstChar.
2. Copies all the characters from the second one to the end and assigns them to the variable
otherChars.
3. Caps the first character.
4. Lower-cases the other characters.
5. Concatenates both parts to re-form the whole string.


# 23 Strings:Finding segments

1 for (var i = 0; i < text.length; i++) {

2 if (text.slice(i, i + 12) === "World War II") {

3 text = text.slice(0, i) + "the Second World War" + text.slice(i + 12);

4 }

5 }

# 24 Strings:Finding a character at a location

var firstChar = firstName.charAt(0)

The code above finds a single character at index-0 (the beginning) of the string represented by the variable firstName and assigns it to the variable firstChar.

# 25 Strings:Replacing characters

var newText = text.replace("World War II", "the Second World War");

