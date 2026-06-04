# Estructuras de Datos en Python

## En Python, la forma en que agrupamos y almacenamos nuestros datos define qué tan rápido y eficiente será nuestro código. Las cuatro estructuras principales (conocidas como colecciones) son: Listas, Tuplas, Diccionarios y Conjuntos.

Cuándo usarlas: Cuando tienes una colección de elementos que necesitas recorrer secuencialmente, modificar, agregar o eliminar elementos sobre la marcha.

### 1. Listas (Lists)
Las listas son secuencias ordenadas y mutables (modificables). Pueden contener diferentes tipos de datos e incluso listas dentro de listas (anidadas). Al tener un orden específico, cada elemento tiene un índice asignado empezando por el 0.

#### Funciones más comunes:

* **append(item):** Añade un elemento al final.

* **extend(iterable):** Añade múltiples elementos al final.

* **insert(index, item):** Inserta un elemento en una posición específica.

* **pop([index]):** Elimina y devuelve el elemento en el índice dado (o el último si no se especifica).

* **remove(item):** Elimina la primera aparición del elemento.

* **sort():** Ordena la lista (modifica la original).

* **len(lista):** Devuelve la cantidad de elementos.


#### Ejercicios

##### Actuarios

###### Ejemplo 1: Registro dinámico de siniestros

"Eres el actuario responsable del ramo de automóviles. A lo largo del mes, la cabina de atención te reporta siniestros de forma secuencial. Crea un programa que registre estos montos iniciales, permita agregar un nuevo reporte que acaba de llegar en tiempo real y, finalmente, calcule la suma del costo total de indemnizaciones del mes."

###### Ejemplo 2: Proyección de tasas de interés

"El comité de inversiones ha proyectado las tasas de interés macroeconómicas para los próximos 5 años y las ha guardado en orden cronológico. Sin embargo, tras un sorpresivo anuncio del Banco Central, la proyección del año 3 debe ser ajustada a la baja. Escribe el código para actualizar específicamente ese valor manteniendo la estructura y el orden de los demás años."

##### Ciencia de Datos

###### Ejemplo 1: Limpieza de una columna de datos (Feature Engineering)

"Como científico de datos, recibes de ingeniería de datos una columna con las edades de los usuarios. Lamentablemente, los datos están 'sucios': mezclan edades en texto con frases como 'No disponible'. Utiliza una estructura dinámica para extraer y convertir únicamente los valores numéricos, construyendo un vector de datos limpio y listo para el modelo."

###### Ejemplo 2: Almacenamiento de la función de pérdida (Loss Function)

"Durante el entrenamiento de tu modelo de Machine Learning, necesitas monitorear si la inteligencia artificial realmente está aprendiendo. Crea un historial que almacene el error de predicción de cada iteración (época). Al finalizar una nueva iteración, añade el nuevo error y verifica mediante código si este último resultado fue mejor (menor) que el anterior."

### Tuplas (Tuples)
Las tuplas son secuencias ordenadas pero inmutables (no se pueden modificar después de crearse). Se definen con paréntesis (). Al ser inmutables, son más seguras y ligeramente más rápidas que las listas en términos de memoria y procesamiento.

Cuándo usarlas: Para proteger datos que "no deben cambiar" bajo ninguna circunstancia (constantes, configuraciones, coordenadas) o para devolver múltiples valores desde una función.

Funciones más comunes:
(Son muy pocas debido a su inmutabilidad)

* **count(item):** Cuenta cuántas veces aparece un elemento.

**index(item):** Devuelve el índice de la primera aparición del elemento.

**len(tupla):** Tamaño de la tupla.
