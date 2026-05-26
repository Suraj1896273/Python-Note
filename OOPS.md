What is OOP?

OOP stands for Object-Oriented Programming.

Think about a Car.

A car has:

Properties → color, model, price
Behaviors → start(), stop()

In OOP:

Car = Class
Real car = Object
What is a Class?

A class is a blueprint or template for creating objects.

Example:

```python
class Car:
    pass
```

What is an Object?

An object is an instance of a class.

```python
class Car:
    pass

c1 = Car()
```

Here:

c1 is an object of class Car
Creating Variables Inside Class
```python
class Student:
    name = "Suraj"
    age = 20

s1 = Student()

print(s1.name)
print(s1.age)

Output:

Suraj
20
```
Constructor in Python

Constructor is a special method:

Automatically runs when object is created
Used to initialize object data

Constructor name:

```python __init__()```
Example of Constructor
class Student:

```python
    def __init__(self, name, age):
        self.name = name
        self.age = age

s1 = Student("Suraj", 20)

print(s1.name)
print(s1.age)

```
What is self?

self refers to the current object.

Example:

self.name = name

Meaning:

Store value inside current object
Instance Variables

Variables created using self.

class Car:
```python
    def __init__(self, model):
        self.model = model
```

Here:

model is instance variable

What is instence variable  :-   Instence variables are the variables whose separate copy is created in every object
                                    
                                     *Instence variables are defined and initilized using a constructor with self parameter


Methods in Class

Functions inside class are called methods.

```python
class Student:

    def show(self):
        print("Hello")
````

Method with constructor
```python
class Student:

    def __init__(self, name):
        self.name = name

    def show(self):
        print(self.name)

s1 = Student("Suraj")
s1.show()
```

| Function                           | Method                              |
| ---------------------------------- | ----------------------------------- |
| Independent block of code          | Function inside a class/object      |
| Does not belong to an object       | Belongs to an object/class          |
| Called directly                    | Called using object                 |
| Syntax: `function()`               | Syntax: `object.method()`           |
| Cannot directly access object data | Can access object data using `self` |           


Types of Methods in Python
1. Instance Method  :-   An intstance method that works object data [instence variable].

```python
   class car :
     def __init__(self , brand):
         self.brand = brand
     def display(self):

   C1 = car("BMW")
   C1.disply
```


3. Class Method   :-  A class method is a method that works with class variables.  It works with cls parameter and created using @classmethod

   ```python
      class Car:
    company = "TATA"
    @classmethod
    def print(cls):
        print(cls.company)
    
    def __init__(self , model , price):
        self.model = model
        self.price = price

    def show(self):
        print(self.model)
        print(self.price)

c1 = Car("NANO" , 10000)
c2 = Car("Punch" , 50000)
c3 = Car("Alto" , 60000)

Car.print()
c1.show()
c2.show()
c3.show()
```

Car.show()
3. Static Method

Independent utility method.

Decorator used:

@staticmethod

Example:

class Math:

    @staticmethod
    def add(a, b):
        return a + b

print(Math.add(2,3))
Difference Between Instance, Class, and Static Method
Type	Uses
Instance Method	Works with object data
Class Method	Works with class data
Static Method	Utility/helper function
Class Variable vs Instance Variable
Class Variable

Shared by all objects.

class Car:
    company = "TATA"
Instance Variable

Different for every object.

self.model = model
Example
class Car:

    company = "TATA"

    def __init__(self, model):
        self.model = model

c1 = Car("Nano")
c2 = Car("Safari")

print(c1.company)
print(c2.company)

print(c1.model)
print(c2.model)
