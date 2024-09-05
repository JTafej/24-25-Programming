## September 5th, 2024! If, Else, and Elif are called conditionals. The program will run differently based on which condition the user selects. 

### I'll start today with some different examples of conditionals. Please run each example in your program for today. Note the use of # to add comments to the program. This is a very valueable tool, and you will be expected to add comments to your projects moving forward. 

```
#Given a variable with a pre-assigned value, we can check to see if the condition is true or not.
#Experiment by plugging in integers other than 18 for age. 
age = 18
if age >= 18:
    print("You are an adult.")
```
### Now including an else statement:
```
# adding in else to handle other situations. 
age = 16
if age >= 18:
    print("You are an adult.")
else:
    print("You are a minor.")
```
### INTRODUCING elif. Elif is used when you are dealing with more than two conditions. Again, mess around with the code to see how it works. Notice how ages greater than 18 don't print adult and teenager. What do you think happens after the first if statement in that situation? 

```
age = 12
if age >= 18:
    print("You are an adult.")
elif age >= 13:
    print("You are a teenager.")
else:
    print("You are a child.")
```
### What if you want to check if more than one condition is true? No problem! You just need to include "and" or "or" depending on what you're checking. 

```
temp = 25
if temp > 30:
    print("It's hot outside.")
elif temp > 20 and temp <= 30:
    print("It's a nice day.")
else:
    print("It's cold outside.")
```
### Small challenge: Change the problem above so that it asks the user for what temperature it is outside. You'll need to specify that you want an integer. Use this as a template:
```
number = int(input("give me a number!))
```






### Example of nested conditionals (nested if): 
```
x = 41

if x > 10:
  print("Above ten,")
  if x > 20:
    print("and also above 20!")
  else:
    print("but not above 20.")
```




Your challenge for the day is to create an adventure game with if -elif - else statements. It should ask a question such as "do you want the story to take place at the beach or in the mountains?" and then have the user input which path they want to take. The program should ask some questions throughout the story to make things interesting. You'll need to understand nested if statements for this to work well. Be careful with indenting! 




