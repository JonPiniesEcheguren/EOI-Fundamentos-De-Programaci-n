# Ejercicios con algoritmos

## Primeros tres ejercicios

### Ejercicio 1

*Calcular la letra del DNI español*

**Paso 1**: Definir el problema, a partir de un número de DNI hemos de calcular la letra

¿Cómo se calcula la letra del DNI?

Número del DNI debe tener 8 dígitos, este DNI hay que dividirlo en 23 y el resto será el ```resultadoResto```
El valor contenido en ```ResultadoResto``` lo compararemos con la lista de código de la siguiente tabla de letras ```tablaLetrasDni```

| resultadoResto | Letra |
| -------------- | ----- |
| 0              | T     |
| 1              | R     |
| 2              | W     |
| 3              | A     |
| 4              | G     |
| 5              | M     |
| 6              | Y     |
| 7              | F     |
| 8              | P     |
| 9              | D     |
| 10             | X     |
| 11             | B     |
| 12             | N     |
| 13             | J     |
| 14             | Z     |
| 15             | S     |
| 16             | Q     |
| 17             | V     |
| 18             | H     |
| 19             | L     |
| 20             | C     |
| 21             | K     |
| 22             | E     |

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ```DNI```, ```tablaLetrasDni```, ```resultado```
Proceso: Validar que el DNI tenga 8 dígitos, y que sean todos numéricos.
         Si es errónea asigne a la variable ```resultado``` "DNI Inválido"
         Dividimos ```DNI``` en 23 y el resto lo asignamos a ```resultadoResto```
         Comparamos el ```resutltadoResto``` con los valores de la tabla y asignar a ```letraDNI``` el valor equivalente en la tabla

Salida: Escribir ```resultado```

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo CalculoDNI
    # Entrada
    DNI<-leer()
    tablaLetrasDNI="TRWAGMYFPDXBNJZSQVHLCKE"
    resultado<-""
    # Proceso
    si DNI es válido entonces
        resultadoResto<-DNI mod 23 #mod es el resto de dvidir
        resultado<-recuperarLetra(resultadoResto, tablasLetrasDNI)
    Sino
        resultado<-"DNI Inválido"
    Fin Si
    # Salida
    Escribir(resultado)
Fin Algoritmo
```

### Ejercicio 2

*Calcular el salario de un empleado*

**Paso 1**: Definir el problema

El salario en España se calcula a partir del salario bruto anual, que incluye todas las percepciones económicas que recibe un trabajador durante el año, incluyendo salario base, pagas extras, complementos y otros conceptos retributivos. 

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ```salarioBase```, ```pagasExtras```, ```complementos```, ```otrosConceptosRetributivos```

```IRPF```, ```Seguridad Social```

Proceso:

   Sumar ```salarioBase```, ```pagasExtras```, ```complementos```, ```otrosConceptosRetributivos``` y lo asigno a ```salarioBruto```
   Sumar ```IRPF```, ```Seguridad Social``` y lo asigno a ```deducciones```
   ```salarioNeto``` asigna ```salarioBruto``` - ```deducciones```

Salida:

Escribir(salarioBruto, salarioNeto)

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo CalculoDNI
    #Entrada
    salarioBase<-Leer()
    pagasExtras<-Leer() 
    complementos<-Leer() 
    otrosConceptosRetributivos<-Leer()
    IRPF<-Leer()
    Seguridad Social<-Leer()
    #Proceso
    salarioBruto<-salarioBase+pagasExtras+complementos+otrosConceptosRetributivos
    deducciones<-IRPF+SeguridadSocial
    #Salida
    Escribir(SalarioBruto, salarioNeto)
Fin Algoritmo
```

### Ejercicio 3

*Determinar la ruta para llegar a una ciudad por avión*

**Paso 1**: Definir el problema

Para llegar a una ciudad en avión:

* Elegir el destino
* Elegir la fecha
* Comprar vuelo
* Ir al aeropuerto
* Hacer el check-in
* Embarcar

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: `salidaAeropuerto` `destino` `fecha` `vuelo` `llegadaAeropuerto` ``checkIn`` ``haEmbarcado`` ``llegada`` 

Proceso:

* Buscar si hay vuelos desde tu aeropuerto `salidaAeropuerto` al aeropuerto del ``destino``  

