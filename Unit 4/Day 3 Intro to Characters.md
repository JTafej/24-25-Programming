## We spent the last couple of days exploring someone elses code for the game Space Invaders.
### You may have some time at the end of the period today to continue working on that, but we should also talk about how you can include characters of your own in your game. 


## Task 1: The first thing you need to do today is to create a "player" character and two "enemy" chracters using this website: https://www.piskelapp.com/p/create/sprite I will help eveyone get started with this. Note, the code below won't work until you have your character created, downloaded, and uploaded into codeHS.



### The code below sets up a window, initializes Pygame, and creates a simple game loop. The player can be moved left and right using the arrow keys. The game loop continuously checks for user input, updates the player's position, and redraws the screen. You have seen this before. 
```
import pygame
import sys

# Initialize Pygame
pygame.init()

# Set up display
width, height = 600, 400
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("Simple Pygame Example")

# Set up colors
white = (255, 255, 255)
blue = (0, 0, 255)

# Set up player
player_size = 50
player_x = width // 2 - player_size // 2
player_y = height - 2 * player_size
player_speed = 5

# Game loop
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT] and player_x > 0:
        player_x -= player_speed
    if keys[pygame.K_RIGHT] and player_x < width - player_size:
        player_x += player_speed

    # Update display
    screen.fill(white)
    pygame.draw.rect(screen, blue, (player_x, player_y, player_size, player_size))

    pygame.display.flip()

    # Set the frames per second
    pygame.time.Clock().tick(60)
```
### Now, this is great and all, but we have done this already. Lets say we want to introduce a character of our own! We have to do 3 additional things. Notice the differences in the code below. 
- 1.) We load the player image using pygame.image.load("player.png").
- 2.) We create a rectangle (player_rect) that represents the player's position and size.
- 3.) The blit method is used to draw the player image onto the screen at the position specified by player_rect.
  
```
import pygame
import sys

# Initialize Pygame
pygame.init()

# Set up display
width, height = 600, 400
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("Pygame with Player Image")

# Set up player
player_image = pygame.image.load("player.png")
player_rect = player_image.get_rect()
player_rect.topleft = (width // 2 - player_rect.width // 2, height - 2 * player_rect.height)
player_speed = 5

# Game loop
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT] and player_rect.left > 0:
        player_rect.x -= player_speed
    if keys[pygame.K_RIGHT] and player_rect.right < width:
        player_rect.x += player_speed

    # Update display
    screen.fill((255, 255, 255))
    screen.blit(player_image, player_rect)

    pygame.display.flip()

    # Set the frames per second
    pygame.time.Clock().tick(60)

```
### This final piece of code includes enemies. Your challenge for today is to create two enemies and one character using piskelapp.com and included them in the game below! Spend some time making the characters cool.
#### New additions in this code are the following: 
-a list of enemies to store information about each enemy
-The create_enemy function generates a new enemy with a random image, position at the top of the screen, and a random speed.
-The game loop updates the positions of existing enemies, creates new enemies randomly, and checks for collisions with the player.
-If an enemy reaches the bottom of the screen, it is removed from the list, and a new enemy is created.
-If the player collides with any enemy, a simple "Game Over!" message is printed, and the game exits. You may want to implement a more sophisticated game over mechanism.
-The game also now includes a timer and a score based on the time the user survives. 

```
import pygame
import sys
import random

# Initialize Pygame
pygame.init()

# Set up display
width, height = 600, 400
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("Pygame with Player Image and Enemies")

# Set up player
player_image = pygame.image.load("player.png")
player_rect = player_image.get_rect()
player_rect.topleft = (width // 2 - player_rect.width // 2, height - 2 * player_rect.height)
player_speed = 5

# Set up enemies
enemy_images = [pygame.image.load("enemy1.png"), pygame.image.load("enemy2.png")]
enemies = []

def create_enemy():
    enemy_image = random.choice(enemy_images)
    enemy_rect = enemy_image.get_rect()
    enemy_rect.topleft = (random.randint(0, width - enemy_rect.width), 0)
    return {"image": enemy_image, "rect": enemy_rect, "speed": random.uniform(1, 3)}

# Set up timer and score display
start_time = pygame.time.get_ticks()
score_font = pygame.font.Font(None, 36)
score = 0


# Game loop
clock = pygame.time.Clock()
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT] and player_rect.left > 0:
        player_rect.x -= player_speed
    if keys[pygame.K_RIGHT] and player_rect.right < width:
        player_rect.x += player_speed

    # Move enemies
    for enemy in enemies:
        enemy["rect"].y += enemy["speed"]
        if enemy["rect"].top > height:
            enemies.remove(enemy)
            enemies.append(create_enemy())
            score += 1 

    # Create new enemies
    if random.randint(0, 100) < 5:
        enemies.append(create_enemy())

    # Check for collisions with player
    for enemy in enemies:
        if player_rect.colliderect(enemy["rect"]):
            end_time = pygame.time.get_ticks()
            duration = (end_time - start_time) / 1000  # Convert milliseconds to seconds
            print(f"Game Over! You survived for {duration:.2f} seconds.")
            pygame.quit()
            sys.exit()

    # Update display
    screen.fill((255, 255, 255))
    screen.blit(player_image, player_rect)

    for enemy in enemies:
        screen.blit(enemy["image"], enemy["rect"])
 # Display the score
    score_text = score_font.render(f"Score: {score}", True, (0, 0, 0))
    screen.blit(score_text, (10, 10))

    pygame.display.flip()

    # Set the frames per second
    clock.tick(60)
```

