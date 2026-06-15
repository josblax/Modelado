# Funciones en Python

* Las funciones son piezas de código reusable.

* Las funciones pueden ser llamadas o invocadas cuando son necesitadas.

* Ayuda a desglosar un problema en partes más manejables.

## Estructura General de una función.

### La estructura general de una función en Python implica el uso de la palabra reservada def y la indentación (sangría) para delimitar el bloque de código:

### Palabra reservada def: Le indica a Python que estás creando una función.


* **Nombre de la función:** Un identificador único.

* **Lista de parámetros:** Variables entre paréntesis separadas por comas (puede estar vacía).

* **Cuerpo de la función:** El bloque de código indentado que define lo que hace.

* **Retorno (opcional):** La instrucción return para devolver un valor (si no se usa, Python devuelve None por defecto).

Estructura General de una función:

```Python
def nombrefuncion(parametro1, parametro2):
    # Cuerpo de la función indentado
    pass
```

**Ejemplo:**

```Python
def suma(num1, num2):
    return num1 + num2

```
### ¿Cómo se llama a una Función? 

Una función puede ser llamada dentro de cualquier otra parte del código y si esta tiene parámetros, debes anexar los valores (argumentos) que reciba la función separados por comas ,.

### ¿Se puede definir una Función dentro de otra Función? 

Sí, a diferencia de C++, en Python sí puedes definir una función dentro de otra función (conocidas como funciones anidadas). Esto es muy útil para ocultar lógica interna o crear "closures". 

> Python también soporta funciones anónimas utilizando la palabra reservada lambda.

Ejemplos de diferentes tipos de funciones.
El ejercicio de hoy implica una serie de ejemplos que muestran algunas de las características de las funciones en Python.

### RECUERDA. Un parámetro es la variable definida dentro de los paréntesis al crear la función.

### Por el contrario, un argumento es el valor real que se le envía a la función cuando esta es llamada.

##  1. Función sin retorno y sin parámetros.

Esta es la estructura más básica. La función ejecutará una acción directa (como imprimir en pantalla), pero no devolverá ningún valor al programa principal (devuelve None por debajo). Al tener los paréntesis vacíos (), tampoco recibe "ingredientes" externos; toda su información es interna.
​
Ejemplo (Imprimir una suma fija internamente):

```Python
# Declaración de función sin retorno explícito y sin parámetros ()
def imprimir_suma_fija():
    # La función define sus propios datos internamente
    a = 8
    b = 12
    suma = a + b
    
    # Ejecuta la acción y termina
    print(f"La suma calculada internamente es: {suma}")

# Bloque principal
if __name__ == "__main__":
    # Al llamarla, simplemente ejecuta su bloque de código encapsulado
    imprimir_suma_fija()
    
    # Podemos llamarla varias veces, pero siempre hará exactamente lo mismo
    imprimir_suma_fija()
```

## 2. Funciones sin retorno y con parámetros
Aquí seguimos ejecutando una acción sin devolver un resultado para operaciones matemáticas, pero ahora los paréntesis contienen "ingredientes" (parámetros). Esto hace que la función sea dinámica.
​
Ejemplo (Imprimir la suma de dos números):

```Python
# Declaración de función que exige dos parámetros
def imprimir_suma(a, b):
    suma = a + b
    print(f"La suma calculada internamente es: {suma}")

if __name__ == "__main__":
    # Llamamos a la función inyectándole los "ingredientes" (5 y 10)
    imprimir_suma(5, 10)
    
    # Podemos reutilizarla con datos distintos
    imprimir_suma(100, 250)

```

## 3. Funciones con retorno y sin parámetros
​
Aquí utilizamos explícitamente la instrucción return. Esto significa que la función trabaja como una "calculadora" que promete entregarnos un dato. Al no tener parámetros, busca la información internamente y nos entrega un resultado limpio.

``` Python
# Declaración de función que devuelve un valor pero no pide parámetros ()
def obtener_suma_fija():
    valor1 = 20
    valor2 = 30
    
    # El return procesa internamente y devuelve el resultado
    return valor1 + valor2

if __name__ == "__main__":
    # La función no imprime nada por sí sola, debemos atrapar su valor en una variable
    resultado = obtener_suma_fija()
    
    print(f"El valor retornado por la función es: {resultado}")
```

## 4. Función con retorno y con parámetros.

Este es el estándar de oro en el diseño de algoritmos modulares. Inyectamos datos externos, la función realiza el cálculo a puerta cerrada y nos entrega un resultado usando return.

