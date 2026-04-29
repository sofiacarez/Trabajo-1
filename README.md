# Trabajo-1: RESERVAS HABITACIONES DE HOTEL
#Integrantes:
#Danae Caro Castillo 22.223.182-5
#Angela Navia Gallegos 22.521.765-3
#Sofía Carez Chandia 20.973.833-3

# SISTEMA DE PLANIFICACIÓN DE RESERVACIÓN DE HOTEL
def mostrar_menu():
    menu = ""
SISTEMA DE PLANIFICACIÓN DE RESERVAS DE HOTEL
1. Generar plan de reservas
2. Ingresar costo de reservas por habitación y día
3. Visualizar ingreso total por habitación
4. Visualizar ingreso total por día
5. Salir del programa
  print(menu)

# Funcion para mostrar tipo de habitacion y dias de reserva
def generar_plan(filas, columnas):
    matriz = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            fila.append(0)
        matriz.append(fila)
    return matriz
print(generar_plan(2, 3))

# Mostrar matriz de reserva
def mostrar_plan(matriz, etiqueta_fila, etiqueta_columna, titulo):
    print(" " + titulo)
    print("*" * 50)
    print(f"{etiqueta_fila:<18}", end = "") 

    for dia in range(len(matriz[0])):  #recorrer plan para imprimir los numeros de los dias segun la cantidad de columnas del plan
        print(f"{etiqueta_fila} {dia + 1:<18}", end="")  #alinea cada numero de dia a la izquierda con un ancho de 18 espacios
    print()

    for habitacion in range(len(matriz)):  #
        print(f"{etiqueta_fila} {habitacion + 1:<18}", end="")
    print()

    print("*" * 50)

# Ingresar     

        
        

    
    
    
