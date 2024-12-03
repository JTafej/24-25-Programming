## Today we will continue building the game we started last week. 
You will see below that the code is similar to what we did Monday, with a few key spots added. 
```
import pygame

pygame.init()

SCREEN_WIDTH = 600
SCREEN_HEIGHT = 400

screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))
wall1 = pygame.Rect((140, 80, 500, 20))
player = pygame.Rect((300, 250, 20, 20))

def draw_text(text, font, text_col, x, y):
  img = font.render(text, True, text_col)
  screen.blit(img, (x, y))

text_font = pygame.font.SysFont("Helvetica", 30)

run = True

Grey = (200, 200, 200)
Blue = (200, 100, 100)
Col = Grey
Col2 = Blue
while run:
  
  screen.fill((0,0,200))
  if player.colliderect(wall1):
    Col = Col2
    draw_text("YOU LOSE", text_font, (255, 255, 255), 220, 150)
  
  
  pygame.draw.rect(screen, (2,255, 200), player)
  pygame.draw.rect(screen, Col, wall1)
  
  key =pygame.key.get_pressed()
  if key[pygame.K_a] == True:
    player.move_ip(-1, 0)
  if key[pygame.K_d] == True:
    player.move_ip(1, 0)
  if key[pygame.K_w] == True:
   player.move_ip(0, -1)
  if key[pygame.K_s] == True:
        player.move_ip(0, 1)


  
  for event in pygame.event.get():
    print(event)
    if event.type == pygame.QUIT:
      run = False

  pygame.display.update()

pygame.quit()
```

### This code defines a function for printing the text that appears after a collision, it also tells the program what font to use. 
```
def draw_text(text, font, text_col, x, y):
  img = font.render(text, True, text_col)
  screen.blit(img, (x, y))

text_font = pygame.font.SysFont("Helvetica", 30)
```

### This code tells the program if we a collision has happened. (In this case the only two objects are wall1 and player.) When a collision happens, the color of the long rectangle is changed, and the text "YOU LOSE" gets printed on the screen. 
```
if player.colliderect(wall1):
  Col = Col2
  draw_text("YOU LOSE", text_font, (255, 255, 255), 220, 150)

```
## Your challenge for today is to design a game (ON PAPER!) where you have a start point and an end point for a rectangle, with some puzzle to naviagate through. This could be a maze like you made on Monday (but this time with collisions), it could be a game where you have to tap every rectangle to turn them a certain color, or something entirely different. You must use text and collisions in your game. Once you have a drawing on paper, show me and then you can get started coding the project. 








