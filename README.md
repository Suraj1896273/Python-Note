Python Full Notes (Basic to Advanced)
What is Python?

Python is a high-level, easy-to-learn programming language created by Guido van Rossum.

Features
Easy syntax
Fast development
Object Oriented
Huge libraries
Used in:
Web Development
AI/ML
Data Science
Automation
Cyber Security
1. Python Syntax
```python
print("Hello World")
```
Variables
name = "Suraj"
age = 20
price = 99.5

print(name)
print(age)
print(price)
2. Data Types
Type	Example
int	10
float	10.5
str	"Hello"
bool	True
list	[1,2,3]
tuple	(1,2,3)
set	{1,2,3}
dict	{"a":1}
Check Type
x = 10
print(type(x))
3. Input & Output
name = input("Enter your name : ")
print("Hello", name)
Integer Input
num = int(input("Enter number : "))
print(num)
4. Operators
Arithmetic Operators
a = 10
b = 5

print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a % b)
print(a ** b)
5. Conditional Statements
if
age = 18

if age >= 18:
    print("Adult")
if-else
num = 5

if num % 2 == 0:
    print("Even")
else:
    print("Odd")
if-elif-else
marks = 85

if marks >= 90:
    print("A")
elif marks >= 70:
    print("B")
else:
    print("C")
6. Loops
for loop
for i in range(5):
    print(i)
while loop
i = 1

while i <= 5:
    print(i)
    i += 1
7. Pattern Programs
Star Pattern
rows = 5

for i in range(rows):
    print("* " * (i + 1))
Pyramid Pattern
rows = 5

for i in range(rows):
    print(" " * (rows - i - 1) + "* " * (i + 1))
Diamond Pattern
rows = 5

for i in range(rows):
    print(" "*(rows-i-1) + "* "*(i+1))

for i in range(rows-1):
    print(" "*(i+1) + "* "*(rows-i-1))
8. Strings
name = "Python"
print(name[0])
print(len(name))
String Slicing
text = "Programming"

print(text[0:5])
print(text[::-1])
Reverse String
text = "hello"

print(text[::-1])
9. Lists
numbers = [1,2,3,4]

print(numbers)
print(numbers[0])
List Methods
numbers.append(5)
numbers.remove(2)
numbers.sort()

print(numbers)
Loop Through List
for i in numbers:
    print(i)
10. Tuples
data = (1,2,3)

print(data[0])
11. Sets
nums = {1,2,3,3,4}

print(nums)
12. Dictionaries
student = {
    "name": "Suraj",
    "age": 20
}

print(student["name"])
Loop Dictionary
for key, value in student.items():
    print(key, value)
13. Functions
Simple Function
def greet():
    print("Hello")

greet()
Function with Parameters
def add(a, b):
    return a + b

result = add(5, 3)

print(result)
14. Recursion
def printNums(n):
    if n == 1:
        print(n)
        return

    printNums(n - 1)
    print(n)

printNums(5)
15. Lambda Function
square = lambda x: x * x

print(square(5))
With map()
nums = [1,2,3]

result = list(map(lambda x: x*2, nums))

print(result)
