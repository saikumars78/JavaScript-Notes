# 26 Rounding numbers
Things to keep in mind:

Math. is how all math functions begin. The "M" must be capped.<br>
The function rounds up when the decimal is .5. It rounds 1.5 to 2, 2.5 to 3, etc. It rounds -1.5 to -1, -2.5 to -2, etc.
```
scoreAvg = Math.round(scoreAvg);
var scoreAvg = Math.round(.0678437);
var scoreAvg = Math.ceil(.000001);
```
ceil stands for "ceiling." It rounds .000001 up to 1, -.000001 up to 0, 1.00001 up to 2,and so on.
```
var scoreAvg = Math.floor(.999999);
```
floor rounds .999999 down to 0, 1.9 down to 1, -.000001 down to -1, and so on.

# 27 Generating random numbers

The following code generates a pseudo-random number, with 16 decimal places, ranging from 0.0000000000000000 through 0.9999999999999999 and assigns it to the variable
randomNumber.
```
var randomNumber = Math.random();
1 var bigDecimal = Math.random();
2 var improvedNum = (bigDecimal * 6) + 1;
3 var numberOfStars = Math.floor(improvedNum);
```
This is what happens in the code above, line by line:
1. Generates a 16-place decimal and assigns it to the variable bigDecimal.
2. Converts the 16-place decimal to a number ranging from 0.0000000000000000 through 5.9999999999999999, then adds 1, so the range winds up 1.0000000000000000 through
6.9999999999999999. This number is assigned to the variable improvedNum.
3. Rounds the value represented by improvedNum down to the nearest integer that ranges from 1 to 6.
