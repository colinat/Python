# Variables and simple data types

## Variables

To define a new variable, we assign a value to a label using the `=` sign (also called the assignment operator):

```python
>>> message = "Hello world!"
>>> print(message)
Hello world!
```

We’ve added a variable named `message`. A variable is similar to the memory functionality found in most calculators, in that it holds one value which can be retrieved many times, and that storing a new value erases the old. In the above example, the value is the text `“Hello world!”`.

Adding a variable makes a little more work for the Python interpreter. When it processes the first line, it associates the text `“Hello world!”` with the variable `message`. When it reaches the second line, it prints the value associated with message to the screen.

You can change the value of a variable in your program at any time, and Python will always keep track of its current value. For example:

```python
>>> message = "Hello world!"
>>> print(message)
Hello world!
 
>>> message = "Hello Python!"
>>> print(message)
Hello Python!
```

### Naming and using variables

When using variables in Python, you need to adhere to a few rules and guidelines. Breaking some of these rules will cause errors; guidelines just help you to write code that's easier to read and understand.

+ Variables names can contain only **letters, numbers, and underscores**.
+ They can **start with a letter or an underscore, but not with a number**. E.g. `message_1` is acceptable but `1_message` is not.
+ **Spaces are not allowed** in variable names
+ Underscores can be used to separate words in variable names. E.g. `greeting_message`.
+ Variable names should be **short but descriptive**. E.g. `name` vs `n`; `name_length` as opposed to `length_of_persons_name`.
+ Be careful when using the lowercase letter `l` and the uppercase letter `O` - they can be confused with the numbers `1` and `0`.

For example of good variable names: 

```python
>>> magic_number = 123
>>> greeting = "Hello World!"
```

Examples of bad variable names:

```python 
>>> magicNumber = 3.14          # looks weird
>>> Greeting = "Hello there!"   # also looks weird
>>> x = "Hello again!"          # what the heck is x?
```

**Note**: In Python, the hash mark (#) indicates a comment. Anything following a hash mark in your code is ignored by the Python interpreter. For example:

```python
>>> # print("Hello world!")
>>> print("Hello world!")
Hello world!
```
Comments are an extremely useful feature in most programming languages. Writing comments helps to explain what your code is sup-
posed to do and how you are making it work. Most software is written collaboratively, whether by a group of employees or a group of people working together on an open source project. Writing clear, concise comments in your code is one of the most beneficial habits you can form as a new programmer.


Last but not least: 
+ **Avoid using Python keywords and function names**. There are words that Python has reserved for a particular programmatic purpose, such as the word `print`.


### Avoiding name errors when using variables

Programmer makes mistakes, and these mistakes can be as simple as a typo. Let’s look at an error you’re likely to make early on and learn how to fix it. Enter the following code, including the misspelled word `mesage` shown below:

```python
>>> message = "Hello world!"
>>> print(mesage)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'mesage' is not defined
```
When an error occurs, the interpreter provides a traceback. A traceback is a record of where the interpreter ran into trouble when trying to execute your code. This help us spot the error quickly and in this case, it found a name error as the variable, `mesage` has not been defined. A name error occurs when we either forgot to set a variable’s value before using it, or we made a spelling mistake when entering the variable’s name. 


## Data types

The data type of a variable determines which operations can be applied to it. Once a variable is assigned a data type, it can be used for computations in the program. The best thing about Python is that the data type doesn’t need to be defined when declaring a variable. Data types exist, but the variables are not bound to any of them. Languages that act in this way are called dynamically typed languages.

### Variations of data types

There are two kinds of data types, both of which are further divided into sub-types:

+ **Primitive data types**: These are pre-defined and supported by the programming language.
+ **Non-primitive data types**: These are derived from the primitive data types and offer increased functionality.

![](https://i.imgur.com/6cg2E9Q.png)


### Primitive data sub-types

#### Strings
You've seen what are strings in the earlier code examples. A string is simply a series of characters. Anything inside quotes is considered a string in Python, and you can use single or double quotes around your strings like this:

```python
>>> "This is a string"
'This is a string'
>>> 'This is also a string'
'This is also a string'
>>> 
```

Double quotes are convenient if your string contains a single quote character (e.g. representing an apostrophe).
```python
>>> "Pluto's a planet"
"Pluto's a planet"
```
Likewise, you can also create a string that contains double-quotes if you wrap it in single quotes: 
```python
>>> 'My dog is named "Pluto"'
'My dog is named "Pluto"'
```

##### Changing Case in a String with Methods
One of the simplest tasks you can do with strings is change the case of the words in a string.

```python
>>> name = "john doe"
>>> print(name.title())
John Doe
```

You can change a string to all uppercase or all lowercase letters like this: 

```python
>>> print(name.upper())
JOHN DOE
>>> print(name.lower())
john doe
```

##### Combining or Concatenating Strings

It’s often useful to combine strings. Python uses the plus symbol (+) to combine strings. For example:

```python
>>> first_name = 'john'
>>> last_name = 'doe'
>>> full_name = first_name + ' ' + last_name
>>> print(full_name.title())
John Doe
```

##### Adding whitespace with Tabs or Newlines

In programming, whitespace refers to any nonprinting character, such as spaces, tabs, and end-of-line symbols. You can use whitespace such as a tab like this:

```python
>>> print("Hello world!")
Hello world!
>>> print("\tHello world!")
	Hello world!
```

To add a newline in a string, use the character combination `\n`:
```python
>>> print("Languages:\nPython\nC\nJavaScript")
Languages:
Python
C
JavaScript
>>> 
```

##### Stripping whitespaces
To programmers `'python'` and `'python '` look pretty much the same, but to a program, they are two different strings. Fortunately, Python makes it easy to eliminate extraneous whitespace from string values if necessary. You can strip whitespaces from either side a string or from both sides at once, like this:

```python
>>> fav_language = '  python '
>>> fav_language.rstrip()
'  python'
>>> fav_language.lstrip()
'python '
>>> fav_language.strip()
'python'
```

#### Integer
Integers represent numeric data – they represent whole numbers from negative infinity to infinity. You can add (+), subtract (-), multiply (\*), and divide (/) integers in Python.

```python
>>> 2 + 3
5
>>> 3 - 2
1
>>> 2 * 3
6
>>> 3 / 2
1.5
```


#### Float


#### Boolean


#### None


### Non-Primitive data sub-types

#### List


#### Tuple


#### Dictionary







## Summary

+ You've learned to work with variables
+ How to resolve name errors when they arise
+ What strings are and simple manipulation, e.g. lowercase, uppercase, or titlecase, stripping whitespaces and concatenatation
+ Working with integers and floats. 
+ Writing explanatory comments to make your code easier for you and others 

---

[<< Prev](https://github.com/colinat/Python/blob/main/basics/ides-and-code-editors.md) | [Next >>]()

[Back to list of contents](https://github.com/colinat/Python)