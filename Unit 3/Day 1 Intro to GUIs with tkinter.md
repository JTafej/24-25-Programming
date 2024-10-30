
### Warm up: 


### Today we are going to learn to create a basic GUI or graphical user interface in Tkinter. 
#### To begin, we will set up a window. Try this out and you should see a blank window. 
```
import tkinter as tk

root = tk.Tk()

#Set the size and title of the window.
root.geometry("400x400")
root.title("My First GUI")

#This loops the program so it runs and thus can respond to events. (And thus accept new text from the user)
#You'll need to add code before this if you want it to be in the window. 
root.mainloop()
```
### Now lets add some text! Insert the following code after "root.title("My First GUI")" but before the main loop code. 
```
#Create a widget that displays the text "Hello World!"
label = tk.Label(root, text="Hello World!", font=('Arial', 18))
#Add padding, aka extra space around the text. 
label.pack(padx=20, pady=20)
```
### Great! Now we have a some text. We can't interact with this. Lets try adding a text box that we can type in. Add this below the text you just added, but still before root.mainloop(). In fact, all of the code you add today should be before root.mainloop()

```
#Creates a text box that can be written in. 
textbox = tk.Text(root, height = 4, font=('Arial', 16))
textbox.pack()
```
### The "pack()" function essentially throws the widget you created into the GUI. There are more intentional methods for placing widgets, as you will see in a moment. 

### The next item here is a text entry, different than a text box. It could be used to store something like a username or password, but doesn't have functionality at the moment. 
```
#We can also add a box that is specific for an entry (Something like a password or username input)
my_entry = tk.Entry(root)
my_entry.pack()
```
### We can also add buttons! Again, you will see "pack()" is used to place the button. 
```
#This will add a button. At the moment, it does not have any functionality. 
button = tk.Button(root, text = "Click Me!", font=('Arial', 18))
button.pack()
```

### Now, lets add a bunch of buttons using a grid to place them. You'll notice one of the buttons is blue. Can you see why? Also notice they are labeled 1, 2, and 3. 
```
buttonframe = tk.Frame(root)
buttonframe.columnconfigure(0, weight = 1)
buttonframe.columnconfigure(1, weight = 1)
buttonframe.columnconfigure(2, weight = 1)

btn1 = tk.Button(buttonframe, text = "1", font=('Arial', 18))

btn1.grid(row = 0, column = 0, sticky=tk.W+tk.E)
btn2 = tk.Button(buttonframe, text = "2", font=('Arial', 18))

btn2.grid(row = 0, column = 1, sticky=tk.W+tk.E)
btn3 = tk.Button(buttonframe, text = "3", bg = "blue", font=('Arial', 18))

btn3.grid(row = 0, column = 2, sticky=tk.W+tk.E)
buttonframe.pack(fill ='x')
```
### Finally, we can also place buttons wherever we'd like! This is done using "place( xloc, yloc, height, width)" instead of "pack()"

```
#This allows you to place a button wherever you like. 
anotherbtn = tk.Button(root, text = "TEST")
anotherbtn.place(x = 200, y = 300, height = 100, width = 100)
```

## Now for your challenge! None of these buttons have functionality, but your task today is to create the visual of a calculator. It can be a basic, 4 function calculator. It will take some adjusting, but you should have all the code you need to create this. Use colors to make it more interesting. Make it your own! For example, I'd call mine "Jacob's Calculator." 

<img width="137" alt="image" src="https://github.com/JTafej/Programming-Lessons/assets/143742710/674d30e0-6852-4309-a13e-647f77cb05d6">
