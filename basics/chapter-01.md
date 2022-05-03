# What is Python?

Python is an interpreted, object-oriented, high-level programming language with dynamic semantics. Python's simple, easy to learn syntax emphasizes readability and therefore reduces the cost of program maintenance. Python supports modules and packages, which encourages program modularity and code reuse.


## What do I need

Python comes with an interpreter that runs in a terminal window, allowing you to try bits of Python without having to save and run an entire program. The Python interpreter is freely available in source or binary form for all major platforms from the Python [web site](https://www.python.org/), and may be freely distributed. 

*Note: On Unix, the Python 3.x interpreter is by default not installed with the executable named python, so that it does not conflict with a simultaneously installed Python 2.x executable.*


## Installing Python
You can download Python from the [website](https://www.python.org/downloads/). After you’ve downloaded the file, run the installer.


## Running Python

### Windows
1. Launch a command/powershell window.

2. Type `python` and press `Enter`. You should see something like this:

![Python on Windows](https://github.com/colinat/Python/blob/main/media/python_cmdprompt.png)


### Mac/Linux
1. Launch a terminal window. 

2. Type `python3` and press `Enter`. You should see something like this:

![Python on Linux](https://github.com/colinat/Python/blob/main/media/python_terminal.png)


## Interactive mode
The `>>>` means that Python is ready and we can enter a command. The basic idea is really simple: we enter a command, press `Enter`, enter another command, press `Enter` and keep going.

Now let's type `print('Hello world!')` after prompt (`>>>`) and press `Enter`. You should see the output being printed.

```python
>>> print("Hello world!")
Hello world!
>>> 
```

To exit the Python interpreter, type `exit()` and press `Enter`. 

```python
>>> exit()
```


## Running Python program

To start your first python program, launch a text editor. Save an empty Python file called `hello_world.py`. The extension `.py` tells the operating system that your file will contain a Python program. In the file, enter the following line:

```python
print("Hello world!")
```

Now saved the [file](https://github.com/colinat/Python/blob/main/examples/hello_world.py). Open a new terminal window, go to the folder where you have saved the file earlier. 
Type `python hello_world.py` in the terminal window. You should see the following output:

```python
$ python hello_world.py 
Hello world!
$
```



## Summary

You've learn a bit about Python and able to run Python code in a terminal session. 

---

[Next >>](https://github.com/colinat/Python/blob/main/basics/ides-and-code-editors.md)

[Back to list of contents](https://github.com/colinat/Python)



