# Python Debugging Challenge - Round 2
## Find and fix the error in each code snippet!

---

### 1. String Slicing
```python
message = "Hello, World!"
print(message[7:0])
```
<details>
<summary>Hint</summary>
Check the start and end indices in the string slice.
</details>

---

### 2. Function Return Value
```python
def multiply(a, b):
    result = a * b
    
x = 5
y = 3
print(multiply(x, y))
```
<details>
<summary>Hint</summary>
What's missing from the function?
</details>

---

### 3. List Append
```python
numbers = [1, 2, 3]
numbers.append(4, 5, 6)
print(numbers)
```
<details>
<summary>Hint</summary>
Check how the append method works with lists.
</details>

---

### 4. List Comprehension with Conditional
```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
even_numbers = [x if x % 2 == 0 for x in numbers]
print(even_numbers)
```
<details>
<summary>Hint</summary>
Check the syntax for conditional list comprehensions.
</details>

---

### 5. If-Else Condition
```python
x = 10
if x > 5
    print("x is greater than 5")
else:
    print("x is not greater than 5")
```
<details>
<summary>Hint</summary>
Check the syntax of the if statement.
</details>

---

### 6. List Iteration
```python
fruits = ["apple", "banana", "cherry"]
for fruit in range(fruits):
    print(fruit)
```
<details>
<summary>Hint</summary>
How do you iterate through items in a list?
</details>

---

### 7. Pygame Surface
```python
import pygame
pygame.init()
screen = pygame.display.set_mode((800, 600))
pygame.draw.circle(800, 600, 50, (255, 0, 0))
pygame.display.update()
```
<details>
<summary>Hint</summary>
Check the parameters for pygame.draw.circle().
</details>

---

### 8. Tkinter Label
```python
import tkinter as tk
root = tk.Tk()
label = tk.Label(text="Hello World")
label.pack()
root.mainloop()
```
<details>
<summary>Hint</summary>
What's missing from the Label constructor?
</details>

---

### 9. Arithmetic Operation
```python
result = 10 / 0
print(result)
```
<details>
<summary>Hint</summary>
Is this operation mathematically valid?
</details>

---

### 10. Class Method Call
```python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def calculate_area():
        return self.width * self.height

rect = Rectangle(5, 10)
area = rect.calculate_area()
print(area)
```
<details>
<summary>Hint</summary>
Check the parameters in the class method definition.
</details>

---
## Simulated Weather App. Below is the code from the paper that you explored at the start of class today. Give it a try and see if it's what you expected!

