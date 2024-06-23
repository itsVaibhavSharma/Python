# Intro and String Manipulation

When coding, readability is key. Comments serve as effective notes, explaining the logic behind your code. They prove valuable when returning to a project after some time and also aid your colleagues in understanding the code.

In Python, you can write a comment using a `#`. Anything that comes after the `#` won't be executed.
#### Creating a variable
```python
variable_name = value

string_1 = "I am a string"
string_2 = 'I am also a string'
string_3 = 'This is not valid"
```

You can use the built-in function `print()` to print the output of your code on the terminal.

Functions are reusable code blocks that you can call, or invoke, to run their code when you need them. To call a function, you just need to write a pair of parentheses next to its name.

An _argument_ is an object or an expression passed to a function — added between the opening and closing parentheses — when it is called:

```py
greet = 'Hello!'
print(greet)
```
The code in the example above would print the string `'Hello!'`, which is the value of the variable `greet` passed to `print()` as the argument.

Each string character can be referenced by a numerical index. The index count starts at zero. So the first character of a string has an index of `0`. For example, in the string `'Hello World'`, `'H'` is at index `0`, `'e'` is at index `1`, and so on.

Each character of a string can be accessed by using bracket notation. You need to write the variable name followed by square brackets and add the index of the character between the brackets:
```py
text = 'Hello World'
r = text[8]
```
- You can also access string characters starting from the end of the string. The last character has an index of `-1`, the second to last `-2` and so on.
- You can access the number of characters in a string with the built-in `len()` function.
- Another useful built-in function is `type()`, which returns the data type of a variable.

#### Key aspects of variable naming in Python are:
- Some words are reserved keywords (e.g. `for`, `while`, `True`). They have a special meaning in Python, so you cannot use them for variable names.
- Variable names cannot start with a number, and they can only contain alpha-numeric characters or underscores.
- Variable names are case sensitive, i.e. `my_var` is different from `my_Var` and `MY_VAR`.
- Finally, it is a common convention to write variable names using `snake_case`, where each space is replaced by an underscore character and the words are written in lowercase letters.

You are going to use the `.find()` method to find the position in the alphabet of each letter in your message. A method is similar to a function, but it belongs to an object.
```py
sentence = 'My brain hurts!'
sentence.find('r') #can be assigned to a variable too
```
Above, the `.find()` method is _called on_ `sentence` (the string to search in), and `'r'` (the character to locate) is passed as the argument. The `sentence.find('r')` call will return `4`, which is the index of the first occurrence of `'r'` in `sentence`.

```python
text = 'Hello World'
alphabet = 'abcdefghijklmnopqrstuvwxyz'
index = alphabet.find(text[0])
```

`.find()` returns the index of the matching character inside the string. If the character is not found, it returns `-1`. As you can see, the first character in `text`, uppercase `'H'`, is not found, since `alphabet` contains only lowercase letters.

You can transform a string into its lowercase equivalent with the `.lower()` method. Add another `print()` call to print `text.lower()` and see the output.

```python
text = 'Hello World'
print(text.lower())
```

```python
text = 'Hello World'
alphabet = 'abcdefghijklmnopqrstuvwxyz'
index = alphabet.find(text[0].lower())
```

- You can use `+` operator in the index to move to further indexes.
```python
shifted = alphabet[index + shift]
```

#### LOOPS
A loop allows you to systematically go through a sequence of elements and execute actions on each one.

In this case, you'll employ a `for` loop. Here's how you can iterate over `text`:

Example Code

```py
for i in text:
```

`for` is the keyword denoting the loop type. `i` is a variable that sequentially takes the value of the elements in `text`. The statement ends with a colon, `:`.

The code to execute at each iteration — placed after the `:` — constitutes the body of the loop. This code must be indented. In Python, it is recommended to use 4 spaces per indentation level. This indented level is a code block.

Example Code

```py
for i in text:
    print(i)
```

Python relies on indentation to indicate blocks of code. A colon at the end of a line is a signal that a new indented block of code will follow.

So, when no indented block is found after the final colon, the code execution stops and an `IndentationError` is thrown. This code will not show the output and instead raise an `IndentationError`:

Example Code

```py
for i in text:
print(i)
```

- The iteration variable can have any valid name, but it's convenient to give it a meaningful name. (i can be any name).

Currently, the `print()` function is taking a single argument `i`, but it can take multiple arguments, separated by a comma.
```python
for char in text:
    index = alphabet.find(char)
    print(char, index)
```

For lower case iteration:
```python
for char in text.lower():
    index = alphabet.find(char)
    print(char, index)
```

Strings are immutable, which means they cannot be changed once created. For example, you might think that the following code changes the value of `my_string` into the string `'train'`, but this is not valid:

```py
my_string = 'brain'
my_string[0] = 't'
```

When you try to change the individual characters of a string as you did in the previous step, you get a `TypeError`, which occurs when an object of inappropriate type is used in your code.

As you can see from the error message, strings do not support item assignment, because they are immutable. However, a variable can be reassigned another string:

