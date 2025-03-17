# gravel
import pygame
import random


pygame.init()
screen = pygame.display.set_mode((800,800))
pygame.display.set_caption("gravel")

#create a buncha empty lists
sizes1 = []
positions1 = []
colors1 = []


#push a buncha numbers into the lists
for i in range(1000):
    sizes1.append(random.randrange(5,10)) #push in 1 number
    positions1.append((random.randrange(0, 800),random.randrange(500, 800))) #push in a 2-slot TUPLE
    colors1.append((random.randrange(4,55),random.randrange(6,25),random.randrange(6,25))) #push in a 3-slot TUPLE



while 1: #game loop###########################################################
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    #render section------------------------------
    
    screen.fill((0,0,0))# Clear the screen

    #draw the lines on the screen
    pygame.draw.line(screen, (255,255,255), (400, 0), (400, 800), 2)

    #draw the gravel
    for i in range(1000):
        pygame.draw.circle(screen, colors1[i], (positions1[i][0], positions1[i][1]), sizes1[i])
    
    pygame.display.flip()# Update the display

#end of game loop###################################################################
pygame.quit()
