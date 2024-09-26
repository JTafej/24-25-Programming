
### **Introduction to Lists in Python**

**Objective**:  
By the end of the lesson, you will be able to:
1. Understand what a list is and why it’s useful.
2. Create and manipulate lists (accessing, modifying, and appending).
3. Iterate over lists using loops.

#### **1. Warm-up**
Remind yourself about for loops and while loops by writing a short program for each. Do the same with an if statement, and a variable. Just to get your brain going. Take note of how each component works! 
  
 # Lists
 #### Imagine you have a collection of items, like a shopping list. In Python, we use *lists* to store collections of items.

#### Example : A grocery list may contain a few items, such as milk, bread, and eggs. In Python, we use square brackets to create lists. For example, to create a list called Groceryitems:
```
Groceryitems = ['milk', 'bread', 'eggs']
```
#### Try printing this list. 
#### **2. What is a List? **
  - A list is a collection of items (called elements) that can hold multiple values under a single variable name.
  - Lists can store any data type: numbers, strings, even other lists.
- **Syntax**:
  ```
  my_list = ['apple', 'banana', 'cherry']
  my_numbers = [10, 20, 30]
  ```
  Notice that each element is separated by a comma and that lists are defined using square brackets. Strings require a single or double quote while integers do not. 
- **Why use lists?**:
  - Lists allow us to work with multiple items efficiently. Instead of defining individual variables for each value, we can store everything in one list. They are incredible powerful and are used in many fields such as data science and machine learning. (Though we would be talking about GIANT lists in those cases.) 
  
- **Accessing Elements in a list**:
  - Importantly,  lists index from 0, meaning the first element in a list is at “location 0.”
  - Test it out: 
    ```
  my_list = ['apple', 'banana', 'cherry']
    print(my_list[0])  # prints 'apple'
    print(my_list[2])  # prints 'cherry'
    ```







#### **4. Modifying Lists (10 minutes)**
- Lists are *mutable*, meaning you can change elements after creating the list.
- **Modifying Elements**:
  ```  favorite_movies = ['Inception', 'The Matrix', 'Interstellar']
  print(favorite_movies[1])  # Accesses the second item
```
```
  favorite_movies[1] = 'The Lord of the Rings'
  print(favorite_movies)  # Now 'The Matrix' is replaced
  ```

- **Adding Elements**:
  Sometimes you will want to be able to add items (elements) to a list. Use `LISTNAME.append()` to add elements to the end of the list.
  ```
  favorite_movies.append('Avatar')
  print(favorite_movies)  # Adds 'Avatar' to the end
  ```

#### **3. Hands-On Practice: Creating and Accessing Lists (15 minutes)**
- **You try it out!**: Create a list of your favorite movies.
  ```
  favorite_movies = ['Inception', 'The Matrix', 'Interstellar']
  print(favorite_movies[1])  # Accesses the second item
  ```



- **Activity 2**: Print the first and last item in your list using indexing. You can use negative indexing (`-1` refers to the last item. This will be helpful if you have a giant list and you don’t necessarily know how long it is, although you can find that out as well):
  ```python
  print(favorite_movies[-1])  # prints 'Interstellar' in my example. 
  ```
#### **5. Iterating Over Lists with Loops**
- Note that loops can be used to go through each item in a list! These are very powerful tools when you combine them. 

- **For Loop with Lists**:
  ```python
  for movie in favorite_movies:
      print(movie)
  ```
  - Walk through how the loop accesses each element of the list one by one.

  - Have students create a list of numbers and use a `for` loop to print each number doubled.
    ```python
    numbers = [1, 2, 3, 4, 5]
    for number in numbers:
        print(number * 2)
    ```

- **While Loop with Lists**:
  - Introduce how a `while` loop can also be used with lists by using the length of the list.
    ```python
    i = 0
    while i < len(numbers):
        print(numbers[i])
        i += 1
    ```

---

#### **6. Additional List Functions (5-10 minutes)**
- **Introduce useful list methods**: 
  - `len()`: Returns the number of items in a list.
    ```python
    print(len(favorite_movies))  # Output: 4
    ```
  - `remove()`: Removes an element by value.
    ```python
    favorite_movies.remove('Avatar')
    ```
  - `insert()`: Inserts an element at a specified index.
    ```python
    favorite_movies.insert(1, 'The Dark Knight')
    ```

- **Hands-On Practice**:
  - Have students use `len()` and `remove()` on their own lists.


#### **7. Closing Activity and Homework**
- **Activity**: Have students create a list of random numbers using the `random` library and a `for` loop, then print only the even numbers in that list.

- **Challenge for today**:  
  Create a list of 5 items. Write a program that:
  1. Prints each item in the list.
  2. Adds a new item to the list.
  3. Removes an item from the list.
  4. Prints the entire modified list.
  5. Prints the last element of the list and says “this is the last item!” 
  6. Prints the length of the list. (You’ll need to look up how to find this. It will work for any length and you shouldn’t need to count. 
