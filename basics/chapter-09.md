# Classes

A class is a kind of data type. In object-oriented programming you write classes that represent real-world things and situations, and you create objects based on these classes. When you create individual objects from that data type, we call it an instance of a class. You can model almost anything using classes.

The data values which we store inside an object are called attributes, and the functions which are associated with the object are called methods. Below is an example of a simple custom class which models a dog:

```python
class Dog():
    """A simple attempt to model a dog"""    
    def __init__(self, name, age):
        """Initialise name and age attributes."""
        self.name = name
        self.age = age
        
    def sit(self):
        """Simulate a dog sitting in response to a command."""
        print(self.name.title() + " is now sitting.")
    
    def roll_over(self):
        """Simulate rolling over in response to a command."""
        print(self.name.title() + " rolled over!")                
```
Things to note about the class:
+ Each instance created from the Dog class will store a name and an age, and we’ll give each dog the ability to `sit()` and `roll_over()`. 
+ These functions which are part of a class are called methods. 
+ By convention, capitalized names refer to classes in Python. 
+ The parentheses in the class definition are empty because we’re creating this class from scratch.


## The __init()__ constructor

The first function is called `__init__()`, which is a special method. The purpose of this method is thus to set up a new object using data that we have provided. Note that this method has two leading underscores and two trailing underscores on each side of `__init__()`; these are called _dunders_. Names that have dunders are reserved for special use in Python. Basically, we are overloading the `__init__()` method in the example above.

We define the `__init()__` method to have three parameters: `self`, name and age. The `self` parameter is required and it must come first before other parameters. Every method call associated with an instance automatically passes self, which is a reference to the instance itself; it gives the individual instance access to the attributes and methods in the class.

We'll need to provide values for only the other parameters in this case; we don't need to pass self as it is automatically passed into the parameter in Python.


## Creating instances from a class
We can now tell Python to make an instance representing a specific dog:

```python
>>> # creating class instance of Dog and assign to object variable my_dog
>>> my_dog = Dog("Willie", 5)
```

### Accessing attributes
To access the attributes of an instance, you use the dot notation. We can access the value of my_dog’s attribute name by writing:

```python
>>> print("my_dog.name")
Willie
>>># accessing dog's attributes - name and age
>>>print(f"My dog's name is {my_dog.name}.")
My dog's name is Willie.
>>> print(f"My dog is {my_dog.age} years old.")
My dog is 5 years old.
```

### Calling methods
We can call any method defined in the class *Dog*. For example:

```python
>>># calling object methods
>>>my_dog.sit()
Willie is now sitting.
>>>my_dog.roll_over()
Willie rolled over!
```

### Creating multiple instances
You can create as many instances from a class as you need. Let's create a second dog:

```python
# define another instance of class Dog
neighbours_dog = Dog('Lucy', 3)


# testing out
print(f"My dog's name is {my_dog.name}.")
print(f"My dog is {my_dog.age} years old.")
my_dog.sit()

print(f"\nMy neighbour's dog is named {neighbours_dog.name}.")
print(f"My neighbour's dog is {neighbours_dog.age}.")
neighbours_dog.roll_over()

```

Output:
```python
My dog's name is Willie.
My dog is 5 years old.
Willie is now sitting.

My neighbour's dog is named Lucy.
My neighbour's dog is 3.
Lucy rolled over!
```


## Inheritance
It's not necessary to start from scratch when writing a class - you can use *inheritance*. When one class inherits from another, it takes on the attributes and methods of the parent class; the class that inherits from the parent is the child class, and it can define new attributes and methods of its own.

Here is an example of inheritance:

```python
class Car:
    """A simple attempt to model a car"""
    
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
    
    @property
    def get_descriptive_name(self):
        return f"{self.year} {self.make} {self.model}"
    
    def read_odometer(self):
        print(f"This car has {self.odometer_reading} miles on it.")
    
    def update_odometer(self, mileage):
        if mileage >= self.odometer_reading: 
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")
            
    def increment_odometer(self, miles):
        self.odometer_reading += miles
        
        
# inheriting from class Car
class ElectricCar(Car):
    """Represent aspects of a car, specific to electric vehicles"""
    
    def __init__(self, make, model, year):
        """Initialise attributes of the parent class"""
        
        # calling method from parent class
        super().__init__(make, model, year)
        self.battery_size = 75

    # the parent class will not have this
    def describe_battery(self):
        """Print a statement describing the battery size"""
        print(f"This car has a {self.battery_size}-kWh battery.")
        
my_tesla = ElectricCar('tesla', 'model s', 2019)
print(my_tesla.get_descriptive_name)
my_tesla.describe_battery()
```

Output:

```python
2019 tesla model s
This car has a 75-kWh battery.
```


## Importing classes
You can import the classes stored in modules into your main program in Python. For example, we can store class definitions into a separate file named _car.py_ and import the classes from that module. You can import as many classes as you need as well:

```Python
from car import Car, ElectricCar

my_tesla = ElectricCar('tesla', 'model s', 2019)
print(my_tesla.get_descriptive_name)
my_tesla.describe_battery()
```

Output:

```python
2019 tesla model s
This car has a 75-kWh battery.
```

### Different ways of importing
Apart from the above which import only specific specific classes/methods, there are other various ways of importing a class/module as shown below:

```python
# import entire module
import car

# import all classes from a module
from car import *
```

You can use an alias for the imported module...

```python
# using alias
from car import ElectricCar as EC
```


## Summary

+ You've learn classes that provide a means of bundling data and functionality together in Python. 
+ Each class instance can have attributes attached to it.
+ Class instances can also have methods.

---

[<< Prev](https://github.com/colinat/Python/blob/main/basics/chapter-08.md) | [Next >>]()

[Back to list of contents](https://github.com/colinat/Python)
