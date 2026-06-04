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

##### Actuarios
###### 1. Parámetros fijos de una Tabla de Mortalidad:

"Para garantizar la integridad y auditoría de un modelo de valuación de seguros de vida, necesitas almacenar la 'Edad' y su 'Probabilidad de Muerte ($q_x$)' asociada. Usa una estructura de datos que proteja esta información como de 'solo lectura', garantizando que ningún otro proceso o programador pueda modificar accidentalmente la probabilidad durante la ejecución."

###### 2: Coordenadas de un escenario de estrés

"En las pruebas de solvencia del trimestre (Stress Testing), se define un escenario catastrófico estático compuesto por dos valores inamovibles: la Severidad (Costo) y la Frecuencia (Probabilidad). Guarda este escenario en una estructura inmutable y calcula la esperanza matemática del riesgo."

##### Ciencia de Datos

###### Coordenadas Geoespaciales

"Estás programando un algoritmo para optimizar rutas de entrega. Las coordenadas geográficas (Latitud y Longitud) del almacén matriz son el centro de gravedad de tu modelo y son fijas. Almacena este par de valores en una estructura de datos segura y protegida contra modificaciones accidentales."

###### Dimensiones de un Tensor (Shape)

"Al procesar un lote de imágenes médicas para una red neuronal, la matriz de píxeles exige una arquitectura estricta de cuatro dimensiones: (cantidad de imágenes, alto, ancho, canales de color). Define estas dimensiones (Shape) de forma estructurada para calcular el total de píxeles a procesar."

### Diccionarios (Dictionaries)

Los diccionarios almacenan información en pares de clave: valor (key: value). Son mutables y (desde Python 3.7) mantienen el orden de inserción. Las claves deben ser únicas e inmutables (como textos, números o tuplas), pero los valores pueden ser cualquier cosa. Son la base del formato JSON.

Cuándo usarlos: Cuando necesitas relacionar identificadores únicos con atributos (como una base de datos pequeña) y necesitas buscar información extremadamente rápido por su "nombre" o "ID" sin importar su posición.

#### Funciones más comunes:

* **keys():** Devuelve una vista con todas las claves.

* **values():** Devuelve una vista con todos los valores.

* **items():** Devuelve pares (clave, valor).

* **get(key, [default]):** Obtiene un valor sin dar error si la clave no existe.

**update(dict2):** Actualiza o añade múltiples pares desde otro diccionario.

##### Actuarios

###### Perfil de Póliza de un Cliente

"Para alimentar el motor automatizado de cotizaciones, necesitas empaquetar toda la información de un solicitante (ID de póliza, edad, estatus de fumador y suma asegurada) en un solo objeto donde cada dato sea consultable por su 'etiqueta' o 'nombre'. Además, debes programar una regla que consulte este perfil e incremente la prima base un 20% si el cliente es fumador."

###### Reservas Técnicas por Ramo

"El departamento de contabilidad te solicita un reporte de las reservas técnicas actuales. Crea una estructura que asocie el nombre de cada ramo (Auto, Vida, Gastos Médicos) con su monto en reservas. Acto seguido, la Comisión Nacional de Seguros aprueba la operación de un nuevo ramo ('Daños'), así que debes incorporarlo dinámicamente al portafolio existente."

##### Ciencia de Datos

##### Construcción rápida de un DataFrame

"Antes de importar librerías avanzadas como Pandas, necesitas simular la estructura tabular de una base de datos relacional. Crea un objeto que relacione los nombres de las columnas ('ID_Cliente', 'Ingreso', 'Abandono') con una lista de sus respectivos valores, construyendo así las bases de un DataFrame."

##### Conteo de Frecuencia de Palabras (NLP)

"En un proyecto de Análisis de Sentimiento (Procesamiento de Lenguaje Natural) para predecir movimientos de la bolsa, necesitas contar cuántas veces se repite cada palabra dentro del texto de una noticia financiera. Crea una estructura de 'clave-valor' que lea las palabras y vaya sumando 1 al contador de cada término de forma dinámica."

### Conjuntos (Sets)

Los conjuntos son colecciones desordenadas y no indexadas que NO permiten elementos duplicados. Están basados en la teoría matemática de conjuntos, lo que los hace increíblemente rápidos para verificar si un elemento existe dentro de ellos y para hacer cruces de información. Se definen con llaves {}.

Cuándo usarlos: Cuando te importa qué elementos tienes, pero no cuántos (eliminar duplicados) ni en qué orden están. Son perfectos para operaciones de intersección, unión y diferencia.

#### Funciones más comunes:

* **add(item):** Añade un elemento.

* **remove(item):** Elimina un elemento (da error si no existe; discard no da error).

* **union(set2) o |:** Une ambos conjuntos sin repetir.

* **intersection(set2) o &:** Devuelve elementos comunes en ambos.

* **difference(set2) o -:** Devuelve elementos en el primero que no están en el segundo.

##### Actuarios
 

##### Auditoría de Pólizas Duplicadas

"Durante la migración de un sistema legado, la base de datos arrojó un vector de IDs de pólizas facturadas con un grave problema: muchos clientes aparecen duplicados por un error del servidor. Demuestra cómo, utilizando una única línea de código basada en teoría de conjuntos, puedes purgar instantáneamente todos los duplicados para auditar únicamente las pólizas reales."

##### Cruce de Siniestralidad (Intersección)

"El departamento de prevención de fraudes te ha entregado dos listas de clientes: aquellos que reportaron un siniestro total en 2024 y los que lo hicieron en 2025. Utiliza operaciones matemáticas de conjuntos para encontrar de forma inmediata a los clientes reincidentes (la intersección) que deben ser sujetos a investigación."

##### Ciencia de Datos

###### Extracción de Categorías Únicas (Variables Categóricas)

"Estás preparando los datos para entrenar un modelo predictivo, y tienes una columna de texto que contiene las 'Ciudades' de los usuarios con miles de registros repetidos. Extrae exclusivamente el catálogo de 'clases únicas' de esa columna (sin repeticiones) para poder transformarlas posteriormente a variables binarias (One-Hot Encoding)."

###### Detección de Fuga de Datos (Data Leakage)

"Tienes dos conjuntos de IDs de pacientes: uno que usaste para 'entrenar' tu modelo y otro que reservaste celosamente para 'probarlo'. En Machine Learning, un paciente no puede estar en ambos grupos. Utiliza una operación de diferencia o intersección para comprobar rápidamente si tu muestra está contaminada (Fuga de Datos)."
