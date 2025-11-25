# 🧱 Basic Structure of a Program

1. Function definitions
```python
def name():
    ...
```

2. Initial variables
```python
variable = 0
list_name = []
running = True
```
    
3. Main loop
```python
while running:
    ...
```

4. Display menu
```python
print("1 - Option 1")
print("2 - Option 2")
print("3 - Exit")
```

5. Input + input validation (number)
```python
user_input = input("Choice: ")

try:
    value = int(user_input)
except ValueError:
    print("Please enter a number.")
    continue
```

---

# 🧩 Commands & Functions

## Input & Output
```python
user_input = input("Text: ")
print(user_input)
```

## Random
```python
import random
number = random.randint(1, max_value)
```

## Conditions
```python
if condition:
    ...
elif other_condition:
    ...
else:
    ...
```

## Comparisons
```python
==  !=  >  <  >=  <=
```

---

# 🔄 Loops

## while loop
```python
while True:
    ...
    if condition:
        break        # ends only the current loop
    if other_condition:
        continue     # jumps to loop start
```

## for loop
```python
for i in range(5):
    print(i)
```

---

# 🔎 Conditions, in / not in, Parentheses

```python
if letter in word:     # checks if letter is in word
    ...

if letter not in word: # checks if letter is not in word
    ...
```

Important for and, or, not:
```python
while not (len(user_input) == 1 and user_input in "abcdefghijklmnopqrstuvwxyz"):
    print("please enter letter a-z")
    user_input = input("enter again: ")
```

---

# 🔎 String Methods

```python
text.isalpha()   # only letters?
text.isdigit()   # only digits?
text.upper()     # all UPPERCASE
text.lower()     # all lowercase
```

---

# 🧮 Arithmetic Operators

```python
+   -   *   /    # Basic arithmetic
%                # Modulo: remainder of division
//               # Integer division
```

---

# 📚 Lists

Basic commands
```python
my_list = []
my_list.append(value)
len(my_list)
sum(my_list)
min(my_list)
max(my_list)
my_list[index]
```

Splitting strings / Extending lists
```python
parts = text.split()              # split string into list of strings
my_list.extend(new_elements)      # extend list with elements from another list
```

Loop over list
```python
for x in my_list:
    print(x)

length = len(my_list)
```

---

# 🟩 Functions & Return Values

```python
def function(x):
    return x
```

---

# 📌 Patterns from Your Programs

## Copy list
```python
copy = []
counter = 0
while counter < len(original):
    copy.append(original[counter])
    counter += 1
```

## Sort list
```python
sorted_list = []
while len(copy) > 0:
    small = min(copy)
    sorted_list.append(small)
    copy.remove(small)
```

## Calculate median
```python
if len(sorted_list) % 2 == 0:
    middle = len(sorted_list) // 2
    median = (sorted_list[middle - 1] + sorted_list[middle]) / 2
else:
    median = sorted_list[len(sorted_list) // 2]
```

---

# ❗ Common Errors

```python
my_list = my_list.append(...)   # wrong
my_list.append(value)           # correct

median_list = attempts          # wrong (not a copy)
# correct copy process: see "Copy list"

break  # does NOT end the whole program, only the loop
```
