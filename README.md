# Proyecto_final-juego-de-adivinanza-de-numeros.
# En esta parte del codigo se da la bienvenida y te dice lo que debes hacer para iniciar el juego

    print("Bienvenido al juego de la adivinanza de numeros")
    print("Adivina el numero entre 1 al 100")
    def obtener_pista(numero_secreto, intento):
    diferencia = abs(numero_secreto - intento)

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

# Esta parte del codigo es la que te dice cuantas veces has intentado adivinar el numero 
# y si lo adivinaste o no

def jugar():
    numero_correcto = 27            
    intentos_maximos = 7
    intentos_hechos = 0
    historial_intentos = []

    while intentos_hechos < intentos_maximos:
        intento = int(input("Ingresa tu número: "))
        historial_intentos.append(intento)
        print(obtener_pista(numero_correcto, intento))
        
 # aqui es donde se compara el numero que ingresaste con el numero correcto y
 # y el historial de estos intentos
 
        if intento == numero_correcto:
            break

        intentos_hechos += 1
        print(f"Intentos restantes: {intentos_maximos - intentos_hechos}")

    else:
        print(f"Has agotado tus intentos. El número era {numero_correcto}.")
    
    print("Tus intentos:", historial_intentos)
jugar()
