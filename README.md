# RETO_9_ALGO_MEDIO_FACIL
1. De los retos anteriores selecione 3 funciones y escribalas en forma de lambdas.

```pseudocode
# defini las variables de los precios
precio_pan = 300
precio_leche = 3300
precio_huevos = 350
# el usuario ingresa los valores   
p = int(input("Ingresa la cantidad de panes: "))
l = int(input("Ingresa la cantidad de bolsas de leche: "))
h = int(input("Ingresa la cantidad de huevos: "))
B = int(input("Ingresa el valor del billete en pesos: "))
print("la cantidad de panes, bolsas de leche y huevos son " + str(p)+ ", " +str(l)+ ", " +str(h)+ ", respectivamente, pagando con un billete de " + str(B)+ " pesos, le sobraria o faltaria: ")
#utilice la funcion lambda y multiplique el precio por la cantidad del producto
costo_total = lambda p, l, h: p * precio_pan + l * precio_leche + h * precio_huevos
total_compra = costo_total(p, l, h)
#calcule las vueltas con la funcion lambda
calcular_vueltas = lambda B, total_compra: B - total_compra
vueltas = calcular_vueltas(B, total_compra)
#si se cumple que las veltas es mayor de cero imprime el mensaje de lo contrario imprime el otro
if vueltas >= 0:
    print("Le sobra " + str(vueltas)+ " pesos")
else:
    print("le faltan " + str(abs(vueltas))+ " pesos")
```
```pseudocode
# defini la cantidad de kilos
peso_gallina = 6  
peso_gallo = 7    
peso_pollito = 1  
#el ususario introduce el numero
N = int(input("Ingresa el número de gallinas: "))
M = int(input("Ingresa el número de gallos: "))
K = int(input("Ingresa el número de pollitos: "))
print("con " + str(N)+ " gallinas, " + str(M)+ " gallos y " + str(K)+ " pollitos, me da: ")
#utilice la funcion lambda para llamar los numeros dados y hacer respectivas operaciones
cantidad_carne = lambda N, M, K: N * peso_gallina + M * peso_gallo + K * peso_pollito
total_carne = cantidad_carne(N, M, K)
#imprime el total de kilos
print("Un total de " + str(total_carne)+ " kilos")
```
```pseudocode
#defini lambda y realice valores correspondientes
numero_total_contagiados = lambda c, d: c * (2 ** d)
#el usuario ingresa los valores
c = int(input("Ingrese el número actual de contagiados: "))
d = int(input("Ingrese el número de días a partir de hoy: "))
#llame a la funcion y imprimi valores
n_total = numero_total_contagiados(c, d)
print("si el numero actual de contagiados es de: " + str(c))
print("El numero total de contagiados después de " + str(d)+ " dias sera " + str(n_total))
```

2. De los retos anteriores selecione 3 funciones y escribalas con argumentos no definidos (*args).

