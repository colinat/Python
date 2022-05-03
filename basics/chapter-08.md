# Functions

You've already seen and used functions such as `print()`. Functions makes your programs easier to write, read, test, and fix. They are named blocks of code that are designed to do one specific job. If you need to perform a particular task multiple times throughout your program, you just call the function dedicated to handling that task, and the call tells Python to run the code inside the function. We will learn about using and defining functions in this chapter


## Getting Help
The `help()` function is possibly the most important Python function you can learn. If you remember how to use `help()`, you hold the key to understanding most other functions.

Here's an example:

```python
>>> help(print)
Help on built-in function print in module builtins:

print(...)
    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
    
    Prints the values to a stream, or to sys.stdout by default.
    Optional keyword arguments:
    file:  a file-like object (stream); defaults to the current sys.stdout.
    sep:   string inserted between values, default a space.
    end:   string appended after the last value, default a newline.
    flush: whether to forcibly flush the stream.
```

`help()` displays two things:
1. the header of the function `round(number[, ndigits])`. In this case, it tells us that `round()` takes an argument we can describe as number. Additionally, we can optionally give a separate argument which could be described as ndigits
2. A brief description of what the function does

**Common pitfall**: When looking up `help` on a function, remember to pass in the name of the function itself, not the result of calling the function, i.e. without the ().


## Docstrings
The docstring is a triple-quoted string (which may span multiple lines) that comes immediately after the header of a function. When we call `help()` on a function, it shows the docstring. You can input a docstring when defining your own functions to give clarity to any programmer that could use your function. For example:

```python
def least_difference(a, b, c):
    """Return the smallest difference between any two numbers
    among a, b and c.
    
    >>> least_difference(1, 5, -5)
    4
    """
    diff1 = abs(a - b)
    diff2 = abs(b - c)
    diff3 = abs(a - c)
    return min(diff1, diff2, diff3)
```

Good programmers use docstrings unless they expect to throw away the code soon after it's used (which is rare). So, you should start writing docstrings too.

