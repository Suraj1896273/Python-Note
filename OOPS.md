## What is OOP?

OOP stands for Object-Oriented Programming.

Think about a Car.

A car has:

Properties → color, model, price
Behaviors → start(), stop()

In OOP:

Car = Class
Real car = Object
## What is a Class?

A class is a blueprint or template for creating objects.

Example:

```python
class Car:
    pass
```

## What is an Object?

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
## What is self?

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

## What is instence variable  :-   
Instence variables are the variables whose separate copy is created in every object

Instence variables are defined and initilized using a constructor with self parameter


## Methods in Class:-

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

## 1. Instance Method  :-  
  An instance method is a method that belongs to an object (instance) of a class. It always takes self as its first parameter, which refers to the current object.

```python
 class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print("Name:", self.name)
        print("Age:", self.age)


s1 = Student("Suraj", 20)

s1.display()
```


## 2. Class Method   :-  
 A class method is a method that works with class variables.  It works with cls parameter and created using @classmethod

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

## 3. Static Method  :-  
A static method is a method that belongs to the class, not to any object.
It does not use self or cls.It created using @staticmethod.

- It can be called directly using the class name, so there is no need to create an object.

```python
class Addition:

   @staticmethod
   def add(a, b):
      return a + b
 print(Addition.add(2,3))
```

## Instance Method VS Class Mthod VS Static Method

| Instance Method                                       | Class Method                                                         | Static Method                                      |
| ----------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------- |
| Works with **object (instance) data**                 | Works with **class data**                                            | Utility/helper function                            |
| Uses **`self`** as the first parameter                | Uses **`cls`** as the first parameter                                | Uses **no `self` or `cls`**                        |
| Can access **instance variables** and class variables | Can access **class variables** (and create/modify them)              | Cannot directly access instance or class variables |
| Usually called using an **object**                    | Can be called using the **class or an object**                       | Can be called using the **class or an object**     |
| Most commonly used for **object-specific behavior**   | Used for **class-level operations** (e.g., alternative constructors) | Used for **helper/utility tasks**                  |



## What is Inheritance ?

Inheritance is an OOP concept where one class acquires the properties and methods of another class.

It helps in:

i)Code reusability

ii)Reducing duplicate code

iii)Creating parent-child relationships between classes.

## What is Method Overriding?

Method overriding is the process of redefining a parent class method in the child class using the same method name and parameters.

i)The method name must be the same.

ii)The parameters should usually be the same.

iii)SWhen an object of the child class calls the method, the child class version is executed instead of the parent's version.

```python class Animal:
    def sound(self):
        print("Animal makes a sound")

class Dog(Animal):
    def sound(self):
        print("Dog barks")

class Cat(Animal):
    def sound(self):
        print("Cat meows")

dog = Dog()
cat = Cat()

dog.sound()
cat.sound()
```
## Output
Dog barks
Cat meows

Here every animal has a sound() method, but each animal behaves differently.

## Method Overloading vs Method Overriding

| **Method Overloading** | **Method Overriding** |
|------------------------|-----------------------|
| Same method name with **different parameters**. | Same method name with the **same parameters**. |
| Python does **not support true method overloading** directly. | Python **fully supports method overriding**. |
| Occurs **within the same class**. | Occurs **between a parent class and a child class**. |
| **Inheritance is not required.** | **Inheritance is required.** |
| Used to perform **different tasks using the same method name**. | Used to **change or customize the behavior** of an inherited method. |
| Achieves **Compile-time Polymorphism** (in languages like Java and C++). | Achieves **Runtime Polymorphism**. |
| Considered a **compile-time concept** (in languages that support it). | Considered a **runtime concept**. |

## Advantages:-

Achieves runtime polymorphism.
Makes code more flexible.
Improves reusability.
Allows customization of inherited methods.
Makes programs easier to maintain.

## Disadvantages:-
Can make code harder to follow if many classes override the same method.
Incorrect overriding may introduce bugs.
Overridden parent behavior is hidden unless super() is used.

## Single Inheritance :- Single inheritance is a type of inheritance in which one child class inherits the properties and methods of one parent class.

```python
class Parent:
    def show(self):
        print("This is the Parent class.")

class Child(Parent):
    def display(self):
        print("This is the Child class.")

obj = Child()
obj.show()      # Inherited from Parent
obj.display()   # Child's own method
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

## What is Multiple Inheritance ?
Multiple Inheritance means :- One child class inherits properties and methods from more than one parent class.

## Syntax :-

```python
class Parent1:
    pass

