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
Types of Methods in Python
1. Instance Method

Works with object variables.

class A:

    def show(self):
        print("Instance Method")
2. Class Method

Works with class variables.

Decorator used:

@classmethod

Example:

class Car:

    company = "TATA"

    @classmethod
    def show(cls):
        print(cls.company)

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
