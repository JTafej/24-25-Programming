## Hello! Today we are going to do another coding Relay! 
#### First things first, you need a team name.
> You will start today with a paper and pencil. Once your group has code that you all agree should work, you can show me. Then, you'll start working on your program in a Sandbox on CodeHS. 
### Your Relay challenge is as follows: 
#### Create a Guess-the-number Game using a while True loop. It should include the following elements: 
* First print something like "Can you guess the number? Your odds are one in a million!"
* You should choose the magic number between 1-1,000,000
  * Basically, YOU can create a variable for the magic number. (Alternatively, you can use the Random library to generate one.)
* The program should include a while True loop
* If the guess is too high, say "Too high!" If the guess is too low, say "too low!"
  * You will need to use IF statements here in order to compare the users input to the magic number. 
* The program should continue to ask the user to a guess until they get it correct.
  * After the guess correctly, the loop should end! How do you do this? 
* Lastly, include a counter that will tell the user how many tries it took them to guess. 

## 
## 

### Now, for something new. We are going to learn a different type of loop! (This is to be completed in the "For Loops Intro" Replit.)
#### "For Loops" Provide a way to run a loop an exact number of times. While loops would run until we met a certain condition. For loops are used when we know exactly how many times we want them to be run. 

#### For example, take this while loops we saw last week: 
```
counter = 0
while counter < 10:
  print(counter)
  counter += 1
```
### We can instead right this as a for loop, because we know we want to count up to 10.
#### Please note the use of the function range(). Range(10) will print [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]. It indexes from 0 and will go up to one less than the number displayed. 
```
for i in range(10):
  print(i)

```
#### You can also choose a specific start point for range(). 
```
for i in range(1,10):
  print(i)

```
#### You can *also* pick the value you want range() to increment by. 
```
for i in range(1, 10, 2):
  print(i)

```
#### Notice that you can use continue in a similar way while True loops. Break would work here as well. 

```
for x in range(6):
  if x == 3: continue
  print(x)
else:
  print("Finally finished!")
```

#### notice the new term "range." range counts from 0-9, and in this case will print numbers 0-1. Range is a function, like exit, so we must include paranthesis after. example: range(4)
#### In the loop above "counter" is the variable. "i", "j", and "k" are commonly used by programmers as variables in for loops. 

## Your Challenge for today is to create a short game that include both a while loop and a for loop. Think about asking the character how many times they want to do something (i.e. they get to decide the range?) Show me your idea before you get started on this challenge today.