```py
message = 'Hello World'
message = 'Hello there!'
```

- We can also print multiple items like: `print('char:', char, 'new char:', new_char)`
```python
text = 'Hello World'
shift = 3
alphabet = 'abcdefghijklmnopqrstuvwxyz'
  
for char in text.lower():
    index = alphabet.find(char)
    new_index = index + shift
    new_char = alphabet[new_index]
    print('char:', char, 'new char:',new_char)
```

```output
char: h new char: k
char: e new char: h
char: l new char: o
char: l new char: o
char: o new char: r
char:   new char: c
char: w new char: z
char: o new char: r
char: r new char: u
char: l new char: o
char: d new char: g
```

- Note: There is a space after even item in the print call.
Concatenation is possible in String
```python
text1 = 'Hello'
text2 = ' '
text3 = 'World'
text = text1 + text2 + text3
```

You can obtain the same effect of `a = a + b` by using the addition assignment operator:

```py
a += b
```

The addition assignment operator enables you to add a value to a variable and then assign the result to that variable.

Comparison operators allow you to compare two objects based on their values. You can use a comparison operator by placing it between the objects you want to compare. They return a _Boolean_ value — namely `True` or `False` — depending on the truthfulness of the expression.

Python has the following comparison operators:

| Operator | Meaning                  |
| -------- | ------------------------ |
| ==       | Equal                    |
| !=       | Not equal                |
| >        | Greater than             |
| <        | Less than                |
| >=       | Greater than or equal to |
| <=       | Less than or equal to    |
```python
print(char == ' ')
```

#### IF STATEMENT
```py
if x != 0:
    print(x)
```

In the example above, the condition of the `if` statement is `x != 0`. The code `print(x)`, inside the `if` statement body, runs only when the condition evaluates to `True` (in this example, meaning that `x` is different from zero).

A conditional statement can also have an `else` clause. This clause can be added to the end of an `if` statement to execute alternative code if the condition of the `if` statement is false:

```py
if x != 0:
    print(x)
else:
    print('x = 0')
```

-   The modulo operator (`%`) can be used to return the remainder of the division between two numbers. For example: `5 % 2` is equal to `1`, because 5 divided by 2 has a quotient of 2 and a remainder of 1.

### FUNCTION
A function is essentially a reusable block of code. You have already met some built-in functions, like `print()`, `find()` and `len()`. But you can also define custom functions like this:

```py
def function_name():
    <code>
```

A function declaration starts with the `def` keyword followed by the function name — a valid variable name — and a pair of parentheses. The declaration ends with a colon.
To execute, a function need to be called (or invoked) by appending a pair of parentheses after its name, like this:

```py
function_name()
```

Although this approach works, it doesn't significantly enhance the code's reusability. Repeatedly calling your function will result in the same outcome. However, functions can be declared with _parameters_ to introduce versatility and customization:

```py
def function_name(param_1, param_2):
    <code>
```

Parameters are variables that you can use inside your function. A function can be declared with different number of parameters. In the example above, `param_1` and `param_2` are parameters.
The function call will now require two `arguments` :
```python
function_name(orgparam_1, orgparam_2)
```
NOTE: It does not have a data type, still the name can be different as the passed parameters.


The `.index()` method is identical to the `.find()` method but it throws a `ValueError` exception if it is unable to find the substring.

A `ValueError` is a built-in exception that is raised when an argument with the right type but inappropriate value is passed to a function.

At the moment, your function prints some strings, but these values cannot be used by other parts of code to perform any actions.

For that purpose, you need to use a `return` statement:

```python
def foo():
    return 'spam'
```

You need to write `return` followed by a space and the value that the function should return. Once the `return` statement is found, that value is returned and the execution of the function stops, proceeding to the next line of code after the function call. In the example above, the `foo` function returns the string `'spam'`.

Functions can be called with default arguments. A default argument indicates the value that the function should take if the argument is not passed. For example, the function below accepts three arguments but you can call it passing two arguments. The third one will assume the specified value by default:

Example Code

```py
def foo(a, b, c=value):
    <code>
```

The `.isalpha()` method returns `True` if all of the characters of the string on which it is called are letters. For example, the code below returns `True`:

Example Code

```py
'VaibhavSharmsa.isalpha()
# True
```

The `not` operator is used to negate an expression. When placed before a truthy value — a value that evaluates to `True` — it returns `False` and vice versa.

```python
if not char.isalpha():
	final_message += char
```

The `pass` keyword can be used as a placeholder for future code. It does not have any effect in your code but it can save you from errors you would get in case of incomplete code:

```python
def foo():
    pass
```

In Python, there's a way to easily format strings. _f-strings_ enable you to interpolate values in your strings.

Interpolation means writing placeholders that will be replaced by the specified values when the program runs. For example, you can get the same result of `'Encrypted text: ' + text` with `f'Encrypted text: {text}'`. You need to put an `f` before the quotes to create the f-string and write the variables or expressions you want to interpolate between curly braces.

