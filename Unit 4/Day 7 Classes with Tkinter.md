### Now that we have spent a few days with classes, lets try to implement them in a new way. Today we'll be combining what we learned previously with tkinter with classes. We will create a GUI that makes an attractive, user friendly pet-simulation game. 

## Here is some starter tkinter code to remind you how it works at a basic level. Reminder that the "command =myClick" section calls the function. You'll need to experiment with how to call a class method instead of a function defined outside of a class. 
```
import tkinter as tk
root = tk.Tk()

e = tk.Entry(root, width=20)
e.pack()

def myClick():
  dontknow = tk.Label(root,text ="I don't know you!")
  myLabel = tk.Label(root, text=("Hello " + e.get()))
  if e.get() == "Jacob":
    myLabel.pack()
  else:
    dontknow.pack()
  

myButton = tk.Button(root, text="Enter your name, then click me", command=myClick)
myButton.pack()

root.mainloop()
``` 


### Pet Simulation Game
## Your task is to create a Pet class with the following. Try implementing tkinter so that instead of typing “feed my pet” you can click a button that says “feed.” Also include a happiness, energy, and hunger meter to go with the “status” option. 
* Attributes: name, hunger, happiness, energy
* Methods:
* feed(): decreases hunger
* play(): increases happiness but decreases energy
* sleep(): increases energy
* status(): prints the pet's current state
## Challenge:
* Create multiple pet types by extending the Pet class (Dog, Cat, etc.), each with a unique behavior.
* Implement a basic loop to interact with the pet through user input (feed, play, sleep).
