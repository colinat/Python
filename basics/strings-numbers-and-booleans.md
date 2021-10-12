# Strings, Numbers and Booleans

## Strings

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

### Changing Case in a String with Methods
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

### Combining or Concatenating Strings

It’s often useful to combine strings. Python uses the plus symbol (+) to combine strings. For example:

```python
>>> first_name = 'john'
>>> last_name = 'doe'
>>> full_name = first_name + ' ' + last_name
>>> print(full_name.title())
John Doe
```

### Adding whitespace with Tabs or Newlines

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
```

### Stripping whitespaces
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

### Splitting to a list of strings
`split()` turns a string into a list of smaller strings, breaking on whitespace by default. This is super useful for taking you from one big string to a list of words.

```python
>>> words = "Pluto is a planet!"
>>> words.split()
['Pluto', 'is', 'a', 'planet!']
```

Occasionally you'll want to split on something other than whitespace, like this:

```python
>>> datestr = '1956-01-31'
>>> print(datestr.split('-'))
['1956', '01', '31']
```


## Integers
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

Python uses two multiplication symbols to represent exponent:

```python
>>> 3 ** 2
9
>>> 10 ** 6
1000000
```

Python supports the order of operations so you can use multiple operations in one expression. You can also use parentheses to modify the order of operations so Python can evaluate your expression in the order you specify. For example:

```python
>>> 2 + 3 * 4
14
>>> (2 + 3) * 4
20
```

## Floats
Python calls any number with a decimal point a float. For the most part, you can use decimals without worrying about how they behave. Simply enter the numbers you want to use, and Python will most likely do what you expect:

```python
>>> 0.1 + 0.1
0.2
>>> 0.2 + 0.2
0.4
>>> 2 * 0.1
0.2
```

But be aware that you can sometimes get an arbitrary number of decimal places like the one below:

```python
>>> 0.1 + 0.2
0.30000000000000004
>>> 3 * 0.1
0.30000000000000004
```

Python tries to find a way to represent the result as precisely as possible, which is sometimes difficult given how computers have to represent numbers internally. Just ignore the extra decimal places for now. 

When you divide any two numbers, even if they are integers that result in a whole number, you'll always get a float. If you mix an integer and a float in any other operations, you'll get a float as well:

```python
>>> 1 + 2.0
3.0
>>> 2 * 3.0
6.0
>>> 3.0 ** 2
9.0
```

#### Floor division
Note that Python has two kinds of division. "True division" using `/` always gives us a float. The other is a "floor division" using `//` which gives us a result that's rounded down to the next integer

```python
>>> 3/2
1.5
>>> 3//2
1
```

#### Modulo operator
You can use the Python modulo operator, `%`, to calculate the remainder of dividing two values:

```python
>>> 5 % 2
1
>>> 49 % 5
4
>>> 49 % 7
0
```


## Booleans

A Boolean value is either `True` or `False`. Boolean values are often used to keep track of certain conditions, such as whether a game is running or whether a user can edit certain content on a website

```python
>>> game_active = True
>>> can_edit = False
```

Rather than putting `True` or `False` directly in our code, we usually get boolean values from boolean operators. These are operators that answer yes/no questions:

**Operation** | **Description**
--- | ---
`a == b` | a equal to b
`a != b` | a not equal to b
`a < b` | a less than b
`a > b` | a greater than b
`a <= b` | a less than or equal to b
`a >= b` | a greater than or equal to b

```python
>>> # at least 21 years old
>>> print("Can a 19-year-old vote?", 19>=21)
Can a 19-year-old vote? False
>>> print("Can a 45-year-old vote?", 45>=21)
Can a 45-year-old vote? True
```

Comparisons frequently work like you'd hope, such as in the case of comparing integer and float:

```python
>>> 3 == 3.0
True
```

This will return `False` when comparing string literal and a number:
```python
>>> '3' == 3
False
```

Testing for equality is case-sensitive in Python. For example, two values with different capitalization are not considered equal:

```python
>>> car = 'Audi'
>>> print(car == 'Audi') # True
True
>>> print(car == 'audi') # False
False
```


## Summary

+ What strings are and simple string manipulation, e.g. changing case, stripping whitespaces and concatenatation
+ Working with integers and floats and basic arithmetic operators: `+`, `-`, `*`, `/`, as well as floor division `//` and modulo `%` 
+ How booleans are used, and what to expect when testing for comparisons between two values/variables

---

[<< Prev](https://github.com/colinat/Python/blob/main/basics/variables-and-data-types.md) | [Next >>](https://github.com/colinat/Python/blob/main/basics/lists-tuples-dictionaries.md)

[Back to list of contents](https://github.com/colinat/Python)