### Ejemplo (Calcular y devolver la suma de datos inyectados):

```Python
# Declaración con retorno explícito y con parámetros
def calcular_suma(a, b):
    # Procesa los "ingredientes" recibidos y devuelve el resultado matemático
    return a + b

if __name__ == "__main__":
    # Inyectamos los valores 15 y 25. 
    # Debemos atrapar el resultado en una nueva variable.
    resultado_total = calcular_suma(15, 25)
    
    # Ahora podemos usar ese dato en el flujo principal
    print(f"El resultado procesado y devuelto es: {resultado_total}")
    
    # También podemos imprimir el retorno directamente sin guardarlo
    print(f"Otra suma rápida es: {calcular_suma(50, 50)}")
```
___

# Práctica #5: Laboratorio de Funciones en Python (Actuaría)

## I. Funciones sin retorno y sin parámetros def nombre():

### Ejercicio 1: Inicializador de Tablas de Mortalidad

Enunciado: Antes de calcular primas de seguros de vida, es necesario cargar las bases biométricas. Escribe una función llamada inicializar_tabla_mortalidad que simule este proceso imprimiendo en consola: "[Sistema] Tabla de mortalidad CNSF cargada exitosamente en memoria."


### Ejercicio 2: Alerta de Auditoría

Enunciado: En la gestión de riesgos, a veces se detienen los procesos para revisión. Diseña una función alerta_auditoria que no reciba parámetros, pero al llamarse imprima: "Cálculo suspendido: Los modelos de reservas requieren validación por el actuario responsable".


### Ejercicio 3: Menú de Ramos de Seguro

Enunciado: Crea una función mostrar_menu_ramos para el cotizador de una aseguradora. Debe imprimir el siguiente texto estructurado: "--- COTIZADOR ACTUARIAL ---" seguido de "1. Vida | 2. Gastos Médicos Mayores | 3. Daños".

## II. Funciones sin retorno y con parámetros def nombre(parametros):

### Ejercicio 4: Emisión de Póliza

Enunciado: Escribe una función emitir_poliza que reciba dos parámetros numéricos: la suma_asegurada y la prima_emitida. La función debe imprimir un resumen del contrato: "Póliza emitida. Suma Asegurada: $[suma], Prima a pagar: $[prima]".


### Ejercicio 5: Notificación de Siniestro

Enunciado: Diseña una función notificar_siniestro que reciba una cadena de texto (string) con el tipo de evento (ej. "Colisión", "Inundación"). Debe imprimir en pantalla: "Alerta de Reserva: Se ha reportado un siniestro de tipo [Evento]".


### Ejercicio 6: Ajuste de Inflación Visual

Enunciado: Crea una función mostrar_tasa_inflacion que reciba un número decimal pequeño (ej. 0.045). La función debe transformar ese número multiplicándolo por 100 e imprimir el aviso: "[Economía] La tasa de inflación proyectada es del [Valor]%".

## III. Funciones con retorno y sin parámetros def nombre(): return

### Ejercicio 7: Tasa Libre de Riesgo

Enunciado: Todo modelo financiero requiere una tasa base. Crea una función obtener_tasa_libre_riesgo que retorne estrictamente el valor decimal 0.05 (representando un 5% de los CETES). Atrapa el retorno en el flujo principal e imprímelo.

### Ejercicio 8: Simulación de Probabilidad de Muerte (qx)

Enunciado: En modelos estocásticos, las probabilidades fluctúan. Diseña una función simular_probabilidad_fallecimiento que no reciba parámetros, pero retorne un número fraccionario aleatorio entre 0.001 y 0.01. Atrapa el valor en el programa e imprímelo.

### Ejercicio 9: Edad de Jubilación Legal

Enunciado: Para calcular reservas de pensiones, se utiliza una edad de corte. Escribe una función obtener_edad_jubilacion que devuelva el número entero 65. Captura este valor y utilízalo en un print indicando que el cálculo de rentas vitalicias iniciará a esa edad.

## IV. Funciones con retorno y con parámetros def nombre(parametros): return

### Ejercicio 10: Prima Pura de Riesgo

Enunciado: La fórmula básica del seguro es multiplicar la frecuencia por la severidad. Crea una función calcular_prima_pura que reciba la frecuencia (probabilidad de que ocurra el siniestro) y la severidad (costo promedio del siniestro). Multiplícalos y retorna el resultado para mostrarlo en el programa principal.

### Ejercicio 11: Valor Presente Simple