```pseudocode
#defini el promedio con argumentos no definidos y hice las operaciones correspondientes
def promedio( *numeros):
    cantidad = len(numeros)
    if cantidad <= 0:
        return 0
    suma = 0
    for n in numeros:
        suma += n
        return suma / cantidad

if __name__ == "__main__":
#el usuario introduce los valores
        n1 = float(input("ingrese el primer numero: "))
        n2 = float(input("ingrese el segundo numero: "))
        n3 = float(input("ingrese el tercer numero: "))
        n4 = float(input("ingrese el cuarto numero: "))
        n5 = float(input("ingrese el quinto numero: "))
#halle el promedio llamando los argumentos  
print("el promedio de " + str(n1)+ ", " + str(n2)+ ", " + str(n3)+ ", " + str(n4)+ ", " + str(n5)+ " es: ")
print(promedio(n1, n2, n3, n4, n5))
```
```pseudocode
#defini con argumentos no definidos las funciones con sus operaciones correspondientes para organizar los numeros 
def ascen( *numeros):
    ascendente = sorted(numeros)
    return ascendente
def descen( *numeros):
    ascendente = sorted(numeros, reverse=True)
    return ascendente
if __name__ == "__main__":
#el usuario ingresa los valores 
        n1 = float(input("ingrese el primer numero: "))
        n2 = float(input("ingrese el segundo numero: "))
        n3 = float(input("ingrese el tercer numero: "))
        n4 = float(input("ingrese el cuarto numero: "))
        n5 = float(input("ingrese el quinto numero: "))
#imprime los valores y llama los argumentos   
print("los numeros " + str(n1)+ ", " + str(n2)+ ", " + str(n3)+ ", " + str(n4)+ ", " + str(n5)+ " en forma ascendente son: ")
print(ascen(n1, n2, n3, n4, n5))
print("los numeros " + str(n1)+ ", " + str(n2)+ ", " + str(n3)+ ", " + str(n4)+ ", " + str(n5)+ " en forma descendente son: ")
print(descen(n1, n2, n3, n4, n5))
```
```pseudocode
#defini con argumentos no dfinidos y hice operaciones correspondientes
def raiz_cubica( *numeros):
    menor = min(numeros)
    raiz_cubica = menor ** 1/3
    return raiz_cubica 

if __name__ == "__main__":
#el usuario inserta los valores
        n1 = float(input("ingrese el primer numero: "))
        n2 = float(input("ingrese el segundo numero: "))
        n3 = float(input("ingrese el tercer numero: "))
        n4 = float(input("ingrese el cuarto numero: "))
        n5 = float(input("ingrese el quinto numero: "))
 #imprime la funcion definida y se indican los argumentos    
print("la raiz cubica del menor numero de " + str(n1)+ ", " + str(n2)+ ", " + str(n3)+ ", " + str(n4)+ ", " + str(n5)+ " es: ")
print(raiz_cubica(n1, n2, n3, n4, n5))
```

3. Escriba una función recursiva para calcular la operación de la potencia.

```pseudocode
def potencia(base, exponente):
# caso base
    if exponente == 0:
        return 1
    else:
#condicion de la funcion recursiva
        return base * potencia(base, exponente - 1)
#defini variales e imprimi resultados
base = 2
exponente = 3
resultado = potencia(base, exponente)
print(" la base " + str(base)+ " elevada a " + str(exponente)+ " da como resultado: " + str(resultado))
```

4. Utilice la siguiente plantilla de code para contar el tiempo. Realice pruebas para calcular fibonacci con iteración o con recursión. Determine desde que número de la serie la diferencia de tiempo se vuelve significativa. Importante: Revisar este hilo.

```pseudocode
import time
# defini la función para calcular Fibonacci de forma recursiva
def fibonacci_recursivo(n):
    if n <= 1:
        return n
    else:
        return fibonacci_recursivo(n - 1) + fibonacci_recursivo(n - 2)

# Determine desde qué número la diferencia de tiempo se vuelve significativa
numero_inicial = 0
limite_superior = 35  
#utilice for y la plantilla code dada 
for n in range(numero_inicial, limite_superior + 1):
    start_time = time.time()
    resultado_recursivo = fibonacci_recursivo(n)
    end_time = time.time()
    timer_recursivo = end_time - start_time
#imprimi el numero y el tiempo recursivo
    cadena = "{:.6f}".format(timer_recursivo) #lo puse en una cadena de solo seis decimales
    print("el numero: " + str(n)+ ", con un tiempo recursivo de: " + str(cadena)+ "s")

    # Defini un umbral de diferencia de tiempo significativa
    umbral_significativo = 1.0 
#se tiene que cumplir que el tiempo recursivo sea mayor que el umbral significativo si este llegara a ser menor se detiene el programa
    if timer_recursivo > umbral_significativo:
        print(f'Diferencia de tiempo significativa a partir de n={n}')
        break
```

5. Crear cuenta en stackoverflow y adjuntar imagen en el repo
[![punto2.png](https://i.postimg.cc/1XJHn0Fb/punto2.png)](https://postimg.cc/n997ND01)

6. Cosas de adultos....ir a linkedin y crear perfil....NO IMPORTA que estén iniciando, si tienen tiempo para redes poco útiles como fb, insta, o tiktok tienen tiempo para crear un perfil mamalón. Dejar enlace en el repo.
[![punto2.png](https://i.postimg.cc/R0YqFWqG/punto2.png)](https://postimg.cc/d78JNt2T)

