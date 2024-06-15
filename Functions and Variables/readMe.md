### USING CLI FOR PYTHON
```python
code filename.py # opens file to write python code
python filename.py #command to interpret the code (top to bottom)
```

## Functions
Predefined or user defined block of code that can be used when necessary.

### The first program / print() function
```python
print("Hello, World")
```

### Taking Input / input() function
```python
print("What is your name?: ")
input()

or

input("What is your name?: ")
```

### return values
Functions can return a value which can be used for more purpose.

### Variables
A variable is just a container for some value in computer.
```python
name = input("What is your name?: ") 
```
 `=` is an assignment operator that copies and value from right and assigns to the left.

```python
name = input("What is your name?: ") 
print("hello,")
print(name)
```

```output
vaibhav #input
hello,
vaibhav
```

### Comments
Notes to yourself that is ignored by the interpreter
`#` is used to comment any statement after the keyword.

- Comments are a way for programmers to track what they are doing in their programs and even inform others about their intentions for a block of code. In short, they are notes for yourself and others who will see your code!
- You can add comments to your program to be able to see what it is that your program is doing. You might edit your code as follows:

```python
# Ask the user for their name
name = input("What's your name? ")
print("hello,")
print(name)
```

- Comments can also serve as a to-do list for you.
### Printing Multiple items together
```python
name = input("What's your name? ")
print("hello," + name) #concatenation
```

```output
vaibhav         #input
hello,vaibhav   #no space between both
```

We can use a comma `,` to pass in multiple arguments by editing our code as follows:
```python
name = input("What's your name? ")
print("hello," , name) #concatenation
```

```output
vaibhav         #input
hello, vaibhav   #1 space between both
```

### Strings and Parameters
A string, known as a `str` in Python, is a sequence of text.

- Functions take arguments that influence their behavior. If we look at the documentation for [`print`](https://docs.python.org/3/library/functions.html#print) you’ll notice we can learn a lot about the arguments that the print function takes.
- Looking at this documentation, you’ll learn that the print function automatically includes a piece of code `end='\n'. This` \n `indicates that the print function will automatically create a line break when run. The print function takes an argument called` end` and the default is to create a new line.
- However, we can technically provide an argument for `end` ourselves such that a new line is not created!
```python
# Ask the user for their name
name = input("What's your name? ")
print("hello, ", end="")
print(name)
```

```output
vaibhav         #input
hello, vaibhav   #no new line
```

- By providing `end=""` we are overwriting the default value of `end` such that it never creates a new line after this first print statement. Providing the name as “Vaibhav”, the output in the terminal window will be `hello, Vaibhav`.
- Parameters, therefore, are arguments that can be taken by a function.

- `sep` can be used for defining the separation filled when more than one argument is passed and separated with a comma. By default, it is an empty space.
```python
# Ask the user for their name
name = input("What's your name? ")
print("hello,",name, sep='') #now, no space between the two arguments
```

```output
vaibhav         #input
hello,vaibhav   #empty space between both
```

### A small problem with quotation marks

- Notice how adding quotation marks as part of your string is challenging.
- `print("hello,"friend"")` will not work, and the compiler will throw an error.
- Generally, there are two approaches to fixing this. First, you could simply change the quotes to single quotation marks.
- Another, more commonly used approach would be code as `print("hello, \"friend\"")`. The backslashes tell the compiler that the following character should be considered a quotation mark in the string and avoid a compiler error.
### Formatting String
Probably the most elegant way to use strings would be as follows:

```python
# Ask the user for their name
name = input("What's your name? ")
print(f"hello, {name}")
```

Notice the `f` in `print(f"hello, {name}")`. This `f` is a special indicator for Python to treat this string a special way.
```output
vaibhav         #input
hello, vaibhav   
```

### More on strings
- You should never expect your user to cooperate as intended. Therefore, you will need to ensure that the input of your user is corrected or checked.
- It turns out that built into strings is the ability to remove whitespace from a string.
- By utilizing the method `strip` on `name` as `name = name.strip()`, will strip all the whitespaces on the left and right of the users input. You can modify your code to be:

```python
# Ask the user for their name
name = input("What's your name? ")

# Remove whitespace from the str
name = name.strip() #remove from right and left, we can use lsrip() or rstrip() too

# Print the output
print(f"hello, {name}")
```

Rerunning this program, regardless of how many spaces you type before or after the name, it will strip off all the whitespace.
```output
   vaibhav        #input
hello, vaibhav   
```

Using the `capitalize()` method, it would title case the user’s name:

```python
# Ask the user for their name
name = input("What's your name? ")

# Remove whitespace from the str
name = name.strip()

# Capitalize the first letter of first word
name = name.capitalize()

# Print the output
print(f"hello, {name}")
```

```output
   vaibhav sharma        #input
hello, Vaibhav sharma   
```

Using the `title` method, it would title case the user’s name:

```python
# Ask the user for their name
name = input("What's your name? ")

# Remove whitespace from the str
name = name.strip()

# Capitalize the first letter of each word
name = name.title()

# Print the output
print(f"hello, {name}")
```

```output
   vaibhav sharma        #input
hello, Vaibhav Sharma   
```

- Notice that you can modify your code to be more efficient:

```python
# Ask the user for their name
name = input("What's your name? ")

# Remove whitespace from the str and capitalize the first letter of each word
name = name.strip().title()

# Print the output
print(f"hello, {name}")
```

This creates the same result as your previous code.
- We could even go further!
```python
# Ask the user for their name, remove whitespace from the str and capitalize the first letter of each word
name = input("What's your name? ").strip().title()

# Print the output
print(f"hello, {name}")
```

### Split the string

```python
# Ask the user for their name, remove whitespace from the str and capitalize the first letter of each word
name = input("What's your name? ").strip().title()

# Split the string into substrings.
first, last = name.split(' ') #assigns text before space to first and rest to last

# Print the output
print(f"hello, {first}")
```

```output
   vaibhav sharma        #input
hello, Vaibhav   
```

# Integer or int
- In Python, an integer is referred to as an `int`.
- In the world of mathematics, we are familiar with +, -, *, /, and % operators. That last operator `%` or modulo operator may not be very familiar to you.
- You don’t have to use the text editor window in your compiler to run Python code. Down in your terminal, you can run `python` alone. You will be presented with `>>>` in the terminal window. You can then run live, interactive code. You could type `1+1`, and it will run that calculation. 

```python
x = 1
y = 2

z = x + y

print(z)
```

```output
3
```

```python
x = input("What's x? ")
y = input("What's y? ")

z = x + y

print(z)
```

- Running this program, we discover that the output is incorrect as `12`. Why might this be?
- Prior, we have seen how the `+` sign concatenates two strings. Because your input from your keyboard on your computer comes into the compiler as text, it is treated as a string. We, therefore, need to convert this input from a string to an integer. We can do so as follows:

```python
x = input("What's x? ")
y = input("What's y? ")

z = int(x) + int(y)

print(z)
```

The result is now correct. The use of `int(x)` is called “casting,” where a value is temporarily changed from one type of variable (in this case, a string) to another (here, an integer).

- We can further improve our program as follows:

```python
x = int(input("What's x? "))
y = int(input("What's y? "))

print(x + y)
```

This illustrates that you can run functions on functions. The inner function is run first, and then the outer one is run. First, the `input` function is run. Then, the `int` function.