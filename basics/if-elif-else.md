# if, elif, else

## Using `if` statements

Programming often involves examining a set of conditions (recall earlier [chapter](https://github.com/colinat/Python/blob/main/basics/strings-numbers-and-booleans.md#booleans) on booleans) and deciding which action to take based on those conditions. Python’s `if` statement allows you to examine the current state of a program and respond appropriately to that state.

The simplest kind of if statement has one test and one action:

```
if conditional_test:
    do something
```

***Note 1:** Python uses indentation to determine when one line of code is connected to the line above it. Always indent the line after the `if` statement.*

***Note 2:** Note especially the use of colons (:) at the end of the `if` statement. A colon is used to start an indent suite of statements. It is also used in case of `while`, `for`, `def` and class statements which you will learn in later chapters.

You can put any conditional test in the first line and just about any action in the indented block following the test. If the conditional test evaluates to `True`, Python executes the code following the `if` statement. If the test evaluates to `False`, Python ignores the code following the `if` statement. For example:

```python
>>> age = 19
>>> if age >= 18:
...     print("You are old enough to vote!")
... 
You are old enough to vote!
```

You can have as many lines of code as you want in the block following the `if` statement:

```python
>>> age = 19
>>> if age >= 18:
...     print("You are old enough to vote!")
...     print("Have you registered to vote yet?")
... 
You are old enough to vote!
Have you registered to vote yet?
```


## `if`-`else` Statements
Often, you’ll want to take one action when a conditional test passes and a different action in all other cases. Python’s `if`-`else` syntax makes this possible. An `if`-`else` block is similar to a simple `if` statement, but the `else` statement allows you to define an action or set of actions that are executed when the conditional test fails.

```python
>>> age = 17
>>> if age >= 18:
...     print("You are old enough to vote!")
...     print("Have you registered to vote yet?")
... else:
...     print("Sorry, you are too young to vote.")
...     print("Please register to vote as soon as you turn 18!")
... 
Sorry, you are too young to vote.
Please register to vote as soon as you turn 18!
```

In a simple if-else chain like the one above, one of the two actions will always be executed.



## `if`-`elif`-`else` Chain

Often, you’ll need to test more than two possible situations, and to evaluate these you can use Python’s `if`-`elif`-`else` syntax. Python executes only one block in an `if`-`elif`-`else` chain. It runs each conditional test in order until one passes. When a test passes, the code following that test is executed and Python skips the rest of the tests. Consider an amusement park that charges different rates for different age groups:

```python
>>> age = 12
>>> if age < 4:
...     print("Your admission cost is $0.")
... elif age < 18:
...     print("Your admission cost is $5.")
... else:
...     print("Your admission cost is $10.")
... 
Your admission cost is $5.
```

The concepts of `if`-`elif`-`else` can be summarised in the illustration below:

![](https://www.pythontutorial.net/wp-content/uploads/2020/10/Python-if-elif-else-statement.png)


## More on `if`-`elif`-`else`

Now we've learn the basics of using `if`, `else` and `elif` statements, lets explore how to utilise these to tackle different conditional tests in our code:


### Using Multiple `elif` Blocks
You can use as many `elif` blocks in your code as you like. For example, if the amusement park were to implement a discount for seniors, you could add one more conditional test to the code to determine whether someone qualified for the senior discount. Let’s say that anyone 65 or older pays half the regular admission, or $5:

```python
age = 12
if age < 4:
    price = 0
elif age < 18:
    price = 5
elif age < 65:
    price = 10
else:
    price = 5
print("Your admission cost is $" + str(price) + ".")
```

*Note: the code example above is demonstrated using IDE/code editor instead of Python interpreter, thus the absence of `>>>`.*


### Omitting the `else` Block
Python does not require an `else` block at the end of an `if`-`elif` chain. Sometimes an `else` block is useful; sometimes it is clearer to use an additional `elif` statement that catches the specific condition of interest:

```python
age = 12
if age < 4:
    price = 0
elif age < 18:
    price = 5
elif age < 65:
    price = 10
elif age >= 65:
    price = 5
print("Your admission cost is $" + str(price) + ".")
```

Output:

```python
Your admission cost is $5.
```


### Testing Multiple Conditions
The `if`-`elif`-`else` chain is only appropriate to use when you just need one test to pass. As soon as Python finds one test that passes, it skips the rest of the tests. However, sometimes it’s important to check all of the conditions of interest. In such case, you should use a series of simple `if` statements with no `elif` or `else` blocks. This technique makes sense when more than one condition could be `True`, and you want to act on every condition that is `True`. For example:

```python
requested_toppings = ['mushrooms', 'extra cheese']
if 'mushrooms' in requested_toppings:
    print("Adding mushrooms.")
if 'pepperoni' in requested_toppings:
    print("Adding pepperoni.")
if 'extra cheese' in requested_toppings:
    print("Adding extra cheese.")
    
print("\nFinished making your pizza!")
```

Output:

```python
Adding mushrooms.
Adding extra cheese.
Finished making your pizza!
```



## Summary

+ Indented code under an `if` statement runs if the condition is true.
+ We can add an optional `else` statement. Indented code under it will run if the code under the `if` statement does not run.
+ If you want only one block of code to run, use an `if`-`elif`-`else` chain. If more than one block of code needs to run, use a series of independent `if` statements.

---

[<< Prev (Lists, Tuples, Dictionaries)](https://github.com/colinat/Python/blob/main/basics/lists-tuples-dictionaries.md) | [Next >> (for and while loops)](https://github.com/colinat/Python/blob/main/basics/for-and-while-loops.md)

[Back to list of contents](https://github.com/colinat/Python)