* Buscar si hay vuelo disponible para la fecha ``fecha`` elegida

  * Si no hay vuelos al aeropuerto del destino:

    cambia el ``destino`` o el aeropuerto de salida

  * Si no hay vuelo en la ``fecha`` elegida:

    cambia la ``fecha`` de salida

* Comprar el ``vuelo`` 

* Ir al aeropuerto en la fecha del vuelo ``llegadaAeropuerto``

* Llegar 2 horas antes para hacer el ``check-in``

* ``embarcar`` al avión

Salida: Escribir la ruta (`salidaAeropuerto` `destino`)

**Paso 3**: Escribir pseudocódigo

```
Algoritmo RutaAvion
	#Entrada
	destino <- Leer()
	fecha <- Leer()
	vuelo <- Leer()
	llegadaAeropuerto <- Leer()
	checkIn <- Leer()
	haEmbarcado <- Leer()
	salidaAeropuerto <- Leer()
	llegada <- Leer()
	#Proceso
	Si salidaAeropuerto y destino son válidos:
	
		si fecha es válida:
			compra vuelo
			
		sino:
			elige otra fecha
			
	sino: 
		elige otro destino o salidaAeropuerto 
		
	si llegadaAeropuerto es mayor o igual a 2 horas:
		hacer checkin
		escribir ("Has llegado con tiempo")
		
	sino:
		hacer checkin
		escribir ("No has llegado con tiempo")
		
	si hora de terminar checkin es mayor o igual a la última llamada:
		puedes embarcar
		haEmbarcado = True
		
	sino: 
		el avión sale en 15 minutos las puertas están cerradas
		haEmbarcado = False
	
	si haEmbarcado y el avión a llegado sin problemas:
		llegada = True
		
	sino:
		llegada = False
	
	#Salida:
	si llegada = True:
		Escribir ("La ruta:", salidaAeropuerto, destino)
	
	sino:
		Escribir ("No ha salido el avión, no es posible calcular la ruta")
		
Fin algoritmo
```

### Ejercicio 4

*Calcula el área y perímetro de un círculo dado su radio.*

**Paso 1**: Definir el problema

Para calcular el área y el perímetro de un círculo dado su radio, podemos utilizar las siguientes fórmulas:

Área = pi x r^2

Perímetro = 2 x pi x r

Donde "r" es el radio del círculo y "pi" es una constante matemática aproximada a 3,1415

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ``area`` ``perimetro`` ``pi`` ``radioDelCirculo`` 

Proceso:

* Crea el valor estático para ``pi`` = 3,1415
* Crear fórmula para el ``área`` 
* Crear fórmula para el ``perímetro`` 

Salida: Escribir resultado de fórmulas para ``area`` y ``perímetro`` 

**Paso 3**: Escribir el pseudocódigo:

```
Algoritmo FormulasCirculo
	#Entrada
	radioDelCirculo = float(input("Radio del círculo:"))
	pi <- 0
	perimetro <- 0
	area <- 0
	#Proceso
	pi <- 3.1415
	area = pi x radioDelCirculo^2
	perimetro = 2 x pi x radioDelCirculo
	#Salida
	print ("Área:", area)
	print ("Perímetro:", perimetro)
Fin Algoritmo
```

### Ejercicio 5

*Dada una lista de números enteros, determina cuál es el mayor y cuál es el menor.*

**Paso 1**: Definir el problema

Introduce lista de números

El primer número se considerará menor y mayor en un primer momento. Se va a comparar cada número que continua la lista con el número almacenado y en caso de ser mayor o menor, lo sustituirá. Al final del proceso, las variables mayor y menor almacenarán el valor correcto que buscamos. 

Cuál es el número mayor

Cuál es el número menor

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ``mayor`` ``menor`` ``numerosAProcesar`` Usuario introduce la lista de números

Proceso:

Se comparan los números. El primer número se considerará menor y mayor en un primer momento. Se va a comparar cada número que continua la lista con el número almacenado y en caso de ser mayor o menor, lo sustituirá. Al final del proceso, las variables mayor y menor almacenarán el valor correcto que buscamos.

Se añade el valor más alto a mayor y el valor más bajo a menor