class Parent2:
    pass

class Child(Parent1, Parent2):
    pass
```

## Diagram :-

        Father      Mother
            \       /
             \     /
              Child
## Method Overriding in Multiple Inheritance :-

```python

 class A:
    def show(self):
        print("A class")

class B:
    def show(self):
        print("B class")

class C(A, B):
    pass

c = C()
c.show()
```
## Output :- A class , Because Python checks A first.

## Method Resolution Order (MRO) :- 

Method Resolution Order (MRO) is the order in which Python searches classes to find a method or attribute. It is mainly used in inheritance, especially multiple inheritance, to determine which method should be called first.

## Rules of MRO:-

i)Python first checks the current class.

ii)If not found, it checks the parent classes from left to right.

iii)If still not found, it checks the object class.

```python
class Human:
    def work(self):
        print("I can work")

class Male:
    def work(self):
        print("I can code")

class Boy(Human, Male):
    pass

obj = Boy()
obj.work()
```
## Output:-
I can work

## Reason: Human comes before Male, so Python checks Human first.

## Diagram :-
Boy
 ↓
Human
 ↓
Male
 ↓
object

## Check MRO :-

(1) Boy.__mro__

(2) Boy.mro()

## Output :-
(<class '__main__.C'>,
 <class '__main__.A'>,
 <class '__main__.B'>,
 <class 'object'>)

 ## Advantages of Multiple Inheritance :- 

 i)Multiple inheritance allows a class to inherit features from more than one parent class.

 ii)It helps in code reuse, because methods and attributes from multiple classes can be used without rewriting them.

 iii)It also reduces code duplication, making programs shorter and easier to maintain.

 iv)t also improves code organization.

 ## Disadvantages:-

 i)Multiple inheritance can make programs more complex.

 ii)It may create confusion if different parent classes contain methods with the same name.

 iii)Because of the complex inheritance structure, debugging becomes more difficult.
 
## Multilevel Inheritance

## Definition:-

Multilevel Inheritance is a type of inheritance where one class inherits from another class, and then a third class inherits from that derived class. This creates a chain of inheritance.

## In simple words:

Grandparent Class → Parent Class → Child Class

The child class can access the properties and methods of both the parent and grandparent classes.

## Syntax:

```python
class A:
    pass

class B(A):
    pass

class C(B):
    pass
```
Here:

A = Base (Parent) Class
B = Derived Class of A
C = Derived Class of B

C can access features of both A and B.

## Diagram
      A
      |
      B
      |
      C
      
## Example Program:

```python
class Human:
    def eat(self):
        print("I can eat")

class Male(Human):
    def sleep(self):
        print("I can sleep")

class Boy(Male):
    def play(self):
        print("I can play")

boy1 = Boy()

boy1.eat()
boy1.sleep()
boy1.play()
```
## Output

I can eat
I can sleep
I can play

## How It Works

Step 1

Human class contains:

eat()
Step 2

Male inherits Human:

class Male(Human):

Now Male can use:

eat()
sleep()
Step 3

Boy inherits Male:

class Boy(Male):

Now Boy can use:

eat()
sleep()
play()

## Constructor Example:
```python
class Person:
    def __init__(self, name):
        self.name = name

class Student(Person):
    def __init__(self, name, course):
        super().__init__(name)
        self.course = course

class Monitor(Student):
    def __init__(self, name, course, section):
        super().__init__(name, course)
        self.section = section

obj = Monitor("Suraj", "CSE", "A")

print(obj.name)
print(obj.course)
print(obj.section)
```
Output:

Suraj
CSE
A

## Method Resolution Order (MRO)

Python searches for methods in this order:

Boy
 ↓
Male
 ↓
Human
 ↓
object

Example:

```python
class Human:
    def show(self):
        print("Human Class")

class Male(Human):
    pass

class Boy(Male):
    pass

b = Boy()
b.show()
```

## Output:

Human Class

Python first checks Boy, then Male, then Human.

## Real-Life Example:

```python
class Person:
    def get_name(self):
        print("Person Details")

class Student(Person):
    def get_course(self):
        print("Course Details")

class RegularStudent(Student):
    def get_attendance(self):
        print("Attendance Details")
