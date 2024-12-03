## In your group of three, use this code and find the RGB values that correspond to the color on the board. 

```
import pygame

pygame.init()

SCREEN_WIDTH = 600
SCREEN_HEIGHT = 400

screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))
wall1 = pygame.Rect((140, 80, 200, 20))
player = pygame.Rect((30, 250, 20, 20))
run = True
while run:

  screen.fill((R,G,B))

  for event in pygame.event.get():
    print(event)
    if event.type == pygame.QUIT:
      run = False

  pygame.display.update()

pygame.quit()
```

## Now, please import the code below into replit. 

```
import pygame

pygame.init()

SCREEN_WIDTH = 800
SCREEN_HEIGHT = 600

screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))
wall1 = pygame.Rect((140, 80, 500, 20))
player = pygame.Rect((300, 250, 20, 20))
run = True
while run:
  
  screen.fill((0,0,200))
  pygame.draw.rect(screen, (150, 250, 0), player)
  pygame.draw.rect(screen, (255, 2, 0), wall1)
  
  key =pygame.key.get_pressed()
  if key[pygame.K_a] == True:
    player.move_ip(-1, 0)
 
    
  for event in pygame.event.get():
    print(event)
    if event.type == pygame.QUIT:
      run = False

  pygame.display.update()

pygame.quit()
```

## You will notice that the character can only move to the left. (Only the a key works.) You will also notice that there is only one wall. Your task is to create a maze of walls so that the character must navigate through them.  
## You need at least 8 walls, and you must change the color of the walls and the player(Small square). 








