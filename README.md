# Reto 9
## 1.De los retos anteriores selecione 3 funciones y escribalas en forma de lambdas.
``` python
# Mi mamá me manda a comprar P panes a 300 cada uno, M bolsas de leche a 3300 cada una y H huevos a 350 cada uno. Hacer un programa que me diga las vueltas (o lo que quedo debiendo) cuando me da un billete de B pesos
if __name__ == "__main__":
  P = int(input("Ingrese la cantidad de panes comprados ")) #pedir al usuario la cantidad de cosas compradas
  M = int(input("Ingrese el número de bolsas de leche compradas "))
  H = int(input("Ingrese la cantidad de huevos comprados "))
  B = int(input("Ingrese la cifra del billete "))
  compra = (lambda x,y,z: (x*300 + y*3300 +z*350)) (P,M,H) #hacer la función anónima con parámetros y argumentos respectivamente
  #establecer los condicionales dependiendo si la cantidad pagada es mayor, menor o igual a lo equivalente del precio total de cosas compradas e imprimir el que se cumpla
  if B == compra:
    print("No sobra nada ni se debe nada de dinero")
  elif B < compra:
    deuda = abs(B-compra)
    print("La deuda es de " +str(deuda)+ " Pesos")
  else:
    vueltas = B-compra
    print("Las vueltas son " +str(vueltas)+ " Pesos")
```
``` python
# programa que utilice una función para calcular el valor de un préstamo C usando interés compuesto del i por n meses.
if __name__ == "__main__":
  C = int(input("Ingrese el valor solicitado para préstamo ")) #Pesos
  i = float(input("Ingrese el valor decimal de la tasa de interés del préstamo "))
  n = int(input("Ingrese la cantidad de meses para pagar el préstamo "))
  capital_a_pagar = (lambda s,t,r: s*((1+t))**r) (C,i,n) #Formula (función anónima) del interes compuesto de manera anónima con parámetros y argumentos respectivos
  print("El valor total del préstamo es de " +str(capital_a_pagar)+ " Pesos")
```
```python
# Hacer un programa que diga el número total de personas que se han contagiado cuando pasen D días a partir de hoy, si el número de contagiados actuales es C. numero de contagiados se duplica cada dia
if __name__ == "__main__":
  C = int(input("Ingrese el número actual de contagiados ")) #valores pedidos al usuario
  D = int(input("Ingrese el número de días de contagio a partir de hoy "))
  personas_contagiadas = (lambda x,y: x*(2)**y) (C,D) #formula (función anónima) basada en el crecimiento poblacional de bacterias, solo que aqui no se tiene en cuenta el euler sino la duplicacion de individuos contagiados
  print ("El número de personas contagiadas en " +str(D)+ " días es de " +str(personas_contagiadas))
```
## 2. De los retos anteriores selecione 3 funciones y escribalas con argumentos no definidos (*args).
```python
# Diseñe una función que calcule la cantidad de carne de aves en kilos si se tienen N gallinas, M gallos y K pollitos cada uno pesando 6 kilos, 7 kilos y 1 kilo respectivamente.

def cantidad_carne_aves(*args) -> int: #función con argumentos no definidos
  kilos_carne: int = 0 #se inicia los argumentos en 0
  for aves in args: #con los numeros guardados en la tupla, hacer:
    kilos_carne = N*6 + M*7 + K*1
  return kilos_carne   
if __name__ == "__main__":
  N = int(input("Ingrese la cantidad de gallinas ")) #valores que serán guardados en la tupla
  M = int(input("Ingrese la cantidad de gallos ")) 
  K = int(input("Ingrese la cantidad de pollitos "))
  print("La cantidad de carne de las aves es de " +str(cantidad_carne_aves(N,M,K))+ " kilos")
```
```python
# función matemática para calcular el área y el perimetro carrito
import math

def calcular_area (*args) -> float: #función con argumentos no definidos
  area_figura: int = 0 #se inicia los argumentos en 0
  for medidas in args: #con los numeros guardados en la tupla, hacer:
    area_figura = a*b + 2*(math.pi*r**2) #suma de las áreas
  return area_figura

def calcular_perimetro (*args) -> float: #función con argumentos no definidos
  perimetro_figura: int = 0 #se inicia los argumentos en 0
  for medidas in args: #con los numeros guardados en la tupla, hacer:
    perimetro_figura = 2*a+2*b + 2*(2*math.pi*r) #suma de los perimetros
  return perimetro_figura

if __name__ == "__main__": #argumentos definidos 
  r = int(input("Ingrese el radio de los círculos ")) #radio de los círculos
  a= int(input("Ingrese la altura del rectángulo ")) #altura del rectángulo
  b= int(input("Ingrese la base del rectángulo ")) #base del rectángulo
  print("El perimetro de la figura es " +str(calcular_perimetro(r,a,b))+ " y el area es " +str(calcular_area(r,a,b)))
```
```python
#area y volumen de la figura compuesta por un cono y una esfera
import math

def calcular_area_figura (*args) -> float: #función con argumentos no definidos
  area_figura:int = 0 #se inicia los argumentos en 0
  for medidas in args: #con los numeros guardados en la tupla, hacer:
    area_figura = 4*math.pi*r1**2 + math.pi*r2*(r2+a) #suma de las areas de la esfera y del cono
  return area_figura

def calcular_volumen_figura(*args) -> float: #función con argumentos no definidos
  volumen_figura:int = 0 #se inicia los argumentos en 0
  for medidas in args: #con los numeros guardados en la tupla, hacer:
    volumen_figura = (4/3)*math.pi*r1**3 + (1/3)*math.pi*r2**2*h #Suma de los volúmenes de la esfera y el cono respectivamente
  return volumen_figura

if __name__ == "__main__": #argumentos definidos por el usuario
  r1 = int(input("Ingrese el radio de la esfera "))
  r2= int(input("Ingrese el radio de la base del cono "))
  h= int(input("Ingrese la altura del cono "))
  a: float = (h**2+r2**2)**(0.5)
  print("El área de la figura es " + str(calcular_area_figura(r1,r2,h)) + " y el volumen es " +str(calcular_volumen_figura(r1,r2,h)))
```
## 3.Escriba una función recursiva para calcular la operación de la potencia.
```python
# función recursiva para calcular la operación de la potencia.
def potencia (base, n) -> int: #establecer una función que depende de dos valores 
  if n == 0: #caso base
    return 1
  else: #condición de la función recursiva 
    return base*potencia(base, n-1)

if __name__ == "__main__":
  base = int(input("Ingrese una base numérica "))
  n = int(input("Ingrese un exponente de la base "))
  potencia_calculada = potencia(base,n)
  print(str(base)+ " elevado a la " +str(n)+ " es igual a " +str(potencia_calculada))
```
## 4. Realice pruebas para calcular fibonacci con iteración o con recursión. Determine desde que número de la serie la diferencia de tiempo se vuelve significativa
```python
import time

def fibonacci(n:int) -> int: #definir la función
  # Caso base
  if n <= 1:
    return n
  else:
    #Condicion
    return fibonacci(n-1) + fibonacci(n-2)


start_time = time.time() #marca el inicio del código donde se quiere medir el tiempo de ejecución
fibonacci(41) #línea de código a la cual se le quiere medir el tiempo de ejecución, se estableció en 41 porque es el n en el que se demora de manera significativa (más de un minuto)
end_time = time.time()  #marca el final del código al cual se le quiere medir el tiempo de ejecución 

timer = end_time - start_time #variable que guarda el tiempo de ejecución 

print("El tiempo de ejecución es de " +str(timer)+ " segundos")
```
