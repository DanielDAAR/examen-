
import os
import math

def clear_screen():
    os.system('cls' if os.name == 'nt' else 'clear')

def draw_square(x, y):
    for i in range(4):
        for j in range(4):
            print('*', end=' ')
        print()

def draw_circle(x, y):
    radius = 2
    for i in range(-radius, radius + 1):
        for j in range(-radius, radius + 1):
            if math.sqrt(i**2 + j**2) <= radius:
                print('*', end=' ')
            else:
                print(' ', end=' ')
        print()

def draw_triangle(x, y):
    height = 4
    for i in range(height):
        for j in range(2 * i + 1):
            print('*', end=' ')
        print()

x, y = 10, 10
opcion = 1

while True:
    clear_screen()

    print("Selecciona una figura para dibujar:")
    print("1. Cuadrado")
    print("2. Círculo")
    print("3. Triángulo")
    print("Opción: " + str(opcion))

    key = input()

    if key == 'w':
        y -= 1
    elif key == 's':
        y += 1
    elif key == 'a':
        x -= 1
    elif key == 'd':
        x += 1
    elif key == '1':
        opcion = 1
    elif key == '2':
        opcion = 2
    elif key == '3':
        opcion = 3

    if opcion == 1:
        draw_square(x, y)
    elif opcion == 2:
        draw_circle(x, y)
    elif opcion == 3:
        draw_triangle(x, y)
