## Enunciado del Ejercicio

### Objetivo: Explorar y comprender el uso del método .format() en Python para la interpolación de cadenas de texto (strings).

En este ejercicio, se utilizará una única plantilla de texto con espacios reservados ({}) para insertar de manera dinámica múltiples valores. A través del código, observarás cómo este método es capaz de procesar e imprimir automáticamente diferentes tipos de datos (números enteros, cadenas de texto y valores booleanos), además de manejar caracteres especiales como saltos de línea (\n) dentro de citas célebres. Finalmente, deberás resolver un pequeño reto práctico basado en lo aprendido.

Explicación del Código paso a paso
El script que has compartido es un excelente ejemplo de cómo Python maneja el formateo de texto de manera limpia y estructurada. Aquí tienes el desglose de lo que sucede en cada sección:

Definición de la plantilla: 
```python
formato = "{} {} {} {}"
```
Aquí se crea una variable llamada `formato` que contiene un *string* con cuatro llaves `{}`. Estas llaves actúan como "contenedores" vacíos. Al llamar al método `.format()` sobre esta variable, Python esperará recibir exactamente cuatro elementos para llenar esos espacios en orden de izquierda a derecha.

```python
print(formato.format(1,2,3,4))
print(formato.format("uno","dos","tres","cuatro"))
print(formato.format(True, False, False, True))
```

El método .format() es muy versátil; no importa si le pasas enteros (int), texto (str) o valores lógicos (bool). Internamente, Python convierte todos estos valores a cadenas de texto y los inserta en la plantilla.


### El manejo de errores (Línea comentada):

```python
#print(formato.format(1,2,3))
```

Esta línea está comentada por una buena razón: generaría un error. Como tu variable formato tiene cuatro llaves {}, requiere obligatoriamente al menos cuatro argumentos. Si le pasas solo tres, Python lanzará un IndexError: tuple index out of range.

## Ejercicios de Introducción a Python

### 1. Imprime los meses del año en una línea nueva cada vez usando .format().
Aquí tienes los enunciados adaptados para el entorno de Python. Como vimos anteriormente, Python no tiene una instrucción do-while, por lo que los ejercicios han sido reescritos para emplear el ciclo while (y el patrón while True: con break para simular el comportamiento deseado).
### 2. Crear el código de un programa en Python que pregunte si el usuario quiere salir del ciclo utilizando un ciclo infinito while True: (simulando la lógica de "hacer y luego evaluar"). 

El programa debe pedir una entrada de texto (string) donde el usuario tiene solo dos opciones para contestar. Si el usuario contesta "SI", entonces debe salir del ciclo usando la instrucción break; si contesta "NO", entonces debe volver a imprimir la pregunta: "¿Quieres salir del ciclo? [SI/NO]". Ojo: la contestación debe evaluarse estrictamente en mayúsculas.

### 3. Hacer un programa interactivo que muestre un menú de opciones para ejecutar las operaciones aritméticas básicas: suma (+), resta (-), multiplicación (*), división (/) y residuo (%). 

Deberá usar un ciclo while True: para mantener el menú activo. El programa leerá un carácter ingresado por el usuario y, con base en esa opción, ejecutará la operación correspondiente.

Los dos operandos deberán ser preguntados al usuario, convertidos a enteros usando int() y guardados en dos variables llamadas numero1 y numero2.

El resultado de la operación debe ser guardado en una variable llamada total y debe ser impreso en la consola.

Una vez que termine la operación, inicialice las variables numero1, numero2 y total en cero. El ciclo permitirá al usuario hacer la siguiente operación hasta que presione "s" para salir, momento en el cual un break terminará el programa.

### 4. Crear un programa en Python que "simule" las operaciones básicas de un cajero automático: retiro y consulta de saldo.

El proceso debe simular la validación de una tarjeta. Si la tarjeta es inválida, terminar el proceso usando la instrucción break. De lo contrario, usar un ciclo while para pedir un PIN, validando que el ingreso sea de exactamente 4 dígitos. El único PIN correcto será "1234"; de lo contrario, imprimirá "PIN inválido" y volverá a pedirlo.

Una vez autenticado, se entrará a un menú principal usando otro ciclo while. Las opciones serán: Retiro, Consulta y Salir.

El saldo inicial de la cuenta será de 3450.00. En la opción de retiro, deberá validar si la cantidad solicitada es mayor al saldo; si es así, desplegará "Fondos insuficientes". De tener fondos suficientes, se restará del saldo y se mostrará el saldo remanente.

Para la consulta, solo deberá mostrar el saldo actual.

Si el usuario selecciona salir, se usará break para terminar la ejecución del cajero.

### 5. Hacer un programa que simule un juego al estilo "Temple Run". El corredor siempre avanza por una pista infinita. 

El jugador comienza con tiempo = 12 unidades. Utiliza un ciclo while cuya condición sea que el tiempo sea mayor a 0 (es decir, el juego continúa mientras haya vida).

En cada iteración (paso) del ciclo, el corredor se enfrentará aleatoriamente a modificadores (puedes usar el módulo random de Python).

Obstáculos (Castigos): Generar un valor aleatorio True o False. Si es True (obstáculo grave), se restarán 3 unidades de tiempo al corredor. Si es False (obstáculo leve), solo se restará 1 unidad.

Premios: Generar un valor aleatorio True o False. Si es True (premio grande), se sumarán 3 unidades de tiempo al corredor. Si es False (premio pequeño), solo se sumará 1 unidad.

El ciclo se repetirá y el corredor continuará jugando. Cuando el tiempo alcance 0 o un número negativo, el ciclo while concluirá y se deberá imprimir que el juego ha terminado.