```

## Here:

Person stores basic information.

Student stores academic information.

RegularStudent stores attendance information.

## Advantages of Multilevel Inheritance:-

- Code reusability.

- Reduce code duplication.

- Easy to extend

- Easy maintenance.

- Represents Real-Life Relationships

## Disadvantages of Multilevel Inheritance:-

- Complex Code.
  
- Difficult Debugging.
  
- Parent Changes Affect Child Classes

- Complex raed ability.

- Too Many Levels Make Code Confusing

## Hierarchical Inheritance (Python)
## Definition:-

Hierarchical Inheritance is a type of inheritance where one parent class is inherited by two or more child classes.

## In simple words:

One Parent → Many Child Classes

## Diagram :-
          Person
         /      \
        /        \
    Student     Teacher

   Here,

- Person is the Parent (Base) Class.
- Student and Teacher are Child (Derived) Classes.

- Both child classes inherit the properties and methods of the Person class.

```python
 class Person:
    def __init__(self, name):
        self.name = name

    def display(self):
        print("Name:", self.name)


class Student(Person):
    def study(self):
        print("Student is studying")


class Teacher(Person):
    def teach(self):
        print("Teacher is teaching")


student = Student("Suraj")
teacher = Teacher("Rahul")

student.display()
student.study()

teacher.display()
teacher.teach()
```
## Output:-
Name: Suraj
Student is studying
Name: Rahul
Teacher is teaching

## Advantages:-

- Code Reusability.
- Less Code Duplication.
- Easy Maintenance.
- Easy to Add New Child Classes.
- Represents Real-Life Relationships.
  
## Disadvantages:-

- Parent Class Changes Affect All Child Classes.
- Code Can Become Complex.
- Difficult to Debug.
- More Child Classes Make the Program Hard to Manage.

## Hybrid Inheritance:-
## What is Hybrid Inheritance?

Hybrid Inheritance is a combination of two or more types of inheritance in a single program.

It combines inheritance types such as:-

- Single Inheritance
- Multiple Inheritance
- Multilevel Inheritance
- Hierarchical Inheritance

## In simple words:

Hybrid Inheritance means using different inheritance types together to build a complex class structure.

## Structure

Example:

        A
       / \
      B   C
       \ /
        D

Here,

- B and C inherit from A (Hierarchical Inheritance).
- D inherits from both B and C (Multiple Inheritance).

Since two inheritance types are combined, it is called Hybrid Inheritance.

Python Example:-
```python
class Person:
    def show_person(self):
        print("Person Details")


class Student(Person):
    def show_student(self):
        print("Student Details")


class Teacher(Person):
    def show_teacher(self):
        print("Teacher Details")


class Monitor(Student, Teacher):
    def show_monitor(self):
        print("Monitor Details")


obj = Monitor()

obj.show_person()
obj.show_student()
obj.show_teacher()
obj.show_monitor()
```
## Output
Person Details
Student Details
Teacher Details
Monitor Details

## How it Works:-
- Step 1

Person is the base class.

Person
- Step 2

Student and Teacher inherit from Person.

        Person
       /      \
    Student  Teacher

This is Hierarchical Inheritance.

- Step 3

Monitor inherits from both Student and Teacher.

Student
     \
      \
     Monitor
      /
Teacher

This is Multiple Inheritance.

Final Structure
          Person
         /      \
    Student    Teacher
         \      /
         Monitor

Since Hierarchical + Multiple are combined, it becomes Hybrid Inheritance.

## Advantages of Hybrid Inheritance:-

- Code Reusability

- Common code can be written once and reused by many classes.

- Reduces Duplicate Code

- The same methods and attributes do not need to be written repeatedly.

- Flexible Design

- Different inheritance relationships can be combined in one project.

- Better Organization

## Disadvantages of Hybrid Inheritance:-

- Complex Structure

- The class hierarchy can become difficult to understand.

- Diamond Problem

- Hard to Debug

- Maintenance Becomes Difficult

- Changes in one parent class can affect many child classes.

- Not Suitable for Small Projects

## Method Resolution Order (MRO):-

Python uses Method Resolution Order (MRO) to decide which parent's method should be called first.

Example:
```python
class A:
    def show(self):
        print("A")


class B(A):
    def show(self):
        print("B")


class C(A):
    def show(self):
        print("C")


class D(B, C):
    pass


obj = D()
obj.show()
```
## Output:- B

Why?

Python checks classes in this order:

print(D.mro())

Output:

[D, B, C, A, object]

So Python finds show() in B first and calls it.