Salida: Se escribe en la pantalla ``mayor`` y ``menor`` 

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo CompararNumero
	#Entrada
	numerosAProcesar <- leer()
	Mayor <- 0
	Menor <- 0
	#Proceso
	numerosAProcesar <- input ("¿Cuántos números quiere procesar?")
	input_lista
	i <- 0
	repeat
		user_input <- input()
			if user_input is not blank
				input_list() <- user_input
				i <- i+1
			endif
	until user_input is not blank
	#Se comparan los numeros de la lista. El mayor va a Mayor y el menor a Menor
	Mayor <- input_list[0]
	Menor <- input_list[0]
	i <- 0
	repeat
		if input_list[i] > Mayor
			mayor <- input_list[i]
		end if
		if input_list[i] < Menor
			menor <- input_list[i]
		end if 
		i <- i+1
	until i es mayor a numerosAProcesar
	#Salida
	Escribir (mayor)
	Escribir (menor)
Fin Algoritmo
```

### Ejercicio 6

*Crea un algoritmo que convierta grados Celsius a Fahrenheit.*

**Paso 1**: Definir el problema

Pasar un valor en grados Celsius a grados Fahrenheit aplicando la fórmula correspondiente. Dado un dato de entrada numérico que se asume que es ```gradosCelsius``` , aplicar la siguiente fórmula: F=C*1,8+32

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ```gradosCelsius``` 

Proceso:

* Multiplicar `gradosCelsius` por 1.8, sumarle 32 y asignarle este resultado a `gradosFahrenheit` 

Salida:

Escribir `gradosFahrenheit` 

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo conversorGrados
	# Entrada
	gradosCelsius <- Leer()
	#Proceso
	gradosFahrenheit<-gradosCelsius*1.8+32
	#Salida
	Escribir(gradosFahrenheit)
Fin Algoritmo
```

### Ejercicio 7

*Dado un número entero, crea un algoritmo que determine si es par o impar.*

**Paso 1**: Definir el problema, dado un número entero, crea un algoritmo que determine si es par o impar. Si el resto de dividir un número entre dos es igual a 0, entonces el número se considera par. En caso de que el resto sea igual a 1, se considera el número impar.

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ```número``` 

Proceso: 

* Si el resto de dividir ```número``` entre 2 es 0, entonces se asigna a ```resultado ```  "es par"
* En caso contrario, se asigna a ```resultado``` "es impar"

Salida:

Escribir (resultado)

**Paso 3**: Escribir pseudocódigo

```
Algoritmo parImpar
	#Entrada
	número<-Leer()
	#Proceso
	Si número mod 2 es igual a 0 entonces
		resultado<- "es par"
	sino
		resultado<- "es impar"
	#Salida
	Escribir(resultado)
Fin Algoritmo
```

### Ejercicio 8

*Crea un algoritmo que determine si un año es bisiesto o no*

**Paso 1**: Definir el problema

Si el año que queremos calcular es divisible con 400 este será un año bisiesto. En caso de cumplir esta condición, ya sabe,os que es bisiesto así que no necesitamos calcular más, si nos dio error vamos por la siguiente validación.

Ahora debemos ver si es divisible por 4 pero no debe ser divisible por 100, si cumple esta condición entonces es un año bisiesto. La regla resumida para calcular año bisiesto es el siguiente: 

Cada 400 años hay un ajuste, ya que el año aun usando años bisiesto se pierden milésimas de segundo, entonces cada 400 años se agrega un día extra. Y como ya sabemos cada 4 años tenemos un día extra. 

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ``anyo``

Proceso: Con la condición dividimos ``anyo``  entre 400 si el resto es 0 es bisiesto o dividimos el ``anyo``  entre 4 y 100 y si entre 4 da 0 y 100 distinto de 0 es bisiesto, sino no es bisiesto.

Salida: Escribe "Es bisiesto"

**Paso 3:** Escribir el pseudocódigo

```
Algoritmo anyoBisiesto
	#Entrada
	anyo<-Leer()
	#Proceso
	si(
		(anyo mod 400 igual a 0) o
		( (anyo mod 4 igual a 0) y (anyo mod 100 diferente a 0) )
		)
		resultado<- anyo + "es bisiesto"
	sino
		resultado<- anyo + "no es bisiesto"
	fin sentencia
	imprime resultado
Fin Algoritmo
```

### Ejercicio 9

**Paso 1**: Definir el problema

Crea un algoritmo que determine si una cadena de texto es un palíndromo o no.

