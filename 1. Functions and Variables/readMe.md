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

# Float 
-   
A floating point value is a real number that has a decimal point in it, such as `0.52`.
- You can change your code to support floats as follows:

```python
x = float(input("What's x? "))
y = float(input("What's y? "))

print(x + y)
```

This change allows your user to enter `1.2` and `3.4` to present a total of `4.6`.

- Let’s imagine, however, that you want to round the total to the nearest integer. Looking at the Python documentation for `round`, you’ll see that the available arguments are `round(number[n, ndigits])`. Those square brackets indicate that something optional can be specified by the programmer. Therefore, you could do `round(n)` to round a digit to its nearest integer. Alternatively, you could code as follows:

```python
# Get the user's input
x = float(input("What's x? "))
y = float(input("What's y? "))

# Create a rounded result
z = round(x + y)

# Print the result
print(z)
```

The output will be rounded to the nearest integer.

- What if we wanted to format the output of long numbers? For example, rather than seeing `1000`, you may wish to see `1,000`. You could modify your code as follows:

```python
# Get the user's input
x = float(input("What's x? "))
y = float(input("What's y? "))

# Create a rounded result
z = round(x + y)

# Print the formatted result
print(f"{z:,}")
```

Though quite cryptic, that `print(f"{z:,}")` creates a scenario where the outputted `z` will include commas where the result could look like `1,000` or `2,500`.

- How can we round floating point values? First, modify your code as follows:

```python
# Get the user's input
x = float(input("What's x? "))
y = float(input("What's y? "))

# Calculate the result
z = x / y

# Print the result
print(z)
```

When inputting `2` as x and `3` as y, the result z is `0.6666666666`, seemingly going on to infinite as we might expect.

- Let’s imagine that we want to round this down. We could modify our code as follows:

```python
# Get the user's input
x = float(input("What's x? "))
y = float(input("What's y? "))

# Calculate the result and round
z = round(x / y, 2)

# Print the result
print(z)
```
`Output: 0.67`

As we might expect, this will round the result to the nearest two decimal points.

- We could also use `fstring` to format the output as follows:

```python
# Get the user's input
x = float(input("What's x? "))
y = float(input("What's y? "))

# Calculate the result
z = x / y

# Print the result
print(f"{z:.2f}")
```

This cryptic `fstring` code displays the same as our prior rounding strategy.

- You can learn more in Python’s documentation of [`float`](https://docs.python.org/3/library/functions.html?highlight=float#float).

# Own Functions / def
- We can create our own function called `hello` as follows:

```python
def hello():
	print("hello")


name = input("What's your name? ")
hello()
print(name)
```

Notice that everything under `def hello()` is indented. Python is an indented language. It uses indentation to understand what is part of the above function. Therefore, everything in the `hello` function must be indented. When something is not indented, it treats it as if it is not inside the `hello` function. Running `python hello.py` in the terminal window, you’ll see that your output is not exactly as you may want.

- We can further improve our code:

```python
# Create our own function
def hello(to):
	print("hello,", to)


# Output using our own function
name = input("What's your name? ")
hello(name)
```

Here, in the first lines, you are creating your `hello` function. This time, however, you are telling the compiler that this function takes a single parameter: a variable called `to`. Therefore, when you call `hello(name)` the computer passes `name` into the `hello` function as `to`. This is how we pass values into functions.

- We can change our code to add a default value to `hello`:

```python
# Create our own function
def hello(to="world"):
	print("hello,", to)


# Output using our own function
name = input("What's your name? ")
hello(name)

# Output without passing the expected arguments
hello()
```

Test out your code yourself. Notice how the first `hello` will behave as you might expect, and the second hello, which is not passed a value, will, by default, output `hello, world`.

- We don’t have to have our function at the start of our program. We can move it down, but we need to tell the compiler that we have a `main` function and a separate `hello` function.

```python
def main():

	# Output using our own function
	name = input("What's your name? ")
	hello(name)

	# Output without passing the expected arguments
	hello()


# Create our own function
def hello(to="world"):
	print("hello,", to)
```

This alone, however, will create an error of sorts. If we run `python hello.py`, nothing happens! The reason for this is that nothing in this code is actually calling the `main` function and bringing our program to life.

- The following very small modification will call the `main` function and restore our program to working order:

```python
def main():

	# Output using our own function
	name = input("What's your name? ")
	hello(name)

	# Output without passing the expected arguments
	hello()


# Create our own function
def hello(to="world"):
	print("hello,", to)


main()
```

### Returning values
- You can imagine many scenarios where you don’t just want a function to perform an action but also to return a value back to the main function. For example, rather than simply printing the calculation of `x + y`, you may want a function to return the value of this calculation back to another part of your program. This “passing back” of a value we call a `return` value.
- Returning to our `calculator.py` code by typing `code calculator.py`. Erase all code there. Rework the code as follows:

```python
def main():
	x = int(input("What's x? "))
	print("x squared is", square(x))


def square(n):
	return n * n


main()
```

Effectively, `x` is passed to `square`. Then, the calculation of `x * x` is returned back to the main function