The newline character `\n` is a special sequence used to represent a new line. You can write a backslash `\` followed by an `n` as a normal sequence of characters in a string and it will be replaced by a new line in the output when the program runs.

### str class
Python comes with built-in classes that can help us with string manipulation. One of them is the `str` class. It has a method called `maketrans` that can help us create a translation table. This table can be used to replace characters in a string:

```python
str.maketrans({'t': 'c', 'l': 'b'})
```

The above, when called on a string, will replace all `t` characters with `c` and all `l` characters with `b`.

Defining the translation does not in itself translate the string. The `translate` method must be called on the string to be translated with the translation table as an argument:

```python
my_string = "tamperlot"
translation_table = str.maketrans({'t': 'c', 'l': 'b'})
translated_string = my_string.translate(translation_table)
```

You have accessed elements (characters) of a string before, using the index operator `[]`. You can also use the index operator to access a range of characters in a string with `string[x:y:h]`:

Example Code

```python
my_string = 'camperbot'
camper = my_string[0:6]
cp = my_string[0:6:3]
```

Where `x` is the starting index, `y` is the ending index, and `h` is the step (the amount of characters to skip over).
Just as the step is optional, a start at `0` and an end at the end of the slice are optional:

Example Code

```python
my_string = 'camperbot'
camperbot = my_string[::]
```

### Converting string to int
```python
my_string = '123'
my_int = int(my_string)
```

### // and % operator
```python
my_number = 12
first_digit = my_number // 10
second_digit = my_number % 10
```

Integer division results in the quotient of the division, rounded down to the nearest integer.

# Lists
A list in Python is a built-in data type that allows you to store many items in a single data structure. In Python, you create a list by putting items inside square brackets (`[]`), with each item separated from the following one by a comma.

```python
numbers = [1, 2, 3, 4]
```

You want to be able to add items at the end of your list. For that you'll use the `.append()` list method.

```python
my_list = [2, 4, 7]
my_list.append(3)
```

In the example above, after appending `3`, `my_list` would be `[2, 4, 7, 3]`.

# Dictionary
A dictionary is another built-in data type in Python. A dictionary is a collection of data in the form of _key_-_value_ pairs. Dictionaries are defined with curly braces (`{}`) and they contain key-value pairs separated by commas. Each key is followed by a colon (`:`) and the value:

```python
{'amount': 50.0, 'category': 'Food'}
```

In the example above, `'amount'` and `'category'` are keys, and `50.0` and `'Food'` are their corresponding values.

In Python, an important thing to know is that the same type of quote used to define a string cannot be used inside it. For example, the string `'I'm a string!'` is not valid. To use the single quote inside that string you should either:

- Escape the quote by prepending a backlash to it: `'I\'m a string!'`
- Or use double quotes to define the string: `"I'm a string!"` (preferred).

You can access values in a dictionary through its keys. You need to use bracket notation and include the key between the square brackets:

```python
my_dict = {'amount': 50.0, 'category': 'Food'}
my_dict['amount'] # 50.0
```

# Lambda Functions
Lambda functions are brief, anonymous functions in Python, ideal for simple, one-time tasks. They are defined by the `lambda` keyword, and they use the following syntax:

```python
lambda x: expr
```

In the example above, `x` represents a parameter to be used in the expression `expr`, and it acts just like any parameter in a traditional function. `expr` is the expression that gets evaluated and returned when the lambda function is called.

Create a variable named `test` and assign it a lambda function that takes an `x` parameter and returns `x * 2`.

```python
test = lambda x: x * 2
```

To call a lambda function you can use the usual function syntax with a pair of parentheses after the variable name.

Call your `test` lambda function and pass `3` as the argument. Then, print the result.

```python
test = lambda x: x * 2
print(test(3))
```

Lambda functions can be valuably combined with the `map()` function, which executes a specified function for each element in a collection of objects, such as a list:

```python
map(lambda x: x * 2, [1, 2, 3])
```

The function to execute is passed as the first argument, and the iterable is passed as the second argument.

The result of the example above would be `[2, 4, 6]`, where each item in the list passed to `map()` has been doubled by the action of the lambda function.

Modify your `print()` call to print the result of calling `map()` with `test` as the first argument, and `[2, 3, 5, 8]` as the second argument. You won't be able to see a readable output yet.

```python
test = lambda x: x * 2
print(map(test, [2, 3, 5, 8]))
```

You should see something like `<map object at 0xd273a8>` printed on the console, which is the string representation of the map object returned by `map()`.

To obtain a readable output you need to turn the map object into a list. Do it by passing the `map()` call as the argument to the `list()` function.

```python
test = lambda x: x * 2
print(list(map(test, [2, 3, 5, 8])))
```

The `sum()` function returns the sum of the items in the iterable which is passed as its argument. You are going to use `sum()` together with `map()` and `lambda` functions to get the total amount of expenses.

For now, make a little test and modify your current `print()` call replacing the `list()` call with a call to the `sum()` function passing it the current `map()` call as the argument.

```python
test = lambda x: x * 2
print(sum(map(test, [2,3,5,8])))
```
