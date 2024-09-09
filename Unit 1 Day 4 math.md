# Today we are going to use some math skills in our program. 
#### Side-note: I put some grades into Canvas. Please check when you have a free minute. 

### Program to reflect what we just did. Try running it in Replit. 
```
myScore = input("Your score: ")
if myScore == 10:
  print("Winner!")
else:
  print("Try again 😭")
```
### We need to tell the program what kind of input we want! In order to do math with an *input*, we must ask for an *integer*! 

We do this by including int() before the input statement. Try the program again. 
```
myScore = int(input("Your score: "))
if myScore == 10:
  print("Winner!")
else:
  print("Try again 😭")
```

### What if we want to include a number that isn't an integer? (ie not 1, 2, 3, 4, 5...) 
### If we want to include a decimal (called a float in python), we simply add float() instead of int()! For example: 

```
myPi = float(input("What is Pi to 2 decimal places? "))
if myPi == 3.14 :
  print("Exactly!")
else:
  print("Try again 😭")
```
### In addition to ==, we can use >= or <= to judge the size of a number. (These are essentially *greater than* and *less than* symbols.) 
### Okay, now that we've learned a bit... See if you can spot my errors and fix them! Please comment out the fixed code in replit. 

```
score = input("What was your score on the test?"))
if score >= 80
  print("Not too shabby")
elif score > "70":
  print("Acceptable.")
else:
print("Dude, you need to study more!")

```

### Group Challenge: Create a questionaire asking about the users favorite something. Respond to 3 items, but ask *multiple questions* for one of the answers. You'll need to use a NESTED if statement for this. See below for an example of a nested if statement. First group to have a working program wins. 
```
fan = input("So...you are a big rock climbing fan?")
if fan == "yes":
  print("okay cool! But let's just check that")
  style = input("What kind of climbing do you do? TR? Sport? Bouldering...?")
  if style == "Trad":
    print("Okay! A tough guy!")
    protection = input("Do you prefer nuts or cams?")
    if protection == "nuts":
        print("Okay. We're done here. You are awesome.")
    else:
        print("HA! Cams are for the weak.")
  else:
    print("Ha! Pathetic! Trad is the only way to go...")
else:
  print("Thanks for not wasting my time. Goodbye.")
  ```









## Below is a list of recent generations in the US. Your task is to create ask the user when they were born, and respond differently based on their age. Hint: you must use "elif" and "int" in your answer. 


#### Traditionalists	1925-1946
#### Baby Boomers	  1947-1964
#### Generation X	  1965-1981
#### Millenials	    1982-1995
#### Generation Z	  1996-2015