Un palíndromo es un apalabra, número o frase que se lee igual al derecho y al revés, es decir, que se puede leer de igual manera de izquierda a derecha que de derecha a izquierda. El algoritmo debe ser capaz de identificar si una cadena de texto dada cumple con esta condición, sin importar si la cadena contiene espacios, signos de puntuación, o si las letras están en mayúsculas o minúsculas.

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ```cadena``` 

Proceso:

* Eliminamos los espacios en blanco de la cadena de texto y convertimos todo a minúsculas para que la comparación sea insensible a mayúsculas y minúsculas.
* Comparamos la cadena de texto original con su versión invertida.
* Si la cadena original es igual a su versión invertida, entonces la función retorna "Sí es palíndromo", indicando que la cadena de texto es un palíndromo.
* Caso contrario retorna "No es palíndromo"

Salida: Escribir es palíndromo o no palíndromo

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo Palindromo
	#Entrada
	cadena<-Leer()
	#Proceso
	cadena<- convertir a minúsculas y eliminar espacios en blanco
	reversa <- depuracionCadena(cadena)
		si cadena es igual a reversa entonces
			Escribir "La cadena es un palíndromo"
		sino
			Escribir "La cadena no es un palíndromo"
		Fin Si
	#Salida
Fin Algoritmo

SubAlgoritmo depuracionCadena (cadena)
    #quita los espacios en blanco, otros caracteres y convierte todo a minusculas
    i<-0
    Mientras cadena[i] sea diferente de findecadena Haga
        caracter<-""
        Si  el ASCII de cadena[i]  mayor que 64 y ASCII de cadena[i] menor que 91 Entonces
            caracter<-cadena[i] en minusculas
        Fin Si
        Si  el ASCII de cadena[i]  mayor que 96 y ASCII de cadena[i] menor que 123 Entonces
            caracter<-cadena[i]
        End Si
        temporal <- temporal + caracter
        Si caracter es diferente "" Entonces
            i<-i+1
        Fin Si
    Fin Mientras
    L<-i
    reversa<-""
    Para N = 0 Hasta L-1 Con Paso 1 Haga
        reversa    <-reversa+ temporal[i-1]
        i<-i-1
    Fin Para
    devuelva reversa
Fin SubAlgoritmo

```

### Ejercicio 10

*Dada una lista de nombres, crea un algoritmo que ordene la lista alfabéticamente.*

**Paso 1**: Definir el problema

Ante una lista de palabras hay que ordenarlas alfabéticamente. Los caracteres tienen un valor ASCII asignado. La ordenación alfabética se realizará teniendo en cuenta el valor ASCII de cada carácter de cada nombre. 

Debemos seleccionar la primera letra de cada palabra y ordenarlas según el alfabeto

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada:

Usuario define la lista de palabras

Proceso:

Se ordena la lista en orden alfabético. Un subAlgoritmo será el encargado de evaluar los valores ASCII de cada carácter y realizar esta ordenación de nombres. 

Salida:

La lista ordenada

**Paso 3**: Escribir el pseudocódigo

````
Algoritmo ordenarPalabras
	#Entrada
	input_list
	i <- 0
	repeat
		user_input <- input()
		if user_input is not blank
			input_list[i] <- user_input
			i <- i+1
		endif
	until user_input is blank
	#Proceso
	input_listOrdered <- ordenarAlfabeticamente(input_list)
	#Salida
	Escribir (input_listOrdered)
Fin Algoritmo
````

### Ejercicio 11

*Crea un algoritmo que calcule el factorial de un número entero.*

**Paso 1**: Definir el problema

El factorial de un número entero se define como el producto de todos los números enteros desde 1 hasta el número en cuestión. Por ejemplo, el factorial de 5 es igual a 5 x 4 x 3 x 2 x 1, que es igual a 120.

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ```factorial``` , ```numero```

Proceso:

* Definir una variable ```factorial``` con un valor inicial de 1
* Escribir un número y guardarlo en una variable llamada ```numero```
* Empezar un bucle "para" que vaya desde 1 hasta ```numero```
* En cada iteración del bucle, multiplicar ```factorial``` por el número actual del bucle
* Después imprimir el valor de ```factorial```

Salida: Escribir "El factorial del número es ```factorial```"

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo CalcularFactorial
	#Entrada
	numero = Recuperar Interger(leer("Numero entero:"))
	factorial=1
	#Proceso
	Para i desde 1 hasta n hacer
		factorial=factorial x i
	#Salida
	Escribir ("El factorial de", numero, "es", factorial)
Fin Algoritmo
```

