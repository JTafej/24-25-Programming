### You're in for a treat! Today we are talking about While loops. We will learn about other loops later, but you will soon discover that loops are a very powerful tool in programming. 

#### So what is a while loop? It is a way to run a program over and over again until a certain condition is met. 
<img src="https://github.com/JTafej/Programming-Lessons/assets/143742710/8bbc0c45-425e-456c-a244-2392c8ae7ef3" width="300" height="300">

#### For example, try running the following code that was demonstrated by our brave volunteer. 

```
counter = 0
while counter < 10:
  print(counter)
  counter +=1
```
#### You will see that the code will run until counter = 10. Amazing. Can you make the program count to 100 instead? 

##### Try running this code. What happens? 
```
exit = input("Exit?: ")
while exit == "no":
  
  print(":)")
exit = input("Do you wanna exit now?: ")

```

##### Ah! The "Exit" question was not IN the while loop in that code. See the code below for the correct format for a while loop. 
```
exit = input("Exit?: ")
while exit == "no":
  
  print(":)")
  exit = input("Do you wanna exit now?: ")

```

##### One of the most powerful ways to use a while use is with a boolean (True in this case). This will run until you tell the while loop to "break," which will end the while loop. Try running this program and notice the use of "counter." You will need to use a counter for your challenge today. 
```
print("can you guess the lyrics??\n Guess the lyrics. If you get them right, you can be cool\n")
counter = 0
while True:

  guess = input("Never going to ____ you up \n Guess:")
  
 
  counter += 1
  if guess == "give":
    break
  print("Try again!")
print("Nice! You got it on attempt number", counter)

```

#### The challenge for today is to create a program that asks the user for an animal, and then says the sound that animal makes. For example: "what animal do you like?" if input = cow, output is "Cows go mooooo" Please use a while loop so you can ask a user if they want to keep playing the game. If they say no, make sure you stop the game. 
*Add a counter to your program, and tell you user how many rounds they played after they exit.*