Enunciado: Escribe una función calcular_valor_presente que reciba un monto_futuro y una tasa_descuento. Aplica la fórmula monto_futuro / (1 + tasa_descuento) para traer el dinero a valor actual por un periodo. Retorna el resultado redondeado a 2 decimales.

### Ejercicio 12: Indemnización con Deducible (Clamp)

Enunciado: Diseña una función calcular_indemnizacion que reciba el daño_evaluado de un siniestro y el deducible contratado por el cliente. Resta el deducible al daño. Usa un condicional (if) para asegurar que, si el deducible es mayor al daño, la indemnización no sea negativa, sino que retorne 0.
___

# Practica #5 Ciencia de Datos (Data Science)

## I. Funciones sin retorno y sin parámetros def nombre():

### Ejercicio 1: Inicializador del Entorno de Datos
Enunciado: Simular la carga automática de una configuración de entorno para análisis de datos. La función imprimirá en consola que el set de datos por defecto (ej. Dataset Iris) ha sido montado en la memoria caché local.


### Ejercicio 2: Limpiar Historial de Logs
Enunciado: Diseña una función encargada de simular la liberación de memoria RAM tras un entrenamiento pesado. Al llamarse debe imprimir en pantalla: "Los registros temporales y logs de entrenamiento han sido removidos para liberar memoria RAM".


### Ejercicio 3: Menú de Modelos Predictivos
Enunciado: Diseña una función para una interfaz de terminal científica que muestre los algoritmos disponibles para ejecutar: "1. Regresión Lineal | 2. Árbol de Decisión | 3. Random Forest".

## II. Funciones sin retorno y con parámetros def nombre(p1, p2):

### Ejercicio 4: Inspección de Dimensiones (Shape)
Enunciado: Escribe una función que reciba dos parámetros enteros: filas y columnas. Debe imprimir las dimensiones tabulares de la matriz de datos que se va a procesar.

### Ejercicio 5: Registro de Métrica de Evaluación
Enunciado: Cuando se evalúa un modelo de Inteligencia Artificial, se escoge una métrica. Diseña una función que reciba una cadena de texto con el nombre de la métrica (ej. "Accuracy" o "MSE") e imprima: "¡Evaluación finalizada! La métrica seleccionada para el modelo es: [Métrica]".

### Ejercicio 6: Ajustar Tasa de Aprendizaje (Learning Rate)
Enunciado: Escribe una función que reciba un número decimal pequeño (entre 0.0001 y 1.0) que represente la velocidad de aprendizaje de un algoritmo. La función debe multiplicar el valor por 100 para imprimirlo como porcentaje en consola.

## III. Funciones con retorno y sin parámetros def nombre(): return valor

### Ejercicio 7: Generador de Ruido Estocástico (Data Augmentation)
Enunciado: Para hacer que un modelo sea robusto se le inyecta ruido matemático. Diseña una función que no reciba parámetros pero retorne un número decimal pequeño aleatorio que simule el sesgo térmico o ruido de una muestra.

### Ejercicio 8: Umbral de Clasificación por Defecto (Threshold)
Enunciado: En problemas de clasificación binaria (ej. determinar si un correo es Spam o No), el límite de decisión por defecto suele ser 0.5. Crea una función que retorne este valor estático para ser usado en las condiciones del programa principal.


### Ejercicio 9: Sincronización de Épocas (Epochs)
Enunciado: Escribe una función que simule leer el progreso del entrenamiento de una red neuronal y devuelva el número entero 100 (indicando que llegó a la época 100). Captura el valor e imprímelo.

## IV. Funciones con retorno y con parámetros def nombre(p1): return valor

### Ejercicio 10: Normalización Min-Max Escalada
Enunciado: Escribe una función que reciba el valor numérico actual de un dato, el valor mínimo de la columna y el valor máximo de la misma. Aplica la fórmula: (valor - minimo) / (maximo - minimo) y retorna el valor transformado a escala entre 0 y 1.

### Ejercicio 11: Error Absoluto Elemental (MAE)
Enunciado: La distancia entre la predicción de la computadora y el valor real mide el error. Diseña una función que reciba la prediccion (float) y el valor_real (float), calcule la resta y devuelva el resultado en valor absoluto absoluto usando la función nativa de Python abs().


### Ejercicio 12: Control de Valores Atípicos (Clip/Tratamiento de Outliers)
Enunciado: Los valores extremos dañan los análisis estadísticos. Diseña una función que reciba el valor de un sueldo, un limite_inferior y un limite_superior. Si el sueldo es menor al inferior, se iguala al inferior; si supera al superior, se reduce al superior. Retorna el valor corregido.

___