### Ejercicio 12

*Dado un número entero, crea un algoritmo que determine si es primo o no.*

**Paso 1**: Definir el problema

Para determinar si un número es primo o no, se divide entre todos los números que le preceden hasta 1. Si alguno de los restos de esas divisiones es 0, el número no será primo.

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: El programa recibe de entrada un número para comprobar.

Proceso:

* Introducir el ```numero``` por teclado
* Validar que sean números
  * Si no es válido, se muestra un mensaje de error
* Se define la variable ```resultado``` 
* Para i=numero-1, hasta que i sea mayor que 1, dividimos el número entre i
* Se imprime "Primo" o "No primo" dependiendo del valor de las operaciones

Salida: Se imprime "Primo" o "No primo" dependiendo del valor de las operaciones

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo Primo
	numero <- leer entrada
	resultado <- 0
	primo <- true
	si numero diferente a entero
		imprimir "Error, el primo debe ser un entero"
	sino 
		para i = numero-1 hasta 2 con paso -1 hacer 
			resultado <- numero mod i
			si resultado = 0
				primo <- false
				i <- 2 #break
			fin si
		fin para
	fin si
	si primo = false entonces
		Imprimir "El número no es primo"
	sino entonces
		Imprimir "El número es primo"
	fin si
fin Algoritmo
```

### Ejercicio 13

*Crea un algoritmo que calcule el área y volumen de un cubo dado su lado.*

**Paso 1**: Definir el problema

Para determinar el área y volumen de un cubo debemos aplicar las respectivas fórmulas sabiendo la longitud de lado.

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ``area`` ``volumen`` ```ladoCubo``` Introduce la longitud del lado del cubo en metros

Proceso:

Calculo del área con la fórmula lado x lado

Cálculo del volumen con la fórmula lado x lado x lado 

Salida: ``area`` ``volumen``  Imprimir los resultados

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo CalculoCubo
	#Entrada
	ladoCubo <- leer()
	area <- 0
	volumen <- 0
	#Proceso
	area <- ladoCubo x ladoCubo
	volumen <- area x ladoCubo
	#Salida
	Escribir ("Área:" area)
	Escribir ("Volumen:" volumen)
Fin Algoritmo
```

### Ejercicio 14

*Dada una lista de números enteros, crea un algoritmo que calcule la suma de todos los números
pares de la lista.*

**Paso 1**: Definir el problema

El usuario introduce una lista de números. Aquellos números pares deben ser sumados y guardados en una variable. 

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ``numero``  ``numerLista`` ``suma``  ``numerParLista`` Introducir número uno a uno.

Proceso:

Se crea una lista con números. Se trasladan los números pares de dicha lista a otra nueva lista. Se suman los números de la segunda lista y se da el resultado.

Salida: Escribir ``suma`` 

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo SumaPar
	#Entrada
	numerLista[]
	numerParLista[]
	numero <- 0
	suma <- 0
	i <- 0
	j <- 0
	repetir:
		numero <- input()
		si user_input es un número entero:
			numerLista[i] <- numero
			i <- i+1
	hasta que numero no es un número entero
	#Proceso
	for num en numerLista[]:
		si num mod 2 igual a 0:
			numerParLista[j] <- num
			j <- j+1
		sino:
			j <- j+1
	for numPar en numerParLista[]:
		suma=suma+numPar
	#Salida
	Escribir("La suma de los números pares es de", suma)
Fin Algoritmo
```

### Ejercicio 15

*Crea un algoritmo que determine si un número es positivo, negativo o cero.*

**Paso 1**: Definir el problema

El usuario introduce un número. El programa debe identificar si el número es positivo, negativo o 0. Para ello se realizará una comparación entre el número de entrada y el número 0. Si el número introducido es mayor a 0 será positivo. Si el número introducido es menor a 0 será negativo. Si el número introducido es igual a 0 será cero.

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ``numero``. Introducir un número.

Proceso:

Se compara el número introducido con el número 0. Si el número introducido es mayor a 0 será positivo. Si el número introducido es menor a 0 será negativo. Si el número introducido es igual a 0 será cero.

Salida: Escribir el resultado

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo PosNegCero
	#Entrada
	numero <- input()
	#Proceso y Salida
	si numero<0:
		Escribir ("Número negativo")
	si numero>0:
		Escribir ("Número positivo")
	sino:
		Escribir ("El número es cero")
Fin Algoritmo
```

