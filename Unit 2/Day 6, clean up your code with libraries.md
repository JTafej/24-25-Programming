## Today we are going to talk about Libaries. 

### In Python, libraries are collections of pre-written code (modules) that provide additional functionality for your programs. Libraries allow you to access functions, classes, and variables that someone else has already created, saving you time and effort so you don't have to reinvent the wheel.

### Why Use Libraries?
* Efficiency: You can accomplish tasks faster by using libraries instead of writing everything from scratch.
* Complex tasks: Libraries often provide powerful tools for handling complex tasks like working with data, creating graphics, or accessing web APIs.
* Reusability: Libraries are reusable across multiple projects.
### Built-in Libraries
#### Python comes with a lot of built-in libraries that are ready to use. For example:
* math: Provides mathematical functions like sqrt() (square root) and sin() (sine).
* random: Used for generating random numbers, selecting random items from lists, and more.
* datetime: Used for working with dates and times.
  
### There currently around 137,000 python libriaries. Holy Cow! Here is a link to the 10 most popular libraries. Take a minute to read through each one and learn what they are used for. 
#### https://www.geeksforgeeks.org/libraries-in-python/

### For example, PyTorch is used for Machine learning and Neural Networks. 
* "PyTorch is the largest machine learning library that optimizes tensor computations. It has rich APIs to perform tensor computations with strong GPU acceleration. It also helps to solve application issues related to neural networks."
* What Library could I use for plotting numberical data?
#
#
### How do you use a library? It's not too complicated! You just have to "import" the library, and then call the function or module you want to use from the library. For example:
#### This program will use the function randint from random to select a random integer between 1 and 100!
```
import random
myNumber = random.randint(1,100)
print(myNumber)
```
#### Try this one (There are a couple of errors you'll need to fix first.) Make sure to comment this in your program. Call me over when you are done so I check you off. 
```
import random
for i in range(10):
  myNumber = randint(1, 100)
  print(Number)
```

### Okay, that's pretty cool. But we can do much more with Libraries!
#### For example, we can use the os library to talk directly to the console! 

```
import os
for i in range(1,1000):
  print(i)
```
### Hmm... Okay, not much going on here yet. We imported os, but we actually have to use it! Check it out:
```
import os
for i in range(1,1000):
  print(i)
  os.system("clear")
```
### We can also use the time library to slow down the loop. Check it out. time.sleep(TIME INTERVAL IN SECONDS) will pause the loop after the print statement before moving it onto the next piece. 
```
import os, time
for i in range(1,1000):
  print(i)
  time.sleep(0.1)
  os.system("clear")
 ```
### Amazing! This is a very powerful tool, as it can clear our results and make the program a lot more pleasant for the user. 

#### What is the problem below?
```
import os
adding = 4 + 3
print(adding)
os.system("clear")

subtraction = 8 - 9
print(subtraction)
os.system("clear")

multiplication = 4 * 32
print(multiplication)
os.system("clear")

division = 50 / 5
print(division)
os.system("clear")

squared = 5**2
print(squared)
os.system("clear")
```
### Well, the program is doing the calculations, but they are getting deleted instantly! If we use the time library, we can see the answers just for a minute!
```
import os, time
adding = 4 + 3
print(adding)
time.sleep(1)
os.system("clear")

subtraction = 8 - 9
print(subtraction)
time.sleep(1)
os.system("clear")

multiplication = 4 * 32
print(multiplication)
time.sleep(1)
os.system("clear")

division = 50 / 5
print(division)
time.sleep(1)
os.system("clear")

squared = 5**2
print(squared)
time.sleep(1)
os.system("clear")
```
### Where might the time and os libraries be usesful to you? think about your programs from the past. Can you use time and os to clean them up a bit? That is your challenge for the day. Please complete your challenge in the new sandbox for the day. If you get finished early, read some more about libraries on the link I attached! 
