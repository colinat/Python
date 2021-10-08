# Variables and simple data types

## Variables

To define a new variable, we assign a value to a label using the `=` sign (also called the assignment operator):

```python
>>> message = "Hello world!"
>>> print(message)
Hello world!
```

We’ve added a variable named `message`. A variable is similar to the memory functionality found in most calculators, in that it holds one value which can be retrieved many times, and that storing a new value erases the old. In the above example, the value is the text `“Hello world!”`.

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

Last but not least: 
+ **Avoid using Python keywords and function names**. There are words that Python has reserved for a particular programmatic purpose, such as the word `print`.


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

### Comments
In Python, the hash mark (#) indicates a comment. Anything following a hash mark in your code is ignored by the Python interpreter. For example:

```python
>>> # print("Hello world!")
>>> print("Hello world!")
Hello world!
```
Comments are an extremely useful feature in most programming languages. Writing comments helps to explain what your code is sup-
posed to do and how you are making it work. Most software is written collaboratively, whether by a group of employees or a group of people working together on an open source project. Writing clear, concise comments in your code is one of the most beneficial habits you can form as a new programmer.


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

The data type of a variable determines which operations can be applied to it. Once a variable is assigned a data type, it can be used for computations in the program. The best thing about Python is that the data type doesn’t need to be defined when declaring a variable. Data types exist, but the variables are not bound to any of them. Languages that act in this way are called dynamically typed languages.]


### Variations of data types

There are two kinds of data types, both of which are further divided into sub-types:

+ **Primitive data types**: These are pre-defined and supported by the programming language.
+ **Non-primitive data types**: These are derived from the primitive data types and offer increased functionality.

![](https://i.imgur.com/6cg2E9Q.png)


### Primitive data sub-types

#### Strings
Strings are used to store data that involves characters (e.g., names or addresses). Strings can be created in Python by enclosing a sequence of characters within a pair of single or double-quotes.

```python
>>> string_1 = "Hello"
>>> string_2 = "World"
>>> print (string_1 + string_2)
HelloWorld
```

#### Integer
Integers represent numeric data – they represent whole numbers from negative infinity to infinity. You can add (+), subtract (-), multiply (\*), and divide (/) integers in Python.

```python
>>> integer_1 = 100
>>> integer_2 = 50

# various operations on integers
>>> print (integer_1*integer_2)
5000
>>> print (integer_1+integer_2)
150
>>> print (integer_1-integer_2)
50
>>> print (integer_1/integer_2)
2.0
```

#### Float
Floating points are used for rational numbers that usually end with a decimal figure.

```python
>>> integer_1 = 100
>>> integer_2 = 50

# various operations on floats
>>> print(integer_1*integer_2)
5000
>>> print(integer_1+integer_2)
150
>>> print(integer_1-integer_2)
50
>>> print(integer_1/integer_2)
2.0
>>> float_1 = 12.539
>>> float_2 = 6.78
>>> 
>>> print(float_1*float_2)
85.01442
>>> print(float_1+float_2)
19.319
>>> print(float_1-float_2)
5.7589999999999995
>>> print(float_1/float_2)
1.849410029498525
```

#### Boolean
Boolean type only has two types of return values: `True` and `False`. These return values are interchangeable with the integers 1 and 0. In Python, and in many other programming languages, `=` is assigning and `==` is comparing. `a = 1` sets a to 1, and `a == 1` checks if a equals 1.

```python
>>> a = 1
>>> a == 1
True
>>> a = 2
>>> a == 1
False
```

#### None
`None` is Python's "nothing" value, i.e. it is used to define a null variable or an object. Some interesting facts about `None`:

+ `None` is not the same as False.
+ `None` is not 0.
+ `None` is not an empty string.
+ Comparing `None` to anything will always return `False` except `None` itself.


```python
>>> var = None
>>> var == 0
False
>>> var == False
False
>>> var == None
True
>>> # You can also use 'is' to check if variable is None
>>> var is None
True
```
Right now it might seem useless but we'll find a bunch of ways to use `None` later.


### Non-Primitive data sub-types

#### List

Python Lists are used to store collections of heterogeneous items; they can be recognized by their square brackets which hold elements and are separated by a comma.

```python
>>> fruits = ["Apple", "Banana", "Kiwi"]
>>> fruits.append("Melon")
>>> fruits.remove("Apple")
>>> print(fruits)
['Banana', 'Kiwi', 'Melon']
```

#### Tuple
Tuples are similar to lists, but they are often used in different situations and for different purposes. A key difference is that while lists are mutable, tuples are **immutable**, i.e. a list of items that cannot change. The syntax for creating them uses parentheses `()` instead of square brackets `[]`

```python
>>> months = ("January", "February", "March")
>>> months.remove("January")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'tuple' object has no attribute 'remove'
>>> print(months)
('January', 'February', 'March')
```

#### Dictionary

A dictionary is an unordered, changeable, and indexed collection of elements. In Python, dictionaries are written with curly brackets and contain keys and values.

```python
>>> my_car = {
... "brand": "Suzuki",
... "model": "Mehran",
... "year": 2001
... }
>>> print("The brand of my car is", my_car["brand"]) 
The brand of my car is Suzuki
```

We will learn more on how to use these data types in our code in the next chapter

## Summary

+ You've learned to work with variables
+ How to resolve name errors when they arise
+ Writing explanatory comments to make your code easier for you and others 
+ You've learned some of the data types in Python. 

---

[<< Prev](https://github.com/colinat/Python/blob/main/basics/ides-and-code-editors.md) | [Next >>](https://github.com/colinat/Python/blob/main/basics/strings-numbers-and-booleans.md)

[Back to list of contents](https://github.com/colinat/Python)