```
import tkinter as tk
from tkinter import ttk
import random
import math
from datetime import datetime, timedelta

# Simulated weather data - in a real app, this would come from an API
CITIES = {
    "New York": {"latitude": 40.7128, "longitude": -74.0060, "climate": "temperate"},
    "Los Angeles": {"latitude": 34.0522, "longitude": -118.2437, "climate": "mediterranean"},
    "Chicago": {"latitude": 41.8781, "longitude": -87.6298, "climate": "continental"},
    "Miami": {"latitude": 25.7617, "longitude": -80.1918, "climate": "tropical"},
    "Seattle": {"latitude": 47.6062, "longitude": -122.3321, "climate": "oceanic"},
    "Denver": {"latitude": 39.7392, "longitude": -104.9903, "climate": "semi-arid"},
}

class WeatherGenerator:
    """Class to generate simulated weather data"""
    
    def __init__(self, city_data):
        self.city_data = city_data
        self.seed = random.randint(1, 1000)  # Random seed for consistent weather patterns
        
    def get_temperature(self, city, day_offset=0):
        """Generate a realistic temperature for the given city and day offset"""
        climate = self.city_data[city]["climate"]
        latitude = self.city_data[city]["latitude"]
        base_temps = {
            "tropical": 30,
            "mediterranean": 22,
            "temperate": 15,
            "continental": 10,
            "oceanic": 12,
            "semi-arid": 18
        }
        
        # Base temperature for climate
        base_temp = base_temps.get(climate, 15)
        
        # Adjust for latitude (colder toward poles)
        latitude_factor = abs(latitude) / 90
        temp = base_temp - (latitude_factor * 20)
        
        # Add a sine wave for seasonal variation (simplified)
        day_of_year = (datetime.now() + timedelta(days=day_offset)).timetuple().tm_yday
        seasonal_variation = 10 * math.sin((day_of_year / 365) * 2 * math.pi)
        
        # Add random daily variation
        random.seed(self.seed + day_offset)
        daily_variation = random.uniform(-5, 5)
        
        return round(temp + seasonal_variation + daily_variation, 1)
    
    def get_conditions(self, city, day_offset=0):
        """Generate weather conditions based on climate and random factors"""
        climate = self.city_data[city]["climate"]
        random.seed(self.seed + day_offset)
        
        # Probability distributions for different climates
        condition_probabilities = {
            "tropical": {"sunny": 0.5, "partly cloudy": 0.2, "rainy": 0.25, "stormy": 0.05},
            "mediterranean": {"sunny": 0.7, "partly cloudy": 0.2, "rainy": 0.1},
            "temperate": {"sunny": 0.4, "partly cloudy": 0.3, "rainy": 0.2, "cloudy": 0.1},
            "continental": {"sunny": 0.3, "partly cloudy": 0.3, "rainy": 0.2, "cloudy": 0.1, "snowy": 0.1},
            "oceanic": {"sunny": 0.2, "partly cloudy": 0.3, "rainy": 0.4, "cloudy": 0.1},
            "semi-arid": {"sunny": 0.8, "partly cloudy": 0.15, "rainy": 0.05}
        }
        
        # Default to temperate if climate not found
        probabilities = condition_probabilities.get(climate, condition_probabilities["temperate"])
        
        # Generate a random condition based on probabilities
        rand = random.random()
        cumulative_prob = 0
        for condition, prob in probabilities.items():
            cumulative_prob += prob
            if rand <= cumulative_prob:
                return condition
        
        return "sunny"  # Default fallback
    
    def get_humidity(self, city, day_offset=0):
        """Generate humidity percentage based on climate and conditions"""
        climate = self.city_data[city]["climate"]
        conditions = self.get_conditions(city, day_offset)
        
        # Base humidity by climate
        base_humidity = {
            "tropical": 80,
            "mediterranean": 60,
            "temperate": 50,
            "continental": 40,
            "oceanic": 70,
            "semi-arid": 20
        }.get(climate, 50)
        
        # Adjust for weather conditions
        condition_factor = {
            "sunny": -10,
            "partly cloudy": 0,
            "cloudy": 10,
            "rainy": 30,
            "stormy": 40,
            "snowy": 20
        }.get(conditions, 0)
        
        # Add random variation
        random.seed(self.seed + day_offset + 100)  # Different seed than temperature
        random_factor = random.uniform(-10, 10)
        
        # Ensure humidity is between 0-100%
        humidity = base_humidity + condition_factor + random_factor
        return max(0, min(100, round(humidity)))
    
    def get_wind_speed(self, city, day_offset=0):
        """Generate wind speed in km/h"""
        random.seed(self.seed + day_offset + 200)  # Different seed than temp and humidity
        return round(random.uniform(0, 30), 1)
    
    def get_forecast(self, city, days=5):
        """Generate a weather forecast for the specified number of days"""
        forecast = []
        for day in range(days):
            forecast.append({
                "day": (datetime.now() + timedelta(days=day)).strftime("%a"),
                "date": (datetime.now() + timedelta(days=day)).strftime("%b %d"),
                "temperature": self.get_temperature(city, day),
                "conditions": self.get_conditions(city, day),
                "humidity": self.get_humidity(city, day),
                "wind_speed": self.get_wind_speed(city, day)
            })
        return forecast


class WeatherDashboard:
    """Main weather dashboard application"""
    
    def __init__(self, root):
        self.root = root
        self.root.title("Weather Dashboard")
        self.root.geometry("800x600")
        self.root.configure(bg="#f0f0f0")
        
        self.weather_gen = WeatherGenerator(CITIES)
        self.current_city = "New York"  # Default city
        
        self.setup_ui()
        self.update_weather_display()
    
    def setup_ui(self):
        """Set up the user interface"""
        # Header frame
        header_frame = tk.Frame(self.root, bg="#3498db", padx=10, pady=10)
        header_frame.pack(fill=tk.X)
        
        tk.Label(header_frame, text="Weather Dashboard", font=("Arial", 24, "bold"), 
                 bg="#3498db", fg="white").pack(side=tk.LEFT)
        
        # City selection
        city_frame = tk.Frame(self.root, bg="#f0f0f0", padx=10, pady=10)
        city_frame.pack(fill=tk.X)
        
        tk.Label(city_frame, text="Select City:", font=("Arial", 12), 
                 bg="#f0f0f0").pack(side=tk.LEFT, padx=(0, 10))
        
        self.city_var = tk.StringVar(value=self.current_city)
        city_dropdown = ttk.Combobox(city_frame, textvariable=self.city_var, 
                                    values=list(CITIES.keys()), state="readonly", width=15)
        city_dropdown.pack(side=tk.LEFT)
        city_dropdown.bind("<<ComboboxSelected>>", self.on_city_changed)
        
        # Current weather frame
        self.current_weather_frame = tk.Frame(self.root, bg="white", padx=20, pady=20, 
                                             relief=tk.RIDGE, borderwidth=1)
        self.current_weather_frame.pack(fill=tk.X, padx=10, pady=10)
        
        # Forecast frame
        forecast_label = tk.Label(self.root, text="5-Day Forecast", font=("Arial", 16, "bold"), 
                                 bg="#f0f0f0")
        forecast_label.pack(anchor=tk.W, padx=10, pady=(10, 0))
        
        self.forecast_frame = tk.Frame(self.root, bg="#f0f0f0")
        self.forecast_frame.pack(fill=tk.X, padx=10, pady=10)
    
    def on_city_changed(self, event):
        """Handle city selection change"""
        self.current_city = self.city_var.get()
        self.update_weather_display()
    
    def update_weather_display(self):
        """Update all weather information displays"""
        # Clear current weather frame
        for widget in self.current_weather_frame.winfo_children():
            widget.destroy()
        
        # Clear forecast frame
        for widget in self.forecast_frame.winfo_children():
            widget.destroy()
        
        # Get weather data
        forecast = self.weather_gen.get_forecast(self.current_city, 5)
        current = forecast[0]  # Today's forecast
        
        # Update current weather
        city_label = tk.Label(self.current_weather_frame, text=self.current_city, 
                             font=("Arial", 22, "bold"), bg="white")
        city_label.grid(row=0, column=0, sticky=tk.W)
        
        date_label = tk.Label(self.current_weather_frame, 
                             text=f"Today, {current['date']}", 
                             font=("Arial", 12), bg="white")
        date_label.grid(row=1, column=0, sticky=tk.W)
        
        # Weather icon (simplified with text)
        condition_label = tk.Label(self.current_weather_frame, 
                                  text=current['conditions'].title(), 
                                  font=("Arial", 16), bg="white")
        condition_label.grid(row=2, column=0, sticky=tk.W, pady=(10, 0))
        
        temp_label = tk.Label(self.current_weather_frame, 
                             text=f"{current['temperature']}°C", 
                             font=("Arial", 40), bg="white")
        temp_label.grid(row=0, column=1, rowspan=2, padx=30)
        
        # Additional weather info
        details_frame = tk.Frame(self.current_weather_frame, bg="white")
        details_frame.grid(row=3, column=0, columnspan=2, sticky=tk.W, pady=(20, 0))
        
        humidity_label = tk.Label(details_frame, 
                                 text=f"Humidity: {current['humidity']}%", 
                                 font=("Arial", 12), bg="white")
        humidity_label.grid(row=0, column=0, sticky=tk.W, padx=(0, 20))
        
        wind_label = tk.Label(details_frame, 
                             text=f"Wind: {current['wind_speed']} km/h", 
                             font=("Arial", 12), bg="white")
        wind_label.grid(row=0, column=1, sticky=tk.W)
        
        # Display 5-day forecast
        for i, day in enumerate(forecast):
            day_frame = tk.Frame(self.forecast_frame, bg="white", padx=10, pady=10, 
                                relief=tk.RIDGE, borderwidth=1, width=150)
            day_frame.grid(row=0, column=i, padx=5)
            day_frame.grid_propagate(False)  # Maintain fixed width
            
            day_label = tk.Label(day_frame, text=day['day'], 
                                font=("Arial", 12, "bold"), bg="white")
            day_label.pack(pady=(0, 5))
            
            date_label = tk.Label(day_frame, text=day['date'], 
                                 font=("Arial", 10), bg="white")
            date_label.pack()
            
            condition_label = tk.Label(day_frame, text=day['conditions'].title(), 
                                      font=("Arial", 10), bg="white")
            condition_label.pack(pady=(10, 5))
            
            temp_label = tk.Label(day_frame, text=f"{day['temperature']}°C", 
                                 font=("Arial", 14), bg="white")
            temp_label.pack(pady=(5, 0))


if __name__ == "__main__":
    root = tk.Tk()
    app = WeatherDashboard(root)
    root.mainloop()
```

### Posibilities for extensions!
1. Add graphical icons for different weather conditions
2. Implement a temperature graph showing the 5-day trend
3. Add a "Feels Like" temperature calculation
4. Create a precipitation probability calculation
5. Add day/night temperature variations
6. Implement a UV index calculation based on latitude and conditions
7. Add more cities to the database
8. Create a map visualization showing the selected city
9. Add a unit conversion toggle (Celsius/Fahrenheit)
10. Implement a "favorite cities" feature
