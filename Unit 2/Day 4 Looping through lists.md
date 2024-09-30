## Today is an exciting day! You get to learn about looping through lists!! This will entail combining what you have learned about lists with what you now know about loops!

### Here are some examples of the code that you hopefully created for the warm-up: 
* for loop:
```
tasks = ["Buy groceries", "Clean the house", "Do laundry", "Finish homework"]

for i in range(len(tasks)):
    print(tasks[i])
```
* while loop:
```
tasks = ["Buy groceries", "Clean the house", "Do laundry", "Finish homework"]
index = 0

while index < len(tasks):
    print(tasks[index])
    index += 1
```
### Using Indices with a For Loop
#### If you need to access both the index and the item while looping through a list, you can use the enumerate() function. Remember that the "index" is essentially just the location of the value in the loop. Also remember that the first element of a list is index 0!!

#### Here is an example of using enumerate. Try running it, and see what you get! 
```
tasks = ["Buy groceries", "Clean the house", "Do laundry", "Finish homework"]

for index, task in enumerate(tasks):
    print(f"{index + 1}. {task}")
```
#### Ahhh, a nice and organized output... But why the f?

#_______________________________________________________________________________________________________________________________________
### Hmm... Let's pause here. Notice the "f" in that print statement? This is used to create something called an f-string, which is very powerful for printing. f-string is short for "formatted string literal." Let's take some time to play around with f-strings and begin to understand their use and syntax. 

##### Please try out these examples on your own. Mess around with them a bit to see how they work.
##### This is adding two numbers. Notice how x and y can be added together and converted to a string within the print statement.
```
x = 5
y = 7
print(f"The sum of {x} and {y} is {x + y}.")
```


##### This is rounding the value of pi to 2 decimals. 
```
pi = 3.14159265359
print(f"The value of π (pi) is approximately {pi:.2f}.")
```
##### This is only printing the first 5 characters of the strings "Hello, World!"
```
text = "Hello, World!"
print(f"First 5 characters: '{text[:5]}'")
```
##### PAUSE HERE!!______________PAUSE HERE!!______________PAUSE HERE!!______________PAUSE HERE!!______________
* Can you use the code above as starting point to recreate the following? *You may want to use a forloop...*
```
#
##
###
####
#####
######
#######
########
```
Please show me your completed triangle before you move on to the next section.


##### This is letting the user know if it sunny or cloudy and if the weather is warm or cold. Notice how different the syntax is from examples we have seen!
```
temperature = 22
weather = "sunny" if temperature > 20 else "cloudy"
print(f"Today's weather is {weather}. It's {'warm' if temperature > 20 else 'cool'}.")
```
##### This will print todays date using the datetime library. 
```
from datetime import datetime
today = datetime.now()
print(f"Today's date: {today:%Y-%m-%d}")
```
#### Please note: , the percent signs within the f-string are used to indicate formatting directives. They are not part of the f-string syntax but rather part of the formatting syntax specific to the datetime module. In this case, the percent signs are used to specify how the today variable, which is a datetime object, should be formatted as a string.

### Okay, enough about f-string! Let's get back to enumerate, loops, and lists. You challenge for today is to create an interactive to-do list. 
### Key Features:
* View Tasks: Prints out all the tasks in the list.
* Add Task: Appends a new task to the list.
* Remove Task: Removes a task based on its number in the list.
* Quit: Exits the app.
  
## Extra Challenge ideas:
* Add an option to edit a task.
* Implement task priority by allowing users to assign a priority level (e.g., High, Medium, Low) to each task.






