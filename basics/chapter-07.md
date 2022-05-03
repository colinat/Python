# `for` and `while` loops

## `for` loops

The concept of looping is important because it’s one of the most common ways a computer automates repetitive tasks. For example, when you want to do the same action with every item in a list (recall earlier [chapter](https://github.com/colinat/Python/blob/main/basics/lists-tuples-dictionaries.md#lists) on what is a list), you can use Python’s `for` loop:

```python
>>> magicians = ['alice', 'david', 'carolina'] 
>>> for magician in magicians: 
...     print(magician)
... 
alice
david
carolina
```

Let's walkthrough this in greater elaboration. In the code example above, Python initially reads the first line of the loop:

```python
for magician in magicians
```

This tells Python to retrieve the first value from the list magicians and store it in the variable `magician`. This first value is 'alice'. Python then reads the next line:

```python
print(magician)
```

Python prints the current value of magician, which is still 'alice'. Because the list contains more values, Python returns to the first line of the loop:

```python
for magician in magicians
```

Python retrieves the next name in the list, 'david', and stores that value in magician. Python then executes the line: 

```python
print(magician)
```

Python repeats the entire loop once more with the last value in the list, 'carolina'. Because no more values are in the list, Python moves on to the next line in the program. In this case nothing comes after the `for` loop, so the program simply ends.


### Doing Something After a for Loop
Any lines of code after the for loop that are not indented are executed once without repetition. For example, we can expand on the earlier example and print a thank you message after the for loop without indentation:

```python
magicians = ['alice', 'david', 'carolina'] 
for magician in magicians: 
    print(magician.title() + ", that was a great trick!")  
    print("I can't wait to see your next trick, " + magician.title() + ".\n")
    
print("Thank you, everyone. That was a great magic show!")
```

Output:

```python
Alice, that was a great trick!
I can't wait to see your next trick, Alice.

David, that was a great trick!
I can't wait to see your next trick, David.

Carolina, that was a great trick!
I can't wait to see your next trick, Carolina.

Thank you, everyone. That was a great magic show!
```

Note that if you accidentally indent code that should run after a loop has finished, that code will be repeated once for each item in the list. Sometimes this prompts Python to report an error, but often it would simply be a logical error.

### Looping through a dictionary
Because a dictionary can contain large amounts of data, Python lets you loop through a dictionary. Dictionaries can be used to store information in a variety of ways; therefore, several different ways exist to loop through them. You can loop through all of a dictionary’s key-value pairs, through its keys, or through its values. 

Consider an example where a dictionary store one person’s username, first name, and last name:
```python
user_0 = {
    'username': 'efermi',
    'first': 'enrico',

    'last': 'fermi',
    }
```

If you want to see everything stored in this user’s dictionary, you could loop through the dictionary using a `for` loop:

```python
>>> for key, value in user_0.items():
...     print("\nKey: " + key)
...     print("Value: " + value)
... 

Key: username
Value: efermi

Key: first
Value: enrico

Key: last
Value: fermi
```

`items()` helps to return a list of key-value pairs in the dictionary. The `for` loop then stores each of these pairs in the two variables, `key` and `value` provided. In the preceding example, we use the variables to print each key, followed by the associated value. 

#### Looping Through All the Keys in a Dictionary
The `keys()` method is useful when you don’t need to work with all of the values in a dictionary. Let’s loop through dictionary and print only the keys:

```python
>>> favorite_languages = {
... 
...     'jen': 'python',
...     'sarah': 'c',
...     'edward': 'ruby',
...     'phil': 'python',
...     }
>>> for name in favorite_languages.keys():
...     print(name.title())
... 
Jen
Sarah
Edward
Phil
```

The code above tells Python to pull all the keys from the dictionary `favorite_languages` and store them one at a time in the variable name. The output shows the names of everyone, identified by the dictionary's keys. 

Also note that looping through the keys is actually the default behavior when looping through a dictionary, so this code would have exactly the same output if you wrote . . . 

```python
for name in favorite_languages:
```

rather than...

```python
for name in favorite_languages.keys():
```

#### Looping Through All the Values in a Dictionary
If you are primarily interested in the values that a dictionary contains, you can use the `values()` method to return a list of values without any keys. 


```python
for language in favorite_languages.values():
...     print(language.title())
... 
Python
C
Ruby
Python
```

The `for` statement pulls each value from the dictionary and stores it in the variable language. When these values are printed, we get a list of all chosen languages


## Using `range()`

Python’s `range()` function makes it easy to generate a series of numbers. It can be very useful for writing loops. For example, you can use the `range()` function to print a series of numbers like this:

```python
>>> for value in range(1,5):
...     print(value)
... 
1
2
3
4
```

Note that in the above example, `range()` prints only the numbers 1 through 4. The `range()` function causes Python to start counting at the first value you give it, and it stops when it reaches the second value you provide. This is a result of the off-by-one behavior you’ll see often in programming languages. Because it stops at that second value, the output never contains the end value, which would have been 5 in this case. 

To print the numbers from 1 to 5, you would use `range(1,6)`:

```python
>>> for value in range(1,6):
...     print(value)
... 
1
2
3
4
5
```

### Using `range()` to make a list of numbers
If you want to make a list of numbers, you can convert the results of `range()` directly into a list using `list()`. When you wrap `list()` around a call to `range()`, the output will be a list of numbers. For example:

```python
>>> numbers = list(range(1,6))
>>> print(numbers)
[1, 2, 3, 4, 5]
```

### Skipping numbers in `range()`
We can also use `range()` function to tell Python to skip numbers in a given range. For example, here’s how we would list the even numbers between 1 and 10:

```python
>>> even_numbers = list(range(2,11,2)) 
>>> print(even_numbers)
[2, 4, 6, 8, 10]
```

## `while` loops
The `for` loop takes a collection of items and executes a block of code once for each item in the collection. In contrast, the `while` loop runs as long as, or while, a certain condition is true. 

You can use a while loop to count up through a series of numbers. For example:


```python
while current_number <= 5:
...     print(current_number)
...     current_number += 1
... 
1
2
3
4
5
```

Python repeats the loop as long as the condition `current_number <= 5` is true. Because 1 is less than 5, Python prints 1 and then adds 1, making the current number 2 after adding 1, and it repeats continuously. Once the value of current_number is greater than 5, the loop stops running and the program ends.

### Avoiding infinite loops
If you accidentally omit `current_number +=1`, the loop will run forever. Python interpreter cannot catch infinite loops. If your program gets stuck in an infinite loop, press Ctrl+C or just close the terminal window displaying your program's output.*

Because of this possible infinite loop error, it is more appropriate to use a `for` loop as we are counting to a predetermined number. `while` loops are more suited for event-controlled loop like below:

```python
prompt = "\nTell me something, and I will repeat it back to you:"
prompt += "\nEnter 'quit' to end the program. "

message = ""   
while message != 'quit':     # loop stops when message is 'quit'
    message = input(prompt)  # prompts for user's input and assign the value to variable, 'message'
    print(message)
```

### Using `input()` with `while` loops
The `input()` method is used to get user's text input. Using `while` statement, the above program will continue to loop, prompting for input from user and printing the input keyed in by user in each loop iteration. The loop will only terminate when user keys in 'quit'.

Output:

```python
Tell me something, and I will repeat it back to you:
Enter 'quit' to end the program. Hello world!
Hello world!

Tell me something, and I will repeat it back to you:
Enter 'quit' to end the program. Hello again!
Hello again!

Tell me something, and I will repeat it back to you:
Enter 'quit' to end the program. quit
quit
```

### Using `break` to exit a loop
To exit a `while` loop immediately without running any remaining code in the loop, you can use the `break` statement. The `break` statement directs the flow of your program; you can use it to control which lines of code are executed and which aren’t, so the program only executes code that you want it to, when you want it to. For example:

```python
prompt = "\nPlease enter the name of a city you have visited:"
prompt += "\n(Enter 'quit' when you are finished.) "
while True:
    city = input(prompt)   

    if city == 'quit':  # break out of the loop when user inputs 'quit'
        break 
    else:
        print("I'd love to go to " + city.title() + "!")
```

Output:

```python
Please enter the name of a city you have visited:
(Enter 'quit' when you are finished.) Mandalay
I'd love to go to Mandalay!

Please enter the name of a city you have visited:
(Enter 'quit' when you are finished.) quit
```

***Note:** `break` can also be used to exit `for` loops as well.

### Using `continue` in a Loop
Rather than breaking out of a loop entirely without executing the rest of its code, you can use the `continue` statement to return to the beginning of the loop based on the result of a conditional test. For example, consider a loop that counts from 1 to 10 but prints only the odd numbers in that range:


```python
current_number = 0
while current_number < 10:
    current_number += 1
    if current_number % 2 == 0:
        continue
    
    print(current_number)
```

Output:
```python
1
3
5
7
9
```


## Using `while` loops with lists
So far, we’ve worked with only one piece of user information at a time. We received the user’s input and then printed the input or a response to it. In order to keep track of many users and pieces of information, we’ll need to use lists and dictionaries with our `while` loops. Using `while` loops with lists and dictionaries allows you to collect, store, and organize lots of input to examine and report on later.

For example, this is a sample [program](https://github.com/colinat/Python/blob/main/examples/users.py) that verify a list of unverified users and moving them to a separate list of confirmed users:


```python
# Start with users that need to be verified, 
unconfirmed_users = ['alice', 'brian', 'candace']
confirmed_users = []  # empty list

# Verify each user until there are no more unconfirmed users.
# Move each verified user into the list of confirmed users.

while unconfirmed_users:  # continues to loop as long as there is at least 1 item in `unconfirmed_users` list
    current_user = unconfirmed_users.pop()
    print("Verifying user: " + current_user.title())
    confirmed_users.append(current_user)
    
# Display all confirmed users.
print("\nThe following users have been confirmed:")
for confirmed_user in confirmed_users:
    print(confirmed_user.title())
```

The `while` loop runs as long as the list unconfirmed_users is not empty. Within this loop, the `pop()` method removes unverified users one at a time from the end of unconfirmed_users. Here, because 'Candace' is last in the unconfirmed_users list, 
her name will be the first to be removed, stored in current_user, and added to the confirmed_users list. Next is Brian, then Alice. When the list of unconfirmed users is empty, the loop stops and the list of confirmed users is printed:

```python
Verifying user: Candace
Verifying user: Brian
Verifying user: Alice

The following users have been confirmed:
Candace
Brian
Alice
```

## Using `while` loops with dictionaries
We can make use of `while` loop that prompts for user's name and responses. We’ll store the data we gather in a dictionary, because we want to connect each response with a particular user. Let's see an [example](https://github.com/colinat/Python/blob/main/examples/mountain_poll.py) below: 

```python
responses = {}

# Set a flag to indicate that polling is active.
polling_active = True
while polling_active:
    # Prompt for the person's name and response.
    name = input("\nWhat is your name? ")
    response = input("Which mountain would you like to climb someday? ")
    
    # Store the response in the dictionary:
    responses[name] = response
    

    # Find out if anyone else is going to take the poll.
    repeat = input("Would you like to let another person respond? (yes/ no) ")
    if repeat == 'no':
        polling_active = False
        

# Polling is complete. Show the results.
print("\n--- Poll Results ---")
for name, response in responses.items():
    print(name + " would like to climb " + response + ".")
```

The program first defines an empty dictionary (responses) and sets a flag (polling_active). As long as polling_active is `True`, Python will run the code in the `while` loop. Within the loop, the user is prompted to enter their name and a mountain they’d like to climb, whereby the information is subsequently stored in the responses dictionary. User will then be asked whether or not to keep the poll running. If they enter yes, the program enters the `while` loop again. If they enter no, the polling_active flag is set to `False`, the `while` loop stops running, and the final code block displays the results:

```python
What is your name? Eric

Which mountain would you like to climb someday? Denali

Would you like to let another person respond? (yes/ no) yes

What is your name? Lynn

Which mountain would you like to climb someday? Devil's Thumb

Would you like to let another person respond? (yes/ no) no

--- Poll Results ---
Eric would like to climb Denali.
Lynn would like to climb Devil's Thumb.
```


## Summary

+ A loop means repeating something multiple times.
+ `for` loops can be used for repeating something to each item in a list or a dictionary.
+ You can easily make a list of sequential numbers using `range()`.
+ `while` loops repeat something as long as a condition is true, and they check the condition only in the beginning.
+ `break` allows you to terminate or exit from a loop.
+ `continue` exits from the current loop iteration; it will continue with the remaining iterations without terminating the loop.
+ `while` loops are useful when processing items in a list or when filling a dictionary
---

[<< Prev](https://github.com/colinat/Python/blob/main/basics/chapter-06.md) | [Next >>](https://github.com/colinat/Python/blob/main/basics/chapter-08.md)

[Back to list of contents](https://github.com/colinat/Python)
