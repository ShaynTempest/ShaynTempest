import pygame

# Initialize Pygame
pygame.init()

# Set up the window
window = pygame.display.set_mode((600, 600))
pygame.display.set_caption("Monkey App")

# Load the images of the monkey
monkey1 = pygame.image.load("monkey1.png")
monkey2 = pygame.image.load("monkey2.png")

# Set the initial image of the monkey
monkey = monkey1

# Main game loop
while True:
    # Check for events
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            quit()
        elif event.type == pygame.KEYDOWN:
            if event.key == pygame.K_p:
                # Change the image of the monkey when the "p" key is pressed
                if monkey == monkey1:
                    monkey = monkey2
                else:
                    monkey = monkey1

    # Clear the screen
    window.fill((255, 255, 255))

    # Draw the monkey
    window.blit(monkey, (100, 100))

    # Update the screen
    pygame.display.update()
