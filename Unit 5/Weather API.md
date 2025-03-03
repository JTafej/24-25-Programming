### After spending some time researching what an API is, we will start exploring an API of our own! 
### The task for this week is to take some starter code shown below, and create a nice little weather app using tkinter. Your app should include little pictures of clouds for cloudy days, sun for sunny days, and display the weather in a nice font. Feel free to add more fun stuff if you'd like. 

#### The API key for this website was generated for my account on Openweathermap.org where you can create an account of your own (Or just use the code below with my key for now if you prefer). The API is how the python code "talks to" the website to gather data. This code is setup to simply take weather and temperature from the webiste, but you can get a lot more information from it if you would like. There will be code at the bottom that you can add if you want to gather more data to work with. 

#### In the following code, requests.get() returns a json file from openweathermap.org. This file gives you an array of weather information. (Arrays are like a combination of lists and dictionaries.) The if statement checks to see if there is an error in retrieving city informtion (No info found error = 404). 

#### The variables weather and temp defined after temp are the elements of the array that contain weather information and temperature. print(weather_data.json()) returns all of the weather data. You can see where the weather and temp are stored, and how the program calls them. You should be able to use your knowledge of Tkinter to create a GUI for this weather app now that you have variables defined. HAVE FUN!

```
import requests
api_key='dbe6b75fc7215163bdad6b7090c38e75'
user_input = input("Enter city: ")

weather_data = requests.get(
    f"https://api.openweathermap.org/data/2.5/weather?q={user_input}&units=imperial&APPID={api_key}")

if weather_data.json()['cod'] == '404':
    print("No City Found")
else:
    print(weather_data.json())
    weather = weather_data.json()['weather'][0]['main']
    temp = round(weather_data.json()['main']['temp'])

    print(f"The weather in {user_input} is: {weather}")
    print(f"The temperature in {user_input} is: {temp}ºF")
```

#### As a reminder for basic tkinter code, here is the starter file from previous units: 
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
