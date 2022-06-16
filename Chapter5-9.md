# Math expressions: Familiar operators

Examples:

1.var popularNumber = 2 + 2;

2.var popularNumber = 12 - 24;

3.var popularNumber = 3 * 12;

4.var num = 10;

  var anotherNum = 1;

  var popularNumber = num + anotherNum;

5.var whatsLeftOver = 10 % 3;

-% is the modulus operator.It gives you the remainder when the division is executed.


# Math expressions: Unfamiliar operators

num++;

This is a short way of writing... 

num = num + 1;

# Math expressions: Eliminating ambiguity

var totalCost = 1 + 3 * 4;

In JavaScript as in algebra, the ambiguity is cleared up by precedence rules. As in
algebra, the rule that applies here.(The result: 13)

Example:

1.var totalCost = 1 + (3 * 4);

2.var totalCost = (1 + 3) * 4;

3.var resultOfComputation = (2 * 4) * 4 + 2;

# Concatenating text strings

alert("Thanks, " + userName + "!");

Using the plus operator, the code combines—concatenates—three elements into the
message: the string "Thanks, " plus the string represented by the variable userName plus the
string "!"

Note that the first string includes a space. Without it, the alert would read,
"Thanks,Susan!".

You can concatenate any combination of strings and variables, or all strings or all
variables.

Example:

Here it is, with three strings.

alert("Thanks, " + "Susan" + "!");

You can assign a concatenation to a variable.

var message = "Thanks, ";

var userName = "Susan";

var banger = "!";

var customMess = message + userName + banger;

alert(customMess);

# Prompts

A prompt box asks the user for some information and provides a response field for her
answer.

Prompt code is like alert code, with two differences.

1.In a prompt, you need a way to capture the user's response. That means you need to start
by declaring a variable, followed by an equal sign.

2.In a prompt, you can specify a second string. This is the default response that appears in
the field when the prompt displays. If the user leaves the default response as-is and just
clicks OK, the default response is assigned to the variable. It's up to you whether you
include a default response.

Example:

var question = "Your species?";

var defaultAnswer = "human";

var spec = prompt(question, defaultAnswer)




