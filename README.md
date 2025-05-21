# Proyecto_final-juego-de-adivinanza-de-numeros.
# Descripcion: Este proyecto es de un juego sobre tratar de adivinar un numero secreto teniendo 7 intentos para descifrarlo
# y señales si te estas acercando al numero o no
# En esta parte del codigo se da la bienvenida usando printf y te dice lo que debes hacer para iniciar el juego
# definiedo el numero con una funcion tambien se agrega una libreria para que de un numero aleatorio al adivinar

import random

print("Bienvenido al juego de la adivinanza de números")
print("Elige un nivel de dificultad:")
print("1 - Fácil (1-50, 10 intentos)")
print("2 - Medio (1-100, 7 intentos)")
print("3 - Difícil (1-150, 5 intentos)")

nivel = int(input("Introduce el número de tu elección: "))

# Ingresas el numero que quieras y esta parte del codigo con los if, elif y else te dan una aproximacion......
# del resultado

    if diferencia == 0:
        return "Excelente adivinaste el número"
    elif diferencia <= 2: 
        return "Estás muy cerca"
    elif diferencia <= 5:
        return "Cáliente, sigue intentando"
    else:
        return "Frío, estás lejos."

        nivel = int(input("Introduce el número de tu elección: "))

if nivel == 1:
    limite_superior = 50
    intentos_maximos = 10
elif nivel == 2:
    limite_superior = 100
    intentos_maximos = 7
else:
    limite_superior = 150
    intentos_maximos = 5

# Esta parte del codigo es la que te dice cuantas veces has intentado adivinar el numero a traves de los while
# y si lo adivinaste o no

    numero_correcto = random.randint(1, limite_superior)

def obtener_pista(numero_correcto, intento):
    diferencia = abs(numero_correcto - intento)
    if diferencia == 0:
        return "¡Excelente, adivinaste el número!"
    elif diferencia <= 2: 
        return "Estás muy cerca"
    elif diferencia <= 5:
        return "Caliente, sigue intentando"
    else:
        return "Frío, estás lejos."
        
 # aqui es donde se compara el numero que ingresaste con el numero correcto y
 # y el historial de estos intentos usando el if y el else
 def jugar():
    intentos_hechos = 0
    historial_intentos = []

    while intentos_hechos < intentos_maximos:
        intento = int(input(f"Ingresa tu número (1-{limite_superior}): "))
        historial_intentos.append(intento)
        print(obtener_pista(numero_correcto, intento))

        if intento == numero_correcto:
            print("¡Felicidades! Has adivinado el número correctamente.")
            break

        intentos_hechos += 1
        print(f"Intentos restantes: {intentos_maximos - intentos_hechos}")

    else:
        print(f"Has agotado tus intentos. El número era {numero_correcto}.")
    
    print("Tus intentos:", historial_intentos)

jugar()
# Integrantes: Gael Dorantes Garcia
