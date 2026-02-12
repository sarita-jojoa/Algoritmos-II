# Taller 1
## Comparación de rendimiento lista vs array
### Primer problema


``` python
# importamos el modulo time para medir el tiempo de ejecución
import time
# importamos la libreria numpy
import numpy as np 

n = 1_000_000 # cantidad de valores a procesar
lista = list(range(n))
array = np.array(lista)

# con este método se recorre cada elemento de la lista y se multiplica por 3 uno por uno
tiempo_inicio = time.time()
lista_resultado = []
for x in lista:
    lista_resultado.append(x * 3)
tiempo_lista = time.time () - tiempo_inicio

# con este método numpy realiza la multiplicación sobre todos los elementos al mismo tiempo 
tiempo_inicio = time.time ()
array_resultado = array * 3
tiempo_array = time.time () - tiempo_inicio 

# se imprimen los tiempos de ejecución de ambos metodos para comparar su rendimiento
print("tiempo con lista:", tiempo_lista, "segundos")
print("tiempo con numpy:", tiempo_array, "segundos")
``` 
### salida de consola
tiempo con lista: 0.2592332363128662 segundos

tiempo con array: 0.007596492767333984 segundos

<img width="837" height="594" alt="image" src="https://github.com/user-attachments/assets/ac234df3-00f1-49c1-b5a0-f1cb0ebdd47d" />



1. Es notable que el programa es más rapido cuando se usa array, esto se debe a que la lista debe usar un ciclo for el cual multiplica los números uno por uno, por lo tanto toma más tiempo en ejecutar, y el array hace la multiplicación con todos los números al mismo tiempo y por eso es más rapido.
2. las listas guardan datos como objetos separados en diferentes partes de la memoria, esto causa que el programa busque cada dato uno por uno, haciendolo más lento. En cambio array (numpy) guarda los datos juntos y ordenados en la memoria, provocando mayor rapidez.
3. Array (numpy) es la mejor opción para procesar grandes volumenes de datos númericos, ya que permite realizar cálculos más rapido y ordenado usando menos memoria.


### Segundo problema

``` python

# lista original de notas de los estudiantes.
notas = [3.0, 2.9, 4.5, 3.8, 2.5, 1.8, 2.9, 4.2, 5.0, 2.9]

#muestra notas originales por estudiante
for i, nota in enumerate(notas):
    print(f"Estudiante: {i} {nota}")

#lista donde se guardan las notas mejoradas
notas_mejoradas = []

#recorre toda la lista.
#si la nota es 2.9, se le suma 0.3 como bonificación, si no cumple con la condición no se haran cambios.
for nota in notas:
    if nota == 2.9:
        notas_mejoradas.append (nota + 0.3)
    else:
        notas_mejoradas.append(nota)

# cálcula la suma total de notas
suma = 0
for n_m in notas_mejoradas:
    suma += n_m

#cálculamos el promedio de notas 
promedio= suma / len(notas_mejoradas)

#cálcula el numero de aprobados y reprobados
aprobados = 0
reprobados = 0

for nota in notas_mejoradas:
    if nota >= 3.0:
        aprobados += 1
    else:
        reprobados += 1    

print ("promedio del curso: ", promedio)
print ("estudiantes aprobados:", aprobados)
print ("estudiantes reprobados:", reprobados)

```

### Salida de consola

<img width="957" height="343" alt="image" src="https://github.com/user-attachments/assets/0d2109e3-4bc2-46f1-b879-6f41c5b32da4" />

Este programa toma una lista de notas de estudiantes y mejora automáticamente las notas que son iguales a 2.9, y les suma 0.3, luego cálcula cuántos estudiantes aprobaron y cuántos reprobarón teniendo en cuenta las notas mejoradas, además de calcular el promedio total de las notas.
