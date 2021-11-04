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

The first function is called `__init__()`, which is a special method. The purpose of this method is thus to set up a new object using data that we have provided. Note that this method has two leading underscores and two trailing underscores on each side of `__init__()`; these are called dunders. Names that have dunders are reserved for special use in Python. Basically, we are overloading the `__init__()` method in the example above.

We define the `__init()__` method to have three parameters: `self`, name and age. The `self` parameter is required and it must come first before other parameters. Every method call associated with an instance automatically passes self, which is a reference to the instance itself; it gives the individual instance access to the attributes and methods in the class.

We'll need to provide values for only the other parameters in this case; we don't need to pass self as it is automatically passed into the parameter in Python.


## Creating instances from a class
We can now tell Python to make an instance representing a specific dog:

```python
>>> # creating class instance of Dog and assign to object variable my_dog
>>> my_dog = Dog("Willie", 5)
>>> # accessing dog's attributes - name and age
>>> print(f"My dog's name is {my_dog.name}.")
My dog's name is Willie.
>>> print(f"My dog is {my_dog.age} years old.")
My dog is 5 years old.
```

### Accessing attributes
To access the attributes of an instance, you use dot notation. At v we access 
the value of my_dog’s attribute name by writing:


### Calling methods



### Creating multiple instances




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



## Summary

You've learn what are some of the IDEs and code editors that can help you embark on Python coding projects. 

---

[<< Prev](https://github.com/colinat/Python/blob/main/basics/functions.md) | [Next >>]()

[Back to list of contents](https://github.com/colinat/Python)