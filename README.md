# momento-2.
5.15
![image](https://github.com/user-attachments/assets/756f86f4-fcc6-4cab-a366-37914dc36158)

NUMERO = float(input("Ingrese el número 1: "))
MAX = NUMERO
MIN = NUMERO

for i in range(2, 101):
    NUMERO = float(input(f"Ingrese el número {i}: "))
    if NUMERO > MAX:
        MAX = NUMERO
    elif NUMERO < MIN:
        MIN = NUMERO

print(f"Máximo {MAX}, Mínimo {MIN}")
![image](https://github.com/user-attachments/assets/700ffb8b-46e2-4e0a-88e2-0585b309a89d)

5.16
![image](https://github.com/user-attachments/assets/fbfe3f8f-ef45-4eb7-9c80-14b6d65473e2)

N1 = int(input("Ingrese N1: "))
N2 = int(input("Ingrese N2: "))

MAX = (N1 + N2) / 2

while N1 != 999 or N2 != 999:
    N1 = int(input("Ingrese N1: "))
    N2 = int(input("Ingrese N2: "))

    if N1 == 999 and N2 == 999:
        break
    M = (N1 + N2) / 2
    if M > MAX:
        MAX = M
print(f"Media maxima = {MAX}")
![image](https://github.com/user-attachments/assets/1aac9c7e-464e-40cd-a077-34e50256323c)

5.17
![image](https://github.com/user-attachments/assets/2e180683-e1d8-440b-8591-12bfa99a155f)

SW = 0

while SW == 0:
    N = float(input("Ingrese un número: "))
    if N != int(N):
        print("Dato no valido")
        print("Ejecute nuevamente")

        SW = 1
    else:
        print(f"Correcto, {N} es entero")
![image](https://github.com/user-attachments/assets/97aa52c5-1c5d-4166-a09f-5ba8fdf3b1a9)

5.19

nombre = input("Nombre del estudiante: ")

while nombre != '***':
    
    BASIC = float(input("Notas de la asignatura BASIC"))
    Pascal = float(input("Notas de la aignatura Pascal"))
    FORTRAN = float(input("Notas de la asignatura FORTRAN"))
    media = (BASIC + Pascal + FORTRAN) / 3
    print(nombre, media)
    nombre = input("Nombre del estudiante: ")
![image](https://github.com/user-attachments/assets/e29ec179-daaf-4e55-b71b-e0b5001264a3)

5.9
Analicis: el codigo que nos pidieron para el desarrollo de este problema es posible secmentarlo en distintas partes para poder explicarlo, de manera que para dar con el importe por cantidad de articulos de cada categoria se va desarrollando la respuesta a medida que se van digitando los datos necesarios para el importe.
así, y mediante el uso de la estructura repetitiva while, es posible seguir sumando el valor del importe por producto de cada categoria hasta que se digite la variable "X" encargada de cortar con el bucle y soltando el resultado deseado.

Pseudocodigo:

algoritmo registro_ventas
var
  entero: total_articulos_A, total_articulos_B, numero_articulos
  real: total_importe_A, total_importe_B, precio_unitario
  caracter: codigo_articulo

inicio
  total_articulos_A ← 0
  total_articulos_B ← 0
  total_importe_A ← 0
  total_importe_B ← 0

  mientras (verdadero) hacer
    leer(codigo_articulo)
    si codigo_articulo == "X" entonces
      romper_mientras
    fin_si
    leer(precio_unitario)
    leer(numero_articulos)
    si codigo_articulo == "A" entonces
      total_articulos_A ← total_articulos_A + numero_articulos
      total_importe_A ← total_importe_A + precio_unitario * numero_articulos
    sino si codigo_articulo == "B" entonces
      total_articulos_B ← total_articulos_B + numero_articulos
      total_importe_B ← total_importe_B + precio_unitario * numero_articulos
    fin_si
  fin_mientras

  escribir("Número total de artículos tipo A: ", total_articulos_A)
  escribir("Importe total de artículos tipo A: ", total_importe_A)
  escribir("Número total de artículos tipo B: ", total_articulos_B)
  escribir("Importe total de artículos tipo B: ", total_importe_B)
fin

Codigo en python:

total_articulos_A = 0
total_articulos_B = 0
total_importe_A = 0
total_importe_B = 0

while True:

    codigo_articulo = input("Ingrese el código del artículo (A, B o X para terminar): ")
    
    if codigo_articulo == "X":
        break

    precio_unitario = float(input("Ingrese el precio unitario del artículo: "))
    numero_articulos = int(input("Ingrese el número de artículos: "))


    if codigo_articulo == "A":
        total_articulos_A += numero_articulos
        total_importe_A += precio_unitario * numero_articulos
    elif codigo_articulo == "B":
        total_articulos_B += numero_articulos
        total_importe_B += precio_unitario * numero_articulos
print(f"Número total de artículos tipo A: {total_articulos_A}")
print(f"Importe total de artículos tipo A: {total_importe_A}")
print(f"Número total de artículos tipo B: {total_articulos_B}")
print(f"Importe total de artículos tipo B: {total_importe_B}")

5.10
dias_totales = 0
dias_con_error = 0
suma_max_temperaturas = 0
suma_min_temperaturas = 0

while True:
    max_temperatura = float(input("Ingrese la temperatura máxima: "))
    min_temperatura = float(input("Ingrese la temperatura mínima: "))

    if max_temperatura == 0 and min_temperatura == 0:
        break 

    dias_totales += 1

    if max_temperatura == 9 or min_temperatura == 9:
        dias_con_error += 1 
    else:
        suma_max_temperaturas += max_temperatura 
        suma_min_temperaturas += min_temperatura  

if dias_totales - dias_con_error > 0:
    media_maxima = suma_max_temperaturas / (dias_totales - dias_con_error)
    media_minima = suma_min_temperaturas / (dias_totales - dias_con_error)
else:
    media_maxima = 0
    media_minima = 0


if dias_totales > 0:
    porcentaje_errores = (dias_con_error / dias_totales) * 100
else:
    porcentaje_errores = 0

print(f"Número total de días: {dias_totales}")
print(f"Número de días con errores (temperatura 9): {dias_con_error}")
print(f"Media máxima de temperaturas: {media_maxima:}")
print(f"Media mínima de temperaturas: {media_minima:}")
print(f"Porcentaje de errores: {porcentaje_errores:}%")