## Useful builtin functions
Apart from `print()`, below shows some are the built-in Python functions that you will use quite regularly. For a more comprehensive list, you can refer to [here](https://docs.python.org/3/library/functions.html)

#### `abs()`
returns the absolute value of a numeric value (e.g. integer or float). Obviously it can’t be a string. It has to be a numeric value.

```python
>>> abs(-4/3)
1.3333333333333333
```

#### `round()`
returns the rounded value of a numeric value.

```python
>>> round(-4/3)
-1
```

#### `min()`
returns the smallest item of a list or of the typed-in arguments. It can even be a string.

```python
>>> min(3, 2, 5)
2
>>> min('c', 'a', 'b')
'a'
```

#### `max()`
Guess, what! It’s the opposite of `min()`


#### `sorted()`
It sorts a list into ascending order. The list can contain strings or numbers.

```python
>>> a = [3, 2, 1]
>>> sorted(a)
[1, 2, 3]
```

#### `sum()`
It sums a list. The list can have all types of numeric values, although it handles floats… well, not smartly.

```python
>>> a = [3, 2, 1]
>>> sum(a)
6
>>> b = [4/3, 2/3, 1/3, 1/3, 1/3]
>>> sum(b)
3.0000000000000004
```

#### `len()`
returns the number of elements in a list or the number of characters in a string.

```python
>>> len('Hello!')
6
>>> a = [3, 2, 1]
>>> len(a)
3
```

#### type()
returns the type of the variable.

```python
>>> a = True
>>> type(a)
<class 'bool'>
>>> b = 2
>>> type(b)
<class 'int'>
```


## Defining a function
Builtin functions are great but we can only get so far with them before we need to start defining our own functions. Here’s a simple function named `greet_user()` that prints a greeting, which we defined:

```python
def greet_user():
    """Display a simple greeting."""
    print("Hello!")    
```

This is simplest structure of a function. The code uses the keyword `def` to inform Python that you’re defining a function. In this case, the name of the function is `greet_user()`, and it needs no information to do its job, so its parentheses are empty. (Even so, the parentheses are required.) Finally, the definition ends in a colon.

The line print("Hello!") is the only line of actual code in the body of this function, so `greet_user()` has just one job: print("Hello!"). When you want to use this function, you call it. A function call tells Python to execute the code in the function. Calling our function is as simple as entering `greet_user()`:

```python
>>> greet_user()
Hello!
```

### Passing information to a function
Modified slightly, the function `greet_user()` can not only tell the user Hello! but also greet them by name. For the function to do this, you enter a parameter (e.g. `username`) in the parentheses of the function’s definition at def `greet_user()`. The function now expects you to provide a value for that parameter. When you call `greet_user()`, you can pass it a name, such as 
'jesse', inside the parentheses:

```python
def greet_user(username):
    """Display a simple greeting."""
    print("Hello, " + username.title() + "!")
```

Calling the function: 
```python
>>> greet_user('jesse')
Hello, Jesse!
```
You can call `greet_user()` as often as you want and pass it any name you want to produce a predictable output every time.

### Arguments and parameters
In the preceding example, we defined `greet_user()` to require a value for the variable `username`. The variable `username` in the function definition is an example of **a parameter, a piece of information the function needs to do its job**. The value 'jesse' in `greet_user('jesse')` is an example of an argument. **An argument is a piece of information that is passed from a function call to a function**. When we call the function, we place the value we want the function to work with in parentheses. In this case the argument 'jesse' was passed to the function `greet_user()`, and the value was stored in the parameter username.


## Passing arguments
Because a function definition can have multiple parameters, a function call may need multiple arguments. You can pass arguments to your functions in a number of ways. You can use positional arguments, which need to be in the same order the parameters were written; keyword arguments, where each argument consists of a variable name and a value; and lists and dictionaries 
of values. Let’s look at each of these in turn.


### Positional Arguments
When you call a function, Python must match each argument in the function call with a parameter. The simplest way to do this is based on the order of the arguments provided. Values matched up this way are called positional arguments. For example:

```python
def describe_pet(animal_type, pet_name):
    """Display information about a pet."""
    print("\nI have a " + animal_type + ".")
    print("My " + animal_type + "'s name is " + pet_name.title() + ".")
    
```

This function needs a type of animal and the animal’s name. When we call `describe_pet()`, we need to provide an animal type and a name, in that order: 
```python
>>> describe_pet('hamster', 'harry')

I have a hamster.
My hamster's name is Harry.
```

#### Order matters in positional arguments
You can get unexpected results if you mix up the order of the arguments in a function call when using positional arguments:

```python
>>> describe_pet('harry', 'hamster')

I have a harry.
My harry's name is Hamster.
```

### Keyword arguments
A keyword argument is a name-value pair that you pass to a function. You directly associate the name and the value within the argument, so when you pass the argument to the function, there’s no confusion. Keyword arguments free you from having to worry about correctly ordering your arguments in the function call, and they clarify the role of each value in the function. 

```python
>>> describe_pet(animal_type='hamster', pet_name='harry')

I have a hamster.
My hamster's name is Harry.
```

### Default values
When we called help`(print)`, we saw that the print function has several optional arguments. For example, we can specify a value for `sep` to put some special string in between our printed arguments:

```python
>>> print(1, 2, 3, sep=' < ')
1 < 2 < 3
```

If we don't specify a value, `sep` is treated as having a default value of ' ' (a single space).

```python
>>> print(1, 2, 3)
1, 2, 3
```

Adding optional arguments with default values to the functions we define turns out to be pretty easy. If an argument for a parameter is provided in the function call, Python uses the argument value. If not, it uses the parameter’s default value. For example, you can set the default value of animal_type to 'dog': 

```python
def describe_pet(pet_name, animal_type='dog'):
    """Display information about a pet."""
    print("\nI have a " + animal_type + ".")
    print("My " + animal_type + "'s name is " + pet_name.title() + ".")
```

Now when the function is called with no `animal_type` specified, Python knows to use the value 'dog' for this parameter:

```python
>>> describe_pet(pet_name='willie')

I have a dog.
My dog's name is Willie.
```

### Passing an arbitrary number of arguments
Python also allow functions to collect an arbitrary number of arguments from the calling statement. This is useful when you do not know ahead of time how many arguments a function needs to accept. 

We will leave this part out of the basic tutorials. If you wish to know more, you can jump directly to the [advanced chapter] to learn more about it. 


## Return values
A function doesn’t always have to display its output directly. Instead, it can process some data and then return a value or set of values. The value the function returns is called a return value. Return values allow you to move much of your program’s grunt work into functions, which can simplify the body of your program.

Returning a simple value:

```python
>>> def get_formatted_name(first_name, last_name):
...     full_name = first_name + ' ' + last_name
...     return full_name.title()
... 
>>> musician = get_formatted_name('jimi', 'hendrix')
>>> print(musician)
Jimi Hendrix
```

When you call a function that returns a value, you need to provide a variable where the return value can be stored. In this case, the returned value is stored in the variable `musician`. The return statement takes a value from inside a function and sends it back to the line that called the function. Return values allow you to move much of your program’s grunt work into functions, which can simplify the body of your program.

A function can return any kind of value you need it to, including more complicated data structures like lists and dictionaries. For example:

```python
>>> def build_person(first_name, last_name):
...     """Return a dictionary of information about a person."""
...     person = {'first': first_name, 'last': last_name}
...     return person
... 
>>> musician = build_person('jimi', 'hendrix')
>>> print(musician)
{'first': 'jimi', 'last': 'hendrix'}
```

### Returning `None`
A Python function will always have a return value. So, if you don’t explicitly use a return value in a `return` statement, or if you totally omit the `return` statement, then Python will implicitly return a default value for you. That default return value will always be `None`.

```python
>>> def build_person(first_name, last_name):
...     full_name = first_name + ' ' + last_name
... 
>>> musician = build_person('jimi', 'hendrix')
>>> print(musician)
None
>>> type(musician)
<class 'NoneType'>
```

## Variable scope
A variable defined inside a function is local to that function. It is accessible from the point at which it is defined until the end of the function, and exists for as long as the function is executing. When we use the assignment operator `=` inside a function, its default behaviour is to create a new local variable – unless a variable with the same name is already defined in the local scope.

```python
# this is a global variable
a = 0

def my_function(c):
    # a is a local variable
    a = c  
    b = a 
    print('value of local b:',b)  # value of b is 7
    print('value of local c:',c) 
```

Now we call the function, passing the value 7 as the first and only parameter:

```python
>>> my_function(7)
value of local b: 7
value of local c: 7
>>> print('value of global a:', a)
value of global a: 0
```

This gives us an error as variable `b` is a variable local only to the function:

```python
>>> print('value of local b:', b)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'b' is not defined
```

## Summary

+ Functions makes your programs easier to write, read, test, and fix.
+ Calling `help()` is incredibly useful to understand other functions
+ Docstrings are useful to briefly explain what the function does.
+ Some built-in Python functions that you are incredibly useful.
+ Function definition can have multiple parameters; make use of positional/keyword arguments or default values to aid in your coding
+ A function will always have a return value; it will return `None` if a return value is not explicitly defined.
+ Variables defined in a function will be local only to that function; they will ceased to exist after the end of the function execution in the code.


[<< Prev](https://github.com/colinat/Python/blob/main/basics/for-and-while-loops.md) | [Next >>](https://github.com/colinat/Python/blob/main/basics/classes.md)

[Back to list of contents](https://github.com/colinat/Python)