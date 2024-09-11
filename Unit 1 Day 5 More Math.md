### First thing today we are going to run through this code and decide what the program is doing. Afterwards, you will alter the code.

```
print("POSITIVITY MACHINE!!😁", "\n",
      "++++++++++++++++++++++++++","\n")
name = input("Glad you're using this machine. So, what's your name?")
if name == "Jacob" or name == "jacob":
  print("Hey Jacob. What are you hoping to get done with your life today? Think small. Just today.")
  task = input("List one simple task here.")
  rating = input("Great. I beleive in you! Maybe you could tell me more about how your day has been so far. Give me 1-5 rating!")

  if rating == "1":
    print("ahh dang. Well, despite that, I am sure you will be able to" , task, " \n I bet your day will improve, whether or not you complete that task")
  elif rating == "2":
    print("Okay! Better than a 1 right?? I am sure you will be able to" , task,  "\n And I bet your day will improve :)")
  else:
    print("😁Booya! That's not bad! I am sure you will complete", task, "and then your day will be even better!")

else :
  print("Ah, I don't know you", name, "so I don't think I can help you any further. \n However, I hope you have an amazing day :)")
```
#### Last class we talked about integers and floats. Remind your neighbor why it is sometimes useful to use numbers in your code. 

<details>
<summary>Reminder </summary>
<br>
  Numbers can be useful when we want to compare values. For instance, if I want to find out if someone scored less that 70% on the test, I would need to use an integer. Ex. (56 <= 70) 
  
</details>

##### Run the following to remind yourself how integers work in python. (Notice "int" next to input. This is telling the program that the user is entering an integer. This is called *casting.* Try plugging in a word instead and see what happens!)  

```
myScore = int(input("Your score: "))
if myScore >= 70:
  print("Nice job!")
else:
  print("Better luck next time...")
```


### Today we are going to use Float and Int again! Python is powerful, and if used correctly in can easily replace a simple calculator. 

Try running this code to see some math python can do: 
```
adding = 4 + 3
print(adding)

subtraction = 8 - 9
print(subtraction)

multiplication = 4 * 32
print(multiplication)

division = 50 / 5
print(division)

# a number raised to the power of some number
# in this example we raise 5 to the power of 2
squared = 5**2
print(squared)

# remainder of a division
modulo = 15 % 4
print(modulo)
```

### Now, comment out everything in main.py. Please fix this code so that all 3 solutions appear on the screen:
```
# multiplication
3.4 * 6.8
# division
2467 / 4673
#raise 10 to the power of 2
```
# Okay, now it's time to put some of our skills to good use. Let's say you are going to eat at Salt & Straw with some friends. Yum! ☺️
### Only problem is, you need to divide up the bill. You can use some python code that looks like this to do that. 
##### ~~ Copy this code and see what happens ~~

```
myBill = float(input("What was the bill?: "))
numberOfPeople = int(input("How many people?: "))
answer = myBill / numberOfPeople
print("You all owe", answer)
```
You might get a strange number with a bunch of decimal points. To avoid this, use this code after "answer" and before "print" 
```
answer = round(answer, 2)
```
# Challenge Time

#### You need to add a tip function that can include a tip, and then split up the bill equally between the friends. 

It should do the following: 
1. Ask the user what the total is
2. Ask what *percent* they want to tip. (Typically 15-25%)
3. Figure out how much **myBill + TIP** will be.

<details>
<summary>Hint </summary>
<br>
  Divide the tip percentage by 100, and then multiple that number by **myBill**. This will give you       the **TIP**. Then do ***myBill + TIP*** 
  
</details>

4. Ask the user how many people there are, and divide it evenly.

Use the code from before to get started. Submit a screenshot of your working code and an output to canvas. You must include comments in your program that explain what each piece is doing. 

```
# Ask user for the total cost and the number of people: 
myBill = float(input("What was the bill?: "))
numberOfPeople = int(input("How many people?: "))
#Calculate amount, and tell user. 
answer = myBill / numberOfPeople
print("You all owe", answer)
```
