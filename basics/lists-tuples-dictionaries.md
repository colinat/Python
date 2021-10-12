# Lists, Tuples, Dictionaries

## Lists

A list is a collection of items in a particular order. In Python, square brackets [] indicate a list, and individual elements in the list are separated by commas:

```python
>>> bicycles = ['trek', 'cannondale', 'redline', 'specialized']
>>> print(bicycles)
['trek', 'cannondale', 'redline', 'specialized']
>>> numbers = [1, 7, 34, 20, 12, 7]
>>> print(numbers)
[1, 7, 34, 20, 12, 7]
```

### Accessing a single item in a list
You can access any element in a list by telling Python the position, or index, of the item desired. To access an element in a list, write the name of the list followed by the index of the item enclosed in square brackets.

```python
>>> print(bicycles[0])
trek
```

You can also use the string methods from the earlier chapter on any string element in a list. 

```python
>>> print(bicycles[0].title())
Trek
```

### Index Positions Start at 0, Not 1
Python considers the first item in a list to be at position 0, not position 1. Using this simple counting system, you can get any element you want from a list by subtracting one from its position in the list. For instance, to access the fourth item in a list, you request the item at index 3.

```python
['trek', 'cannondale', 'redline', 'specialized']
>>> print(bicycles[1])
cannondale
>>> print(bicycles[3])
specialized
```

Python has a special syntax for accessing the last element in a list. Using index -1, Python always returns the last item in the list. This syntax is quite useful when you’ll want to access the last items in a list without knowing exactly how long the list is:

```python
>>> print(bicycles[-1])
specialized
>>> print(bicycles[-3])
cannondale
```

### Lists can include different data types
A list can contain a mix of different types of variables such as this:

```python
>>> my_fav_things = [8, 'raindrops on roses', help]  # `help` is a reserved keyword in Python

# You can have a list of lists as well
>>> hands = [
... ['J', 'Q', 'K'],
... ['2', '2', '2'], 
... ['6', 'A', 'K']]

```

### List slicing
To access a range of elements in a list, you need to slice a list. One way to do this is to use the simple slicing operator i.e. colon(`:`):

```python
# Accessing from 1st to 3rd item in the list
>>> print(bicycles[0:3])
['trek', 'cannondale', 'redline']

# You can omit the 0 as well. Python will automatically assume the index range starts from the 1st item or the zeroth-index
>>> print(bicycles[:3])
['trek', 'cannondale', 'redline']
```

Simple illustration:

<img src="https://www.learnbyexample.org/wp-content/uploads/python/Python-List-Slicing-Illustration.png" height="300"/>


### Searching values in a list
If we know the values in the list, we can get the index of a specified value using `index()`:

```python
>>> bicycles.index('redline')
2
```

We can also check if a specific value is in the list, using the `in` keyword:

```python
>>> 'trek' in bicycles
True
>>> 'bmx' in bicycles
False
```

### Changing lists
Lists are "mutable", meaning they can be modified "in place".

```python
>>> bicycles
['trek', 'cannondale', 'redline', 'specialized']
>>> bicycles[3] = "haro"
>>> print(bicycles)
['trek', 'cannondale', 'redline', 'haro']
```

```python
# Modify a range of items in a list all-at-once using slicing
>>> bicycles[:3] = ['tre', 'can', 'red']
>>> print(bicycles)
['tre', 'can', 'red', 'haro']
```

### Strings are sequences
Strings can be thought of as sequences of characters. Almost everything we've seen that we can do to a list, we can also do to a string as well:

```python
>>> planet = 'Pluto'
>>> print(planet[0])
P
>>> print(planet[:3])
Plu
```

### Adding to list
The simplest way to add a new element to a list is to use `append()`. When you append an item to a list, the new element is added to the end of the list.

```python
>>> bicycles = ['trek', 'cannondale', 'redline', 'specialized']
>>> bicycles.append('haro')
>>> print(bicycles)
['trek', 'cannondale', 'redline', 'specialized', 'haro']
```

`append()` works with only one new element, but you can use `extend()` to append multiple values at the end of the list:

```python
>>> numbers
[1, 7, 34, 20, 12, 7]
>>> numbers.extend([56, 2, 12])
>>> print(numbers)
[1, 7, 34, 20, 12, 7, 56, 2, 12]
```
### Inserting value to list
You can insert a new item into the list via a specified index using `insert()`. For example, lets add a new item into 2nd position in the list:

```python
>>> bicycles = ['trek', 'cannondale', 'redline', 'specialized']
>>> bicycles.insert(1, 'haro')
>>> print(bicycles)
['trek', 'haro', 'cannondale', 'redline', 'specialized']
```

### Removing from list
Using `pop()` removes and returns the last element of a list:

```python
>>> bicycles
['trek', 'cannondale', 'redline', 'specialized', 'haro']
>>> bicycles.pop()
'haro'
>>> print(bicycles)
['trek', 'cannondale', 'redline', 'specialized']
```

If you know the value of the item, you can remove an item from the list using `remove()`:

```python
>>> bicycles.remove('cannondale')
>>> print(bicycles)
['trek', 'redline', 'specialized']
```

### Sorting lists
Python provides a number of different ways to organize your lists, depending on the situation. For instance, you can use `sort()` to sort a list:

