## Hello again!
### Today we will continue working with the tile map you used yesterday. If you'll recall, you created a tile map of your own choice. Today, as you saw in the code that was printed out, we will be adding a background, and a character that moves using 2d graphics. 

### The code that was printed on the sheet is shown below. You can use this as your starting place, or you can choose to take the pieces of the code and implement them into your current tile map. 

#### Again, [here is a link](https://www.youtube.com/watch?v=5Ui51gD3uRE) to the video that the code is from if you want to watch/learn more about each step in the process. 

### Your challenge for today is to add y motion using the x motion as a starting point, at and to make a map that works for your screen size. 

```
import pygame

# Define a 2d Vector
vector = pygame.math.Vector2

#Initialize the game
pygame.init()

# Set display surface (divisible by 32 tile size)
WINDOW_WIDTH = 960 # 30 columns
WINDOW_HEIGHT = 640 # 20 rows
display_surface = pygame.display.set_mode((WINDOW_WIDTH,WINDOW_HEIGHT))
pygame.display.set_caption("Aspen Platformer - Codemy.com")

# Set FPS and clock
FPS = 60
clock = pygame.time.Clock()

# Tile Class
class Tile(pygame.sprite.Sprite):
	# Read and Create tiles and put em on the screen
	def __init__(self, x, y, image_integer, main_group, sub_group=""):
		super().__init__()
		# Load image and add to the tile subgroups
		if image_integer == 1:
			self.image = pygame.image.load('dirt.png')
		elif image_integer == 2:
			self.image = pygame.image.load('grass.png')
			sub_group.add(self)
		elif image_integer == 3:
			self.image = pygame.image.load('water.png')
			sub_group.add(self)

		# add every tile to main tile group
		main_group.add(self)

		# Get rect of images and position within the grid
		self.rect = self.image.get_rect()
		self.rect.topleft = (x,y)

# Apsen Player Class
class Aspen(pygame.sprite.Sprite):
	def __init__(self, x, y):
		super().__init__()
		# Define our aspen image
		self.image = pygame.image.load("dirt.png")
		# Get rect
		self.rect = self.image.get_rect()
		# Postion aspen
		self.rect.bottomleft = (x,y)

		# Kinematic Vectors (x,y)
		self.position = vector(x,y)
		self.velocity = vector(0,0) # Don't move to start 0,0
		self.acceleration = vector(0,0) # no speeding up or slowing down to start 0,0

		# Kinematic Constants
		self.HORIZONTAL_ACCELERATION = 2 #How quick player speeds up
		self.HORIZONTAL_FRICTION = 0.10 # friction



	def update(self):
		# set the initial acceleration to 0,0 to start
		self.acceleration = vector(0,0)
		keys = pygame.key.get_pressed()
		if keys[pygame.K_LEFT]:
			self.acceleration.x = -1 * self.HORIZONTAL_ACCELERATION
		if keys[pygame.K_RIGHT]:
			self.acceleration.x = self.HORIZONTAL_ACCELERATION

		# Calculate new Kinematics
		self.acceleration.x -= self.velocity.x * self.HORIZONTAL_FRICTION
		self.velocity += self.acceleration # (1,2) + (3,4) = (4,6)
		self.position += self.velocity + 0.5 * self.acceleration

		# update rect
		self.rect.bottomleft = self.position




# Define our sprite groups
main_tile_group = pygame.sprite.Group()
grass_tile_group = pygame.sprite.Group()
water_tile_group = pygame.sprite.Group()
aspen_group = pygame.sprite.Group()


# Create a tile map, nested python list: 0=no tile, 1=dirt, 2=grass, 3=water, 4=aspen
tile_map = [
	[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
	[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
	[2,2,2,2,2,2,2,2,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,2,2,2,2],
	[1,1,1,1,1,1,1,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1,1,1],
	[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
	[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
	[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,2,2,2,2,0,0,0,0,0,0,0],
	[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1,1,1,0,0,0,0,0,0,0],
	[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
	[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
	[0,0,0,0,0,0,0,0,0,0,2,2,2,2,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
	[0,0,0,0,0,0,0,0,0,0,1,1,1,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
	[2,2,2,2,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,2,2],
	[1,1,1,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1],
	[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
	[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
	[4,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],
	[2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,2,0,0,0,0,0,0,2,2,2,2,2],
	[1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,3,3,3,3,3,3,1,1,1,1,1],
	[1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,3,3,3,3,3,3,1,1,1,1,1]
]

# Create Tile objects from the tile map
# 2 for loops because tile map is nested. 20 i down
for i in range(len(tile_map)):
	# loop thru the 30 elements in each list, j across
	for j in range(len(tile_map[i])):
		# Check for 0,1,2,3
		if tile_map[i][j] == 1:
			# dirt
			Tile(j*32, i*32, 1, main_tile_group)
		elif tile_map[i][j] == 2:
			# grass
			Tile(j*32, i*32, 2, main_tile_group, grass_tile_group)
		elif tile_map[i][j] == 3:
			# water
			Tile(j*32, i*32, 3, main_tile_group, water_tile_group)
		elif tile_map[i][j] == 4:
			aspen = Aspen(j*32, i*32 + 32)
			aspen_group.add(aspen)


# Add a background
bg_image = pygame.image.load('space.png')
bg_image_rect = bg_image.get_rect()
bg_image_rect.topleft = (0,0)



# Game Loop
running = True
while running:
	# Check to quit
	for event in pygame.event.get():
		if event.type == pygame.QUIT:
			running = False

	# fill the display or blit an image
	# display_surface.fill("black")
	display_surface.blit(bg_image, bg_image_rect)

	# Draw the Tiles
	main_tile_group.draw(display_surface)

	# Update and draw sprites
	aspen_group.update()
	aspen_group.draw(display_surface)


	# Update Display
	pygame.display.update()
	clock.tick(FPS)

# End the game
pygame.quit()
```