### Ejercicio 16

*Dada una lista de números enteros, crea un algoritmo que calcule la media de la lista.*

**Paso 1**: Definir el problema

El usuario introduce una lista de números. Se calcula la media de estos números. La media será la suma de todos los números entre la cantidad de números introducida.

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ``numero``  ``cantidad`` ``suma``  ``media`` ``numerlista`` Introducir número uno a uno.

Proceso:

Se crea una lista con números. Se contabilizan y suman. Se calcula la media de dichos números.

Salida: Escribir ``media`` 

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo SumaPar
	#Entrada
	numerLista[]
	numero <- 0
	cantidad <- 0
	media <- 0
	suma <- 0
	i <- 0
	repetir:
		numero <- input()
		si user_input es un número entero:
			numerLista[i] <- numero
			i <- i+1
	hasta que numero no es un número entero
	#Proceso
	for num en numerLista[]:
		suma=suma+num
	cantidad=i
	media=suma/cantidad
	#Salida
	Escribir("La media de los números es de", media)
Fin Algoritmo
```

### Ejercicio 17

*Crea un algoritmo que genere un número aleatorio entre 1 y 100, y le pida al usuario adivinarlo. El
algoritmo deberá indicar si el número introducido es mayor o menor que el número aleatorio, hasta
que el usuario adivine el número correcto.*

**Paso 1**: Definir el problema

Crear un algoritmo que de un número aleatorio y un comparador entre el número escogido al azar y el número que da el usuario hasta que acierte. El número aleatorio será un valor entre 1 y 100 que el propio programa seleccionará. 

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: `nuser` ``nalea`` ``intento`` 

Proceso:

* Generar ``nalea`` y ``nuser`` . Generar ``intento`` para almacenar el número de intentos necesitados por el usuario para acertar el número.
* Comparar ``nuser`` y ``nalea``
* Dependiendo del resultado asignar a ``resultado`` "es más grande", "es más pequeño" o "¡Ese es!"

Salida: Escribir ``resultado``

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo NumAlea
	#Entrada
	nalea <- valor entre 1 y 100
	nuser <- 0
	intento <- 0
	#Proceso
	Repetir
		nuser <- Leer()
		intento <- intento+1
		si nuser>nalea
			Escribe ("Es más grande. Prueba de nuevo")
		si nuser<nalea
			Escribe ("Es más pequeño. Prueba de nuevo")
		si user=nalea
			resultado <- ("¡Ese es! ¡Lo adivinaste!")
	Hasta que resultado <- ("¡Ese es! ¡Lo adivinaste!")
	#Salida
	Escribir resultado + "Estos han sido tus intentos"+intentos
Fin Algoritmo
```

### Ejercicio 18

*Crea un algoritmo que determine si una cadena de texto es un anagrama de otra cadena de texto.*

**Paso 1**: Definir el problema, crea un algoritmo que determine si una cadena de texto es un anagrama de otra cadena de texto. Un anagrama se da cuando dos cadenas de texto cuentan con los mismos caracteres, aunque en distinto orden. Por ejemplo: Angela y Alegan.

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ``cadena1`` ``cadena2`` 

Proceso:

* Se cuenta el número de elementos de ``cadena1`` y el número de elementos de ``cadena2`` , asignándose estos valores a ``n`` y ``m`` , respectivamente.
* Si ``n`` y ``m`` son iguales:
  * Asignar a ``i`` el valor 0.
  * Se asigna a ``resultado`` el valor es ``anagrama`` .
    * Mientras ``i`` sea menor o igual que ``n-1`` :
      * Se asigna a ``NoEstaLetra`` el valor ``True`` .
      * Para ``j`` empezando en ``i`` hasta que sea igual que ``n-1`` :
        * Si ``cadena1[i]`` es igual a ``cadena2[j]`` entonces:
          * La posición ``j`` en la que está ``cadena1[i]`` se asigna a ``posición`` .
          * Se asigna a ``NoEstaLetra`` el valor ``False`` .
      * Si ``NoEstaLetra`` tiene valor ``True`` :
        * Se asigna a ``resultado`` el valor "no es anagrama".
        * Se asigna a ``i`` el valor ``n``. 
      * Sino:
        * Se asigna a ``temporal`` el elemento ``cadena2[i]`` .
        * Se asigna a ``cadena2[i]`` igual a ``cadena1[i]``.
        * Se asigna ``cadena2[posicion]`` igual a ``temporal``.
        * Se asigna a ``i`` el valor ``i+1``.