```python
[1, 7, 34, 20, 12, 7]
>>> numbers.sort()  # sort numbers in ascending order
>>> print(numbers)
>>> [1, 7, 7, 12, 20, 34]
>>> print(bicycles)
['trek', 'cannondale', 'redline', 'specialized']  # sort strings in alphabetical
>>> bicycles.sort()
>>> print(bicycles)
['cannondale', 'redline', 'specialized', 'trek']
>>> bicycles.sort(reverse=True)  # sort in reverse-alphabetical order
>>> print(bicycles)
['trek', 'specialized', 'redline', 'cannondale']
```

### Reverse-sort
We can reverse the sort order of the list using `reverse()`:

```python
>>> print(numbers)
[1, 7, 34, 20, 12, 7]
>>> numbers.reverse() # reverse the order of the list
>>> print(numbers)
[34, 20, 12, 7, 7, 1]
```

### Using arithmetic operators with lists
Some of the arithmetic operators we have used on numbers before can also be used on lists, but the effect may not always be what we expect:

```python
>>> # this concatenates two list rather than adding element-wise
>>> list_1 = [1, 2, 3] + [4, 5, 6]
>>> print(list_1)
[1, 2, 3, 4, 5, 6]


```python
>>> # we can concatenate a list with itself by multiplying it by an integer
>>> list_2 = [1, 2, 3] * 3
>>> print(list_2)
[1, 2, 3, 1, 2, 3, 1, 2, 3]
```

Not all arithmetic operators can be used on lists though. This will give us an error:

```python
>>> print([1, 2, 3] - [2, 3, 0])
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for -: 'list' and 'list'
>>> 
```

## Tuples

Tuples are similar to lists in many ways, but they are **immutable**, that is a list of items that cannot change. We define a tuple literal by putting a comma-separated list of values inside round brackets `()`:

```python
>>> t = (1, 2, 3,) # Trailing comma is optional
>>> t = 1, 2, 3    # this is equivalent to above
>>> print(t)
(1, 2, 3)
```

### Tuples cannot be modified

You will get an error if you attempt to modify a value in a tuple:

```python
>>> t[0] = 100
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

### Tuples supports indexing, slicing as well
Though tuples cannot be modified, you can access values in tuple via indexing or slicing just as you would for a list. Likewise, you can also search using `index()` for tuples:

```python
>>> print(t[1])  # you can index a tuple just like a list
2
>>> print(t[:2]) # tuple supports slicing as well
(1, 2)
>>> print(t.index(2)) # searching for a value in tuple
1
```

## Dictionaries
A dictionary in Python is a collection of key-value pairs. Each key is connected to a value, and you can use a key to access the value associated with that key. To define a dictionary literal, we put a comma-separated list of key-value pairs between curly brackets `{}`. We use a colon to separate each key from its value:

```python
>>> numbers = {'one':1, 'two':2, 'three':3}
>>> numbers['one']  # accessing a value using corresponding key in dictionary
1
```

### Adding a key-value pair

We can use the same syntax to add another key, value pair:

```python
>>> numbers['eleven'] = 11  # append a new key, 'eleven' with a value of '11' in the dictionary
>>> numbers
{'one': 1, 'two': 2, 'three': 3, 'eleven': 11}
```

### Removing key-value pair
You can use the `del` statement to remove a key-value pair:

```python
>>> del numbers['eleven']  # delete key-value pair identified by the key: 'eleven'
>>> print(numbers)
{'one': 1, 'two': 2, 'three': 3}
```

### Different data types in a dictionary
The keys in dictionary don’t have to be strings – we can mix different types of keys and different types of values:

```python
>>> # Tuples are used as keys while corresponding values are in boolean
>>> battleship_guesses = {
...     (3, 4): False,
...     (2, 6): True,
...     (2, 5): True,
... }
>>> print(battleship_guesses[(3,4)]) # print value corresponding to key: (3,4)
False
>>> print(battleship_guesses.get((3,4))) # this does the same thing as the code above
False
```

### Nesting
In Python, you can store multiple dictionaries in a list, or a list of items as a value in a dictionary, i.e. nesting. You can nest dictionaries inside a list, a list of items inside a dictionary, or even a dictionary inside another dictionary:

```python
>>> # nesting a list of dictionaries
>>> car_0 = {'brand': 'toyota', 'colour': 'silver'}
>>> car_1 = {'brand': 'honda', 'colour': 'blue'}
>>> car_2 = {'brand': 'mercedes', 'colour': 'white'}
>>> cars = [car_0, car_1, car_2]
>>> print(cars)
[{'brand': 'toyota', 'colour': 'silver'}, {'brand': 'honda', 'colour': 'blue'}, {'brand': 'mercedes', 'colour': 'white'}]
```

## Summary

+ You've learn what are lists and how to work with them. 
+ Tuples are almost like lists but they are immutable, i.e. cannot be modified. 
+ Dictionaries are a collection of key-value pairs that you can retrieve a value using its associated key, add or remove key-value pairs.

---

[<< Prev](https://github.com/colinat/Python/blob/main/basics/strings-numbers-and-booleans.md) | [Next >>](https://github.com/colinat/Python/blob/main/basics/if-elif-else.md)

[Back to list of contents](https://github.com/colinat/Python)