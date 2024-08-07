### **Python Basics**

**Print to Console:**
```python
print("Hello, World!")
```

**Variables:**
```python
x = 10
name = "Alice"
```

**Data Types:**
```python
integer = 10
floating_point = 10.5
string = "Hello"
boolean = True
```

**Lists:**
```python
my_list = [1, 2, 3, 4]
print(my_list[0])  # Output: 1
my_list.append(5)  # Adds 5 to the end of the list
my_list.insert(2, 10)  # Inserts 10 at index 2
my_list.remove(10)  # Removes the first occurrence of 10
popped_value = my_list.pop()  # Removes and returns the last item
index_of_3 = my_list.index(3)  # Finds the index of the first occurrence of 3
count_of_1 = my_list.count(1)  # Counts occurrences of 1
```

**Tuples:**
```python
my_tuple = (1, 2, 3)
print(my_tuple[1])  # Output: 2
```

**Dictionaries:**
```python
my_dict = {"name": "Alice", "age": 25}
print(my_dict["name"])  # Output: Alice

# Methods
value = my_dict.get("name")  # Retrieves value for key "name"
my_dict.update({"age": 26})  # Updates the value for key "age"
del my_dict["name"]  # Deletes the key "name"
keys = my_dict.keys()  # Returns a view of dictionary keys
values = my_dict.values()  # Returns a view of dictionary values
items = my_dict.items()  # Returns a view of dictionary key-value pairs
```

### **Control Flow**

**If Statements:**
```python
x = 10
if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x is 5")
else:
    print("x is less than 5")
```

**Loops:**

*For Loop:*
```python
for i in range(5):
    print(i)
```

*While Loop:*
```python
i = 0
while i < 5:
    print(i)
    i += 1
```

### **Functions**

**Defining a Function:**
```python
def greet(name):
    return f"Hello, {name}!"
```

**Calling a Function:**
```python
print(greet("Alice"))
```

**Lambda Function:**
```python
square = lambda x: x**2
print(square(4))  # Output: 16
```

### **Classes and Objects**

**Class Definition:**
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hello, my name is {self.name}."
    
    def is_adult(self):
        return self.age >= 18
```

**Creating an Object:**
```python
person = Person("Alice", 25)
print(person.greet())
print(person.is_adult())
```

### **Exception Handling**

**Try and Except:**
```python
try:
    x = 1 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
```

### **File Handling**

**Reading a File:**
```python
with open('file.txt', 'r') as file:
    content = file.read()
    print(content)
```

**Writing to a File:**
```python
with open('file.txt', 'w') as file:
    file.write("Hello, World!")
```

### **List Comprehensions**

**Basic List Comprehension:**
```python
squares = [x**2 for x in range(10)]
print(squares)
```

**Conditional List Comprehension:**
```python
even_squares = [x**2 for x in range(10) if x % 2 == 0]
print(even_squares)
```

### **String Methods**

**Basic String Operations:**
```python
s = "Hello, World!"

# Length
print(len(s))  # Output: 13

# Uppercase
print(s.upper())  # Output: HELLO, WORLD!

# Lowercase
print(s.lower())  # Output: hello, world!

# Replace
print(s.replace("World", "Python"))  # Output: Hello, Python!

# Split
words = s.split(", ")
print(words)  # Output: ['Hello', 'World!']

# Strip
s2 = "   Hello   "
print(s2.strip())  # Output: Hello
```

### **Additional Methods and Functions**

**Sorting:**

*Sort a List:*
```python
my_list = [3, 1, 4, 1, 5]
my_list.sort()  # Sorts in place
print(my_list)  # Output: [1, 1, 3, 4, 5]
```

*Sorted Function:*
```python
sorted_list = sorted([3, 1, 4, 1, 5])  # Returns a new sorted list
print(sorted_list)  # Output: [1, 1, 3, 4, 5]
```

**Map, Filter, and Reduce:**

*Map Function:*
```python
numbers = [1, 2, 3]
squared_numbers = list(map(lambda x: x**2, numbers))
print(squared_numbers)  # Output: [1, 4, 9]
```

*Filter Function:*
```python
numbers = [1, 2, 3, 4, 5]
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print(even_numbers)  # Output: [2, 4]
```

*Reduce Function:*
```python
from functools import reduce

numbers = [1, 2, 3, 4]
sum_of_numbers = reduce(lambda x, y: x + y, numbers)
print(sum_of_numbers)  # Output: 10
```

Feel free to ask if you need more details or additional methods!
