# Trabajo-1: RESERVAS HABITACIONES DE HOTEL
#Integrantes:
#Danae Caro Castillo 22.223.182-5
#Angela Navia Gallegos 22.521.765-3
#Sofía Carez Chandia 20.973.833-3

#Listas vacias
tipo_habitacion = []
dias = []
pagos = []

#Menú en while
opcion = 0
while opcion != 5:
  print("\n=== Sistema de planificación de reservación de habitaciones de hotel ===")
  print("1. Reservar")
  print("2. Costo por habitación y día")
  print("3. Ingreso total por habitación")
  print("4. Ingreso total por día")
  print("5. Salir")
  opcion = int(input("Seleccione una opción: "))

#Funcion para mostrar tipo de habitacion y dias de reserva
  if opcion == 1:
    habitacion = input("Ingrese número de habitacion(es): ").strip().title()
    dia = input("Ingrede día(s) de reserva: ").strip()
