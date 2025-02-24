# Python Debugging Challenge
## Find and fix the error in each code snippet!

---

### 1. List Operations
```python
fruits = ["apple", "banana", "cherry"]
print(fruits[3])
```
<details>
<summary>Hint</summary>
Check the list indexing - remember that Python uses zero-based indexing.
</details>

---

### 2. For Loop Range
```python
for i in range(1, 10, 2)
    print(i)
```
<details>
<summary>Hint</summary>
Check the syntax of the for loop statement.
</details>

---

### 3. Variable Scope
```python
def calculate_area():
    width = 5
    height = 10
    area = width * height

print(area)
```
<details>
<summary>Hint</summary>
Think about where variables are defined and where they can be accessed.
</details>

---

### 4. String Formatting
```python
name = "Alice"
age = 20
print("My name is" + name + "and I am" + age + "years old.")
```
<details>
<summary>Hint</summary>
Check the data types being concatenated.
</details>

---

### 5. Class Definition
```python
class Rectangle
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height
```
<details>
<summary>Hint</summary>
Look at the class definition syntax.
</details>

---

### 6. While Loop Condition
```python
counter = 0
while counter < 5
    print(counter)
    counter += 1
```
<details>
<summary>Hint</summary>
Check the syntax of the while loop statement.
</details>

---

### 7. List Comprehension
```python
numbers = [1, 2, 3, 4, 5]
squared = [x^2 for x in numbers]
print(squared)
```
<details>
<summary>Hint</summary>
Check the operator being used to square numbers.
</details>

---

### 8. Pygame Event Loop
```python
import pygame
pygame.init()
screen = pygame.display.set_mode((800, 600))
running = True

while running:
    for event in pygame.event:  # Error is here
        if event.type == pygame.QUIT:
            running = False
    
    pygame.display.update()

pygame.quit()
```
<details>
<summary>Hint</summary>
How do you properly get all events in pygame?
</details>

---

### 9. Tkinter Button Command
```python
import tkinter as tk

def say_hello():
    print("Hello!")

root = tk.Tk()
button = tk.Button(root, text="Click Me", command=say_hello())
button.pack()
root.mainloop()
```
<details>
<summary>Hint</summary>
Check how the function is passed to the button's command parameter.
</details>

---

### 10. List Manipulation
```python
def remove_first(my_list):
    my_list = my_list[1:]
    return my_list

original = [1, 2, 3, 4, 5]
remove_first(original)
print(original)  # Expected: [2, 3, 4, 5]
```
<details>
<summary>Hint</summary>
Think about how lists are passed to functions and how to properly modify them.
</details>