Salida: Escribir (``resultado``)

**Paso 3**: Escribir pseudocódigo

```
Algoritmo Anagrama
	#Entrada
	cadena1 <- Leer()
	cadena2 <- Leer()
	#Proceso
	n <- ContarElementosLista(cadena1)
	m <- ContarElementosLista(cadena2)
	Si n es igual a m
		i <- 0
		resultado <- "es anagrama"
		Mientras i sea menor o igual que n-1
			noEstaLetra <- True
			Para j=i Hasta n-1 con paso 1 Hacer
				Si cadena1[i] es igual a cadena2[j] Entonces
					posicion <- j
					noEstaLetra <- False
				FinSi
			FinPara
			Si noEstaLetra es igual a True Entonces
				resultado <- "no es anagrama"
				i <- n
			Sino
				temporal <- cadena2[i]
				cadena2[i] <- cadena1[i]
				cadena2[posicion] <- temporal
				i <- i+1
			FinSi
		FinMientras
	Sino
		resultado <- "no es anagrama"
	FinSi
	#Salida
	Escribir(resultado)
Fin Algoritmo
```

### Ejercicio 19

*Dada una lista de números enteros, crea un algoritmo que elimine los números duplicados de la
lista.*

**Paso 1**: Definir el problema

El usuario introduce una lista de números. Se añaden los números a otra lista siempre y cuando estos no se hayan repetido antes. De la lista de números que se introduce solo queremos quedarnos una vez con cada uno de ellos, por lo que nos debemos deshacer de aquellos repetidos. 

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ``numero`` ``numerLista`` ``nuevaLista`` . Introducir número uno a uno.

Proceso:

Se crea una lista con números. Se seleccionan los números a introducir en la segunda lista, sin repetir los ya existentes. Se lee uno a uno los números de la lista. Dichos números se comparan con los ya existentes en la nueva lista. Si, tras la comparación, el número no se encuentra en la nueva lista, se añade a esta. 

Salida: Escribir ``nuevalista`` 

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo SumaPar
	#Entrada
	numero <- 0
	numerLista[]
	nuevaLista[]
	i <- 0
	j <- 0
	repetir:
		numero <- input()
		si user_input es un número entero:
			numerLista[i] <- numero
			i <- i+1
		FinSi
	hasta que numero no es un número entero
	#Proceso
	Para num en numerLista[]:
		Si num no en nuevaLista[]:
			nuevaLista[j] <- num
			j <- j+1
		FinSi
	#Salida
	Escribir("La lista es", nuevaLista)
Fin Algoritmo
```

### Ejercicio 20

*Crea un algoritmo que determine si un número es capicúa o no.*

**Paso 1**: Definir el problema

El usuario introduce un número. Se calcula si el número es capicúa o no, es decir,si es igual de izquierda a derecha que al contrario. Ejemplo de números capicúa son: 234432, 121 y 22.

**Paso 2**: Poner la entrada, el proceso y la salida

Entrada: ``numero`` ``capicua`` .

Proceso:

Se introduce un número. Se verifica si el número es capicúa o no. Para ello se compara cada posición en la cadena de texto (recordar que al introducir el número el programa lo entiende como string) con la misma posición empezando por la cola. Por ejemplo: en un número de seis posiciones (seis dígitos) la posición 1 se compara con la 6, la 2 con la 5 y la 3 con la 4.  

Salida: Escribir resultado

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo Capicua
	#Entrada
	numero <- input()
	i <- 0
	capicua <- True
	#Proceso
	repetir
		Si numero[i] no es igual a numero[-i]
			capicua <- False
			i <- i+1
	hasta que i sea mayor a numero.length
	#Salida
	Si capicua es False
		Escribir("El número no es capicúa")
	Sino
		Escribir("El número es capicúa")
	FinSi
Fin Algoritmo
```
