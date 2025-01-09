## Intro to Classes!
#### Today you will be introduced to the idea of a Class in python. This is a fundamental part of Object-Oriented-Programming. Read more about Object Oriented Programming here: https://www.geeksforgeeks.org/introduction-of-object-oriented-programming/ Note: This is a powerful topic, and gets complicated quickly. We will start with some basics today. 

### Shown below is a basic class called "Dog" with attributes name and age. The class also contains two functions (called methods, because they are within the class) that have the dog roll over and sit. This is all our class can do for now. 
```
class Dog:
#A simple attempt to model a dog.
  def __init__(self, name, age):
  #Initialize name and age attributes.
    self.name = name
    self.age = age

  def sit(self):
  #Simulate a dog sitting in repsonse to a command.
    print(f"{self.name} is now sitting.")

  def roll_over(self):
  #Simulate a dog rolling over in response to a command.
    print(f"{self.name} rolled over!")

```
### When you run this code, you will notice that there is no output. Well, all we have done is told the program ABOUT the class Dog. We still need to create an INSTANCE of the dog. (Think a red robot, or a blue robot, rather than just "a robot".) To do this, we type the following code: 

```
jacob_dog = Dog('Indy', 3)
```
### If you add this to the program, it will create an instance(AKA an OBJECT) of a dog, whose name is Indy, and whose age is 3. To check this, we can add the following lines: 
```
print(f"Jacob's dog's name is {jacob_dog.name}.")
print(f"Jacob's dog is {jacob_dog.age} years old.")
```

### What if we want to have the dog sit or roll over? (AKA we want to call a METHOD from the Class dog) We use the following code. Add this to your file to test it. 
```
# To have the dog sit
jacob_dog.sit()
# To have the dog roll over
jacob_dog.roll_over()
```
### Try creating a new instance(OBJECT) for your own dog. Call it my_dog. If you do not have a dog, make up a name and age of a dog! After you have created the new instance, try running the following code:
```
print(f"Jacob's dog's name is {jacob_dog.name}.")
print(f"Jacob's dog is {jacob_dog.age} years old.")

print(f"My dog's name is {my_dog.name}.")
print(f"My dog is {my_dog.age} years old.")
```

### Hopefully you are starting to notice the power of classes. We can create as many instances (Or different dogs/objects) as we want!!!

### Your challenge. Use the class Dog in a program that prints the dogs name and age, and then asks the user if the dog should sit or roll over. If the user types something else, the program should say "(dogs name) doesn't know that trick!"



### Your bonus challenge is to create a new class called Doggy_dice in which:
* the dog has similar attributes to those in class Dog 
* but it can also roll a 6 sided die if you ask it to. (You may need to look at previous code to remember how to create a 6 sided die.)
