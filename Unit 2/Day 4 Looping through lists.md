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

#### Here is an example of using enumerate. Try running it, and see what you get! Ahhh, a nice and organized output...
```
tasks = ["Buy groceries", "Clean the house", "Do laundry", "Finish homework"]

for index, task in enumerate(tasks):
    print(f"{index + 1}. {task}")
```










