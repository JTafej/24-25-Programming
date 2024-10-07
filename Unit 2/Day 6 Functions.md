### Hello Everyone!
#### Today, we’re going to learn about functions. Functions allow us to organize our code, make it reusable, and break down larger programs into smaller, more manageable parts. We’ll start with simple examples and build up to more complex programs. Let’s dive in!
________________________________________
### Introduction to Functions
#### You may remember learning about functions in Precalculus! f(x), g(x), and h(x) were all common names for functions. In math, functions take some input, and spit out an output. For example, for the function f(x) = 3x + 2, if you plug in 2, you get: f(2) = 3(2) + 2 = 8. Each input will have a distinct output. That's what makes it a function!  
### So What is a Function in Python?
#### A function is a block of code that runs only when it is called. You can pass data into a function (parameters are what your "inputs" are called), and the function can return data (output) as a result.
#### Simple Function Example:
#### Here’s an example of a function that greets someone by name. Notice that if you don't include the print statement at the end, the function won't print anything. Although it will still be "returning" the value "Hello, {input}"
```
# Defining a function
def greet(name):
    return f"Hello, {name}!"

# Calling the function
print(greet("Alice"))
```
### Key Concepts:
*	def: This keyword is used to define a function.
*	Parameters: Values you can pass into a function (e.g., name in the example).
*	Return Value: What the function gives back (in this case, a greeting string).
________________________________________
### Let’s create our own simple function!
#### Here is a function called double_number that takes in a number as a parameter, doubles it, and returns the result.
```
def double_number(n):
    return n * 2

# Test it out
print(double_number(5))  # This should print 10
```
#### *Task 1:* Use this starter code to write a "triple_number" function. Comment this task out in your code once you’re done.
________________________________________
### Functions with Multiple Parameters
### Functions can take more than one parameter. Let’s write a function that adds two numbers together.
Example:
```
def add_numbers(a, b):
    return a + b

print(add_numbers(3, 7))  # This should print 10
```

#### *Task 2:* Write a function called multiply_numbers that takes in two numbers as parameters and returns their product. Comment this task out in your code once you’re done!
________________________________________
### Functions in Loops
#### You can also use functions inside loops. Let’s create a function that says "Hello!" multiple times.
Example:
```
def say_hello():
    print("Hello!")

for i in range(3):
    say_hello()
```
#### *Task 3:* Modify the say_hello() function to accept a name as a parameter, and then print "Hello, [name]!" in the loop for three different names.
Comment this task out in your code once you’re done. This one may be a bit trickier! A list may be helpful, maybe not. 
________________________________________
Step 6: Using Functions to Simplify Code
Let’s revisit your random adventure generator from yesterday. You can make it cleaner by turning parts of it into functions. For example, you can create a function that returns a random character, another that returns a random setting, and so on.
Here’s an example of refactoring the adventure generator using functions:
python
Copy code
import random

characters = ["a knight", "a wizard", "a thief"]
settings = ["in a dark forest", "in a mystical cave", "in a busy village"]
actions = ["fights a dragon", "finds a treasure", "gets lost"]

def get_random_character():
    return random.choice(characters)

def get_random_setting():
    return random.choice(settings)

def get_random_action():
    return random.choice(actions)

# Generate and print a random scenario
print(f"{get_random_character()} {get_random_setting()} and {get_random_action()}.")
Task 4: Refactor your adventure generator (or to-do list app) by breaking parts of it into functions.
Comment this task out in your code once you’re done.
________________________________________
Step 7: Challenge: Create a More Complex Function
Now for a bigger challenge! Create a function that asks the user for two numbers, adds them together, multiplies them, or subtracts them (based on the user’s choice), and then returns the result.
Here’s an outline of what to do:
1.	Write a function called calculate that:
o	Takes in two numbers.
o	Asks the user if they want to add, multiply, or subtract the numbers.
o	Performs the chosen operation and returns the result.
2.	Use conditionals (if, elif, else) to perform the correct operation based on the user’s input.
Example interaction:
```
def calculate(a, b):
    operation = input("Would you like to add, subtract, or multiply? ").lower()
    if operation == "add":
        return a + b
    elif operation == "subtract":
        return a - b
    elif operation == "multiply":
        return a * b
    else:
        return "Invalid operation!"

# Test the function
result = calculate(10, 5)
print(result)
```
________________________________________
Final Notes
If you finish all tasks early, review any previous assignments or work on enhancing the adventure generator or to-do list project with more complex functions.
Good luck, and remember, functions are here to make your life easier by organizing and reusing code!

