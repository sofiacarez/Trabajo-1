# Trabajo-1: RESERVAS HABITACIONES DE HOTEL
#Integrantes:
#Danae Caro Castillo 22.223.182-5
#Angela Navia Gallegos 22.521.765-3
#Sofía Carez Chandia 20.973.833-3


# MENÚ PRINCIPAL
def menu():
    plan = []   # Inicialmente no hay plan de reservas
    opcion = ¨"  # Iniciamos la variable
    while opcion != "5":  # El buble se repite hasta que el usuario escriba 5
        # Se muestra el menú principal
        print("\nSISTEMA DE PLANIFICACIÓN DE RESERVACIÓN DE HABITACIONES DE HOTEL")
        print("1. Generar plan de reservas")
        print("2. Ingresar costo de reservas por habitación y día")
        print("3. Visualizar ingreso total de una habitación")
        print("4. Visualizar ingreso total por día")
        print("5. Salir del programa")
        
        opcion = input("Seleccione su opción: ")
        
        if opcion == "1":
            # Se pide al usuario el número de habitaciones y días
            habitaciones = int(input("Ingrese número de habitaciones: "))
            dias = int(input("Ingrese número de días de reserva (máx 5): "))
            if dias > 5:
                print("Error: no se puede reservar más de 5 días.")
                continue
            plan = generar_plan_reservas(habitaciones, dias)
            print("\nPlan de reserva")
            for i in range(habitaciones):
                print(f"Habitación {i+1}: {plan[i]}")
        
        elif opcion == "2":
            if plan:
                plan = ingresar_costos(plan)
                print("\nPlan actualizado:")
                for i in range(len(plan)):
                    print(f"Habitación {i+1}: {plan[i]}")
            else:
                print("Primero debe generar un plan de reservas (opción 1).")
        
        elif opcion == "3":
            if plan:
                habitacion = int(input("Ingrese la habitación a calcular: "))
                ingreso_total_habitacion(plan, habitacion)
            else:
                print("Primero debe generar un plan de reservas.")
        
        elif opcion == "4":
            if plan:
                dia = int(input("Ingrese el día a calcular: "))
                ingreso_total_dia(plan, dia)
            else:
                print("Primero debe generar un plan de reservas.")
        
        elif opcion == "5":
            print("Fin de la ejecución del programa.")
            break
        else:
            print("Opción inválida, intente nuevamente.")

# Generar plan de reservas
def generar_plan_reservas(habitaciones, dias):
    # Se crea una matriz (lista de listas) llena de ceros
    # Cada fila representa una habitación, cada columna un día
    # segun tambien se puede hacer así: return [[0 for _ in range(dias)] for _ in range(habitaciones)]
    matriz = []
    for i in range(habitaciones):
        habitaciones = []
        for j in range(dias):
            habitaciones.append(0)
        matriz.append(habitaciones)
    return matriz

# Mostrar matriz de reserva
def mostrar_plan(matriz, etiqueta_fila, etiqueta_columna, titulo):
    print("\nPlan de reserva")
    print("*" * 50)

    print(f"{etiqueta_fila:<18}", end="") 
    for j in range(len(matriz[0])):  #recorrer plan para imprimir los numeros de los dias segun la cantidad de columnas del plan
        print(f"{etiqueta_columna} {j + 1:<18}", end="")
    print()

    for i in range(len(matriz)): 
        print(f"{etiqueta_fila} {i + 1:<18}", end="")
    print()

    print("*" * 50)


# Ingresar costos, es lo mismo que ya sabemos hacer pero ahora añadimos funciones
def ingresar_costos(plan):
  # Se recorre cada habitación (fila de la matriz)
    for i in range(len(plan)):
        print(f"\nHabitación {i+1}")

        # Se recorre cada día de esa habitación
        for j in range(len(plan[i])):
            while True:   # Bucle para validar que el costo esté en el rango correcto
                  costo = int(input(f"Ingrese costo del día {j+1}: "))
                  if 45000 <= costo <= 80000:   # Validación de rango
                        plan[i][j] = costo        # Se guarda el costo en la matriz
                        break
                  else:
                        print("Error, el costo debe estar entre $45.000 y $80.000.")
                        print("Debe ingresar un número válido.")
    return plan

# Calcular ingreso total de una habitación
def ingreso_total_habitacion(plan, habitacion):
    # Se suma el costo de todos los días de la habitación seleccionada
    total = sum(plan[habitacion-1])


# EJECUCIÓN DEL PROGRAMA
if __name__ == "__main__":
    menu()

        
        

    
    
    
