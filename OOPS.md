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
## Constructor in Python

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

## What is instence variable  :-   Instence variables are the variables whose separate copy is created in every object
                                    
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
## Difference between Function and Method

| Function                           | Method                              |
| ---------------------------------- | ----------------------------------- |
| Independent block of code          | Function inside a class/object      |
| Does not belong to an object       | Belongs to an object/class          |
| Called directly                    | Called using object                 |
| Syntax: `function()`               | Syntax: `object.method()`           |
| Cannot directly access object data | Can access object data using `self` |           


Types of Methods in Python
## 1. Instance Method  :-   An intstance method that works object data [instence variable].

```python
   class car :
     def __init__(self , brand):
         self.brand = brand
     def display(self):

   C1 = car("BMW")
   C1.disply
```


## 2. Class Method   :-  A class method is a method that works with class variables.  It works with cls parameter and created using @classmethod

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

   Car.show()
```

## 3. Static Method  :-  Independent utility method.

```python
class Addition:

   @staticmethod
   def add(a, b):
      return a + b
 print(Addition.add(2,3))
```

## Instance Method VS Class Mthod VS Static Method

| Instance Method               | Class Method                    | Static Method                                   |
| ----------------------------- | ------------------------------- | ----------------------------------------------- |
| Works with object data        | Works with class data           | Utility/helper function                         |
| Uses `self`                   | Uses `cls`                      | No `self` or `cls`                              |
| Can access instance variables | Can access class variables      | Cannot directly access instance/class variables |
| Called using object           | Called using class/object       | Called using class/object                       |
| Most commonly used            | Used for class-level operations | Used for helper tasks                           |


## What is Inheritance ?

Inheritance is an OOP concept where one class acquires the properties and methods of another class.

It helps in:

Code reusability
Reducing duplicate code
Creating parent-child relationships between classes.

```python
class Animal:
    def sound(self):
        print("Animal makes sound")

class Dog(Animal):
    pass

d = Dog()
d.sound()
```
## Advantages :- 

1. Reuse code
2. Less coding
3. Easy to manage
4. Improves readability
5. Supports polymorphism


## What is super() Method?
The super() method is used to access methods and constructors of the parent class from the child class.

It is mainly used in Inheritance.

## Why Use super()?

Suppose a child class wants to use the parent class constructor or methods without rewriting the same code.

## Features :-

1. Reuse parent class code.
2. Avoid duplicate code.
3. Call parent constructor easily.
4. Easier in large project.
```python
class Company:
    def __init__(self, name):
        self.name = name

class Employee(Company):
    def __init__(self, name, salary):
        super().__init__(name)
        self.salary = salary

    def show(self):
        print("Name :", self.name)
        print("Salary :", self.salary)

e1 = Employee("Suraj", 50000)
e1.show()
```
