## Happy Wednesday! Today we are going to start adding some functionality to our GUI! (Graphical User Interface)

### Recall from last class that we created a calculator with buttons that could be clicked, and values that could be "input." Recall also that the buttons did not actually do anything when clicked. 

### First, lets look at how we could have a button that responds in some way when clicked! Notice that a function "myClick" is being run each time we click the button. 
```
import tkinter as tk
root = tk.Tk()

def myClick():
  myLabel = tk.Label(root, text="Look! I clicked a button!")
  myLabel.pack()

myButton = tk.Button(root, text="Click Me!", command=myClick)
myButton.pack()

root.mainloop()
```
### Now, we want to accept an input or "entry." Notice we can add the tk.Entry method to accept an input! Try this code out. 
```
import tkinter as tk
root = tk.Tk()

e = tk.Entry(root, width=20, bg = "blue", fg = "white")
e.pack()

def myClick():
  myLabel = tk.Label(root, text="Look! I clicked a button!")
  myLabel.pack()

myButton = tk.Button(root, text="Click Me!", command=myClick)
myButton.pack()

root.mainloop()
```
### If we want the code to work with our entry, we can simply include the entry aka e.get() in myClick! Try this code. 
```
import tkinter as tk
root = tk.Tk()

e = tk.Entry(root, width=20, bg = "blue", fg = "white")
e.pack()

def myClick():
  myLabel = tk.Label(root, text=e.get())
  myLabel.pack()

myButton = tk.Button(root, text="Enter your name, then click me", command=myClick)
myButton.pack()

root.mainloop()
```
### Now we can do whatever we'd like with the inputs! For example, let's say hello if Jacob enters his name, and say "I don't know you!" if someone else tries to use the program. 
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
### Your challenge for today is to use the code above to create a short, 3 question quiz for users. If they answer correctly, tell them so. If they are wrong, let them know. You should use 3 separate entry boxes.
#### Note: There are a lot of new terms in the code above. Be sure you understanding the meaning of each. It will make things easier when we move to more complex uses of tkinter. 

