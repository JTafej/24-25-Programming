## Hello all. We are going to continue talking about Classes today. 

### The first snippet of code for today is to remind you of what we did on Thursday. This is slightly different code, but the same basic idea of what we did last class: 
```
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def bark(self):
        print(f"{self.name} says Woof!")

# Creating instances of the Dog class
dog1 = Dog("Buddy", 3)
dog2 = Dog("Max", 5)

# Accessing attributes and calling methods
print(f"{dog1.name} is {dog1.age} years old.")
dog2.bark()

```

### The next thing I want to show you is how classes may be used in games. (The following code is from a blog post about Space Invaders. Link to the full blog is below.) 

#### Notice how this does the same thing we have done in many games, but we are now using classes to define the rectangle. 

```
import pygame
import sys

# Initialize Pygame
pygame.init()

# Define constants
WIDTH, HEIGHT = 800, 600
FPS = 60

# Colors
WHITE = (255, 255, 255)
RED = (255, 0, 0)

# Player class
class Player(pygame.sprite.Sprite):
    def __init__(self):
        super().__init__()
        self.image = pygame.Surface((50, 50))
        self.image.fill(RED)
        self.rect = self.image.get_rect()
        self.rect.center = (WIDTH // 2, HEIGHT // 2)
        self.speed = 5

    def update(self):
        keys = pygame.key.get_pressed()
        if keys[pygame.K_LEFT]:
            self.rect.x -= self.speed
        if keys[pygame.K_RIGHT]:
            self.rect.x += self.speed
        if keys[pygame.K_UP]:
            self.rect.y -= self.speed
        if keys[pygame.K_DOWN]:
            self.rect.y += self.speed

# Initialize Pygame screen
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Pygame Example")
clock = pygame.time.Clock()

# Create player
player = Player()

# Create sprite group
all_sprites = pygame.sprite.Group()
all_sprites.add(player)

# Game loop
running = True
while running:
    # Event handling
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Update
    all_sprites.update()

    # Draw / Render
    screen.fill(WHITE)
    all_sprites.draw(screen)

    # Flip the display
    pygame.display.flip()

    # Cap the frame rate
    clock.tick(FPS)

# Quit Pygame
pygame.quit()
sys.exit()

```

### The nice thing about this is I can easily add a new rectangle by creating a second instance of the class. The nice thing is, all I need to do is create another instance of the Player class! (Notice the only issue here is they both move the exact same way.) 
```
import pygame
import sys

# Initialize Pygame
pygame.init()

# Define constants
WIDTH, HEIGHT = 800, 600
FPS = 60

# Colors
WHITE = (255, 255, 255)
RED = (255, 0, 0)

# Player class
class Player(pygame.sprite.Sprite):
    def __init__(self, x, y):
        super().__init__()
        self.image = pygame.Surface((50, 50))
        self.image.fill(RED)
        self.rect = self.image.get_rect()
        self.rect.center = (x, y)
        self.speed = 5

    def update(self):
        keys = pygame.key.get_pressed()
        if keys[pygame.K_LEFT]:
            self.rect.x -= self.speed
        if keys[pygame.K_RIGHT]:
            self.rect.x += self.speed
        if keys[pygame.K_UP]:
            self.rect.y -= self.speed
        if keys[pygame.K_DOWN]:
            self.rect.y += self.speed

# Initialize Pygame screen
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Pygame Example")
clock = pygame.time.Clock()

# Create player instances
player1 = Player(WIDTH // 4, HEIGHT // 2)
player2 = Player(3 * WIDTH // 4, HEIGHT // 2)

# Create sprite group
all_sprites = pygame.sprite.Group()
all_sprites.add(player1, player2)

# Game loop
running = True
while running:
    # Event handling
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Update
    all_sprites.update()

    # Draw / Render
    screen.fill(WHITE)
    all_sprites.draw(screen)

    # Flip the display
    pygame.display.flip()

    # Cap the frame rate
    clock.tick(FPS)

# Quit Pygame
pygame.quit()
sys.exit()

```







### There will be several challenges today. Once you have completed a challenge, feel free to comment it out and move on to the next one. 

### Challenge 1: 
 * Create a class named Car with attributes such as make, model, and year. Include a method display_info that prints information about the car.
```
class Car:
    def __init__(self, make, model, year):
        # Your code here

    def display_info(self):
        # Your code here

# Create an instance of Car and test the display_info method
```
### Challenge 2:
* Extend the Dog class to include a new method birthday that increments the age of the dog by 1.

```
class Dog:
    # Existing code here

    def birthday(self):
        # Your code here

# Create a Dog instance, call birthday, and print the updated age
```
### Challenge 3:
* Create a class named Rectangle with attributes length and width. Include methods to calculate the area and perimeter of the rectangle.
```
class Rectangle:
    def __init__(self, length, width):
        # Your code here

    def calculate_area(self):
        # Your code here

    def calculate_perimeter(self):
        # Your code here

# Create an instance of Rectangle and test the methods

```

### Challenge 4: (Scroll to the bottom for a possible solution to this challenge.) 

* Create a BankAccount class with attributes account_holder and balance. Include methods to deposit and withdraw funds. Ensure that the balance cannot go below zero.

```
class BankAccount:
    def __init__(self, account_holder, balance):
        # Your code here

    def deposit(self, amount):
        # Your code here

    def withdraw(self, amount):
        # Your code here

# Create an instance of BankAccount and test deposit and withdraw methods
```

### Challenge 5:
* This is a "bonus challenge." Try to use a class to create a video game with two rectangles that can be moved indepently of eachother. For example, one uses WASD keys and one uses the arrows. Alternatively, you could use classes within a game to create a bunch of enemies. (Refer to the Space Invaders code https://www.mrmichaelsclass.com/python-programming/python-projects/space-invaders if you'd like). 


#### Possible solution for Challenge 4: 
```
class BankAccount:
    def __init__(self, account_holder, balance=0):
        self.account_holder = account_holder
        self.balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print(f"Deposit of ${amount} successful. New balance: ${self.balance}")
        else:
            print("Invalid deposit amount. Please deposit a positive amount.")

    def withdraw(self, amount):
        if amount > 0:
            if amount <= self.balance:
                self.balance -= amount
                print(f"Withdrawal of ${amount} successful. New balance: ${self.balance}")
            else:
                print("Insufficient funds for withdrawal.")
        else:
            print("Invalid withdrawal amount. Please withdraw a positive amount.")

# Create an instance of BankAccount
account1 = BankAccount("John Doe", 1000)

# Test deposit and withdraw methods
account1.deposit(500)
account1.withdraw(200)
account1.withdraw(900)  # This should print "Insufficient funds for withdrawal."
account1.deposit(-100)  # This should print "Invalid deposit amount. Please deposit a positive amount."
```
