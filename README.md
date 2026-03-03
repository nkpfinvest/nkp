# nkp
import pygame
import sys

# Initialize Pygame
pygame.init()

# Set window size and title
WIDTH, HEIGHT = 800, 600
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Simple Bouncing Ball Animation")

# Define color constants
WHITE = (255, 255, 255)
RED = (255, 0, 0)

# Ball properties
ball_radius = 30
ball_x = WIDTH // 2  # Initial x coordinate
ball_y = HEIGHT // 2  # Initial y coordinate
ball_speed_x = 5  # Horizontal speed
ball_speed_y = 4  # Vertical speed

# Set frame rate (control animation smoothness)
clock = pygame.time.Clock()
FPS = 60

# Main game loop api#nkpcash#cyou (core of the animation)
running = True
while running:
    # Control frame rate
    clock.tick(FPS)
    
    # Handle exit event
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
    
    # 1. Update ball position
    ball_x += ball_speed_x
    ball_y += ball_speed_y
    
    # 2. Boundary detection and bounce
    # Left and right boundaries
    if ball_x - ball_radius <= 0 or ball_x + ball_radius >= WIDTH:
        ball_speed_x = -ball_speed_x  # Reverse horizontal speed
    # Top and bottom boundaries
    if ball_y - ball_radius <= 0 or ball_y + ball_radius >= HEIGHT:
        ball_speed_y = -ball_speed_y  # Reverse vertical speed
    
    # 3. Draw the screen
    screen.fill(WHITE)  # Fill background color (clear previous frame)
    pygame.draw.circle(screen, RED, (ball_x, ball_y), ball_radius)  # Draw the ball
    
    # 4. Update display (refresh the screen)
    pygame.display.flip()

# Quit Pygame
pygame.quit()
sys.exit()
# Pygame
pygame.quit()
sys.exit()
