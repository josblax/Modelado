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

```python
# ---------------------------------------------------------
# Ejemplo 1: Registro dinámico de siniestros
# ---------------------------------------------------------
print("\n--- Ejercicio 1: Siniestros Automotrices ---")
# Generamos una lista inicial de 10 siniestros aleatorios (entre $5,000 y $50,000)
siniestros_mes = [round(random.uniform(5000, 50000), 2) for _ in range(10)]
print(f"1. Montos registrados al inicio del día: \n{siniestros_mes}")

# Llega un reporte en tiempo real (Generamos el monto aleatorio)
nuevo_reporte = round(random.uniform(5000, 50000), 2)
print(f"2. [ALERTA] Nuevo siniestro reportado en cabina: ${nuevo_reporte:,.2f}")

# Usamos append() para meterlo al final de la lista
siniestros_mes.append(nuevo_reporte)
```

###### Ejemplo 2: Proyección de tasas de interés

"El comité de inversiones ha proyectado las tasas de interés macroeconómicas para los próximos 5 años y las ha guardado en orden cronológico. Sin embargo, tras un sorpresivo anuncio del Banco Central, la proyección del año 3 debe ser ajustada a la baja. Escribe el código para actualizar específicamente ese valor manteniendo la estructura y el orden de los demás años."

```python
# ---------------------------------------------------------
# Ejemplo 2: Proyección de tasas de interés
# ---------------------------------------------------------
print("\n--- Ejercicio 2: Ajuste de Tasas ---")
# Generamos 5 años de tasas base (entre 4% y 8%)
tasas_proyectadas = [round(random.uniform(4.0, 8.0), 2) for _ in range(5)]
print(f"1. Proyección macroeconómica original (Años 1 a 5): \n{tasas_proyectadas}")

# Calculamos un ajuste aleatorio a la baja para el Año 3
baja_sorpresa = round(random.uniform(0.5, 1.5), 2)

# El "Año 3" corresponde al índice 2 de la lista (0, 1, 2)
# Reasignamos el valor modificando la lista original
tasas_proyectadas[2] = round(tasas_proyectadas[2] - baja_sorpresa, 2)

print(f"2. El Banco Central anunció una baja de {baja_sorpresa}% para el Año 3.")
print(f"3. Proyección actualizada conservando el orden cronológico: \n{tasas_proyectadas}")
```

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

```python
import random

print("--- TUPLAS: ACTUARÍA ---")
# 1. Parámetros fijos de una Tabla de Mortalidad
edad_simulada = random.randint(20, 80)
qx_simulado = round(random.uniform(0.001, 0.05), 5)

tabla_mortalidad_tupla = (edad_simulada, qx_simulado)
print(f"1. Datos Inmutables: Edad {tabla_mortalidad_tupla[0]}, Probabilidad de Muerte {tabla_mortalidad_tupla[1]}")
# Intentar reasignar tabla_mortalidad_tupla[1] = 0.5 daría un TypeError, lo cual asegura la auditoría.
```


###### 2: Coordenadas de un escenario de estrés

"En las pruebas de solvencia del trimestre (Stress Testing), se define un escenario catastrófico estático compuesto por dos valores inamovibles: la Severidad (Costo) y la Frecuencia (Probabilidad). Guarda este escenario en una estructura inmutable y calcula la esperanza matemática del riesgo."

```python
# 2. Coordenadas de un escenario de estrés
severidad = round(random.uniform(500000, 5000000), 2) # Costo entre 500k y 5M
frecuencia = round(random.uniform(0.01, 0.15), 4) # Probabilidad entre 1% y 15%

escenario_estres = (severidad, frecuencia)
esperanza_matematica = escenario_estres[0] * escenario_estres[1]
print(f"2. Escenario Estático: {escenario_estres} -> Esperanza del Riesgo: ${esperanza_matematica:,.2f}")
```

##### Ciencia de Datos

###### Coordenadas Geoespaciales

"Estás programando un algoritmo para optimizar rutas de entrega. Las coordenadas geográficas (Latitud y Longitud) del almacén matriz son el centro de gravedad de tu modelo y son fijas. Almacena este par de valores en una estructura de datos segura y protegida contra modificaciones accidentales."


```python
# 1. Coordenadas Geoespaciales
latitud = round(random.uniform(-90.0, 90.0), 6)
longitud = round(random.uniform(-180.0, 180.0), 6)

almacen_matriz = (latitud, longitud)
print(f"3. Coordenadas fijas del almacén: {almacen_matriz}")
```
###### Dimensiones de un Tensor (Shape)

"Al procesar un lote de imágenes médicas para una red neuronal, la matriz de píxeles exige una arquitectura estricta de cuatro dimensiones: (cantidad de imágenes, alto, ancho, canales de color). Define estas dimensiones (Shape) de forma estructurada para calcular el total de píxeles a procesar."

```python
# 2. Dimensiones de un Tensor (Shape)
lote_imagenes = random.randint(16, 128)
shape_tensor = (lote_imagenes, 256, 256, 3) # (imagenes, alto, ancho, canales RGB)

total_pixeles = shape_tensor[0] * shape_tensor[1] * shape_tensor[2] * shape_tensor[3]
print(f"4. Shape del Tensor: {shape_tensor} -> Total de píxeles a procesar: {total_pixeles:,}")
```

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

```python
# 1. Perfil de Póliza de un Cliente
perfil_cliente = {
    "ID_Poliza": f"POL-{random.randint(1000, 9999)}",
    "edad": random.randint(18, 70),
    "fumador": random.choice([True, False]),
    "suma_asegurada": random.choice([500000, 1000000, 2000000]),
    "prima_base": 5000.0
}

# Regla de recargo por tabaquismo
if perfil_cliente["fumador"]:
    perfil_cliente["prima_base"] *= 1.20 # Aumento del 20%
    
print(f"1. Perfil Cliente: {perfil_cliente['ID_Poliza']} | Fumador: {perfil_cliente['fumador']} | Prima Final: ${perfil_cliente['prima_base']:,.2f}")
```

###### Reservas Técnicas por Ramo

"El departamento de contabilidad te solicita un reporte de las reservas técnicas actuales. Crea una estructura que asocie el nombre de cada ramo (Auto, Vida, Gastos Médicos) con su monto en reservas. Acto seguido, la Comisión Nacional de Seguros aprueba la operación de un nuevo ramo ('Daños'), así que debes incorporarlo dinámicamente al portafolio existente."

```python
# 2. Reservas Técnicas por Ramo
reservas_tecnicas = {
    "Auto": round(random.uniform(1e6, 5e6), 2),
    "Vida": round(random.uniform(10e6, 50e6), 2),
    "Gastos Médicos": round(random.uniform(5e6, 15e6), 2)
}

# Incorporación dinámica del nuevo ramo
reservas_tecnicas["Daños"] = round(random.uniform(2e6, 8e6), 2)
print(f"2. Portafolio de Reservas Actualizado: {reservas_tecnicas}")
```

##### Ciencia de Datos

##### Construcción rápida de un DataFrame

"Antes de importar librerías avanzadas como Pandas, necesitas simular la estructura tabular de una base de datos relacional. Crea un objeto que relacione los nombres de las columnas ('ID_Cliente', 'Ingreso', 'Abandono') con una lista de sus respectivos valores, construyendo así las bases de un DataFrame."

```python
# 1. Construcción rápida de un DataFrame
n_registros = 5
dataframe_simulado = {
    "ID_Cliente": [f"USR-{random.randint(100, 999)}" for _ in range(n_registros)],
    "Ingreso": [round(random.uniform(15000, 80000), 2) for _ in range(n_registros)],
    "Abandono": [random.choice([0, 1]) for _ in range(n_registros)]
}
print(f"3. Base de datos simulada (Columnas): {dataframe_simulado.keys()}")
print(f"   Datos 'Ingreso': {dataframe_simulado['Ingreso']}")
```

##### Conteo de Frecuencia de Palabras (NLP)

"En un proyecto de Análisis de Sentimiento (Procesamiento de Lenguaje Natural) para predecir movimientos de la bolsa, necesitas contar cuántas veces se repite cada palabra dentro del texto de una noticia financiera. Crea una estructura de 'clave-valor' que lea las palabras y vaya sumando 1 al contador de cada término de forma dinámica."

```python
# 2. Conteo de Frecuencia de Palabras (NLP)
vocabulario = ["mercado", "acciones", "baja", "alza", "riesgo", "inversión", "tasa", "fed"]
# Simulamos un texto aleatorio de 30 palabras
noticia_financiera = [random.choice(vocabulario) for _ in range(30)]

frecuencia_palabras = {}
for palabra in noticia_financiera:
    # get(palabra, 0) devuelve 0 si la palabra no existe aún en el diccionario
    frecuencia_palabras[palabra] = frecuencia_palabras.get(palabra, 0) + 1

print(f"4. Frecuencia de palabras en el texto: {frecuencia_palabras}")
```

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

```python
# 1. Auditoría de Pólizas Duplicadas
# Generamos 20 IDs donde seguramente habrá repetidos (rango corto de 1 a 10)
ids_brutos = [random.randint(1, 10) for _ in range(20)] 

# Purgamos duplicados en una sola línea convirtiendo la lista a conjunto
ids_purgados = set(ids_brutos)
print(f"1. IDs Originales (Con duplicados): {len(ids_brutos)} -> IDs Auditados (Únicos): {len(ids_purgados)}")
```

##### Cruce de Siniestralidad (Intersección)

"El departamento de prevención de fraudes te ha entregado dos listas de clientes: aquellos que reportaron un siniestro total en 2024 y los que lo hicieron en 2025. Utiliza operaciones matemáticas de conjuntos para encontrar de forma inmediata a los clientes reincidentes (la intersección) que deben ser sujetos a investigación."

```python
# 2. Cruce de Siniestralidad (Intersección)
# Simulamos IDs de clientes que tuvieron siniestros (rango 100 a 200)
siniestros_2024 = set([random.randint(100, 200) for _ in range(30)])
siniestros_2025 = set([random.randint(150, 250) for _ in range(30)])

# Encontramos a los reincidentes usando la intersección
clientes_reincidentes = siniestros_2024.intersection(siniestros_2025)
print(f"2. Clientes investigados por reincidencia (Intersección): {clientes_reincidentes}")
```

##### Ciencia de Datos

###### Extracción de Categorías Únicas (Variables Categóricas)

"Estás preparando los datos para entrenar un modelo predictivo, y tienes una columna de texto que contiene las 'Ciudades' de los usuarios con miles de registros repetidos. Extrae exclusivamente el catálogo de 'clases únicas' de esa columna (sin repeticiones) para poder transformarlas posteriormente a variables binarias (One-Hot Encoding)."


```python
# 1. Extracción de Categorías Únicas (Variables Categóricas)
lista_ciudades = ["CDMX", "Monterrey", "Guadalajara", "Puebla", "Tijuana", "Mérida"]
# Simulamos 100 registros con muchas repeticiones
columna_ciudades_repetidas = [random.choice(lista_ciudades) for _ in range(100)]

# Extraemos el catálogo de clases únicas
catalogo_unico = set(columna_ciudades_repetidas)
print(f"3. De {len(columna_ciudades_repetidas)} registros, las clases únicas para One-Hot Encoding son: {catalogo_unico}")
```

###### Detección de Fuga de Datos (Data Leakage)

"Tienes dos conjuntos de IDs de pacientes: uno que usaste para 'entrenar' tu modelo y otro que reservaste celosamente para 'probarlo'. En Machine Learning, un paciente no puede estar en ambos grupos. Utiliza una operación de diferencia o intersección para comprobar rápidamente si tu muestra está contaminada (Fuga de Datos)."

```python
# 2. Detección de Fuga de Datos (Data Leakage)
# IDs del universo de pacientes: 1 al 100
# El Train set toma pacientes aleatorios del 1 al 80. El Test toma del 70 al 100 (habrá contaminación intencional).
train_set = set([random.randint(1, 80) for _ in range(50)])
test_set = set([random.randint(70, 100) for _ in range(20)])

# Comprobamos fuga de datos viendo si la intersección tiene algún elemento
fuga_datos = train_set.intersection(test_set)

if len(fuga_datos) > 0:
    print(f"4. ¡ALERTA! Fuga de datos detectada. Pacientes en ambos grupos: {fuga_datos}")
else:
    print("4. Modelo seguro: No hay fuga de datos (Intersección vacía).")
```

### PRACTICA #4 ACTUARIA

#### Tema 1: Listas (Manejo de Siniestros y Tasas)

##### Básico (Funciones): "Corte de Caja"

Tienes una lista con los montos de 5 siniestros reclamados hoy: [12000, 4500, 8900, 23000, 1500]. Utiliza las funciones nativas de Python para agregar un nuevo siniestro de 7500, calcular el costo total del día y encontrar cuál fue el siniestro más caro.

##### Intermedio (For / If): "Filtro de Jubilación"

Dada una lista con las edades de los asegurados de un portafolio de Vida: [34, 65, 23, 67, 45, 70, 29]. Utiliza un ciclo for y un condicional if para crear una nueva lista que contenga únicamente a las personas que ya alcanzaron la edad de jubilación (65 años o más) y cuenta cuántos son.

##### Intermedio (While): "Simulador de Capitalización"

Un cliente invierte $10,000 a una tasa de interés compuesto del 5% anual. Utiliza un ciclo while para calcular año con año cuánto dinero tiene acumulado, agregando cada nuevo saldo a una lista. El ciclo debe detenerse exactamente cuando el capital acumulado supere los $15,000.

#### Tema 2: Tuplas (Parámetros Fijos y Coordenadas)

###### Básico (Funciones/Desempaquetado): "Lectura de Póliza"

Tienes una tupla estática con los datos de una póliza: ("Auto", "Juan Perez", 25000). Extrae (desempaqueta) estos valores en tres variables individuales y utiliza una impresión formateada (f-string) para mostrar: "El cliente Juan Perez tiene un seguro de Auto con prima de $25,000".

##### Intermedio (For): "Esperanza de Mortalidad"

Recibes una lista de tuplas donde cada tupla tiene (Edad, Probabilidad de Muerte qx): [(40, 0.0012), (41, 0.0014), (42, 0.0017)]. Si tienes un grupo de 100,000 personas de cada edad, usa un ciclo for para calcular e imprimir cuántas muertes esperadas hay para cada edad.

##### Intermedio (For / If): "Alerta de Estrés Catastrófico"

Tienes un portafolio de escenarios de riesgo guardado en tuplas (Nombre, Severidad, Probabilidad): [("Inundacion", 500k, 0.05), ("Sismo", 2M, 0.01), ("Incendio", 100k, 0.1)]. Usa un ciclo para calcular la Pérdida Esperada (Severidad * Probabilidad) de cada uno. Usa un if para imprimir una ALERTA si la pérdida esperada de algún escenario supera los 15,000.

#### Tema 3: Diccionarios (Portafolios y Reservas)

###### Básico (Funciones): "Actualización de Tarifas"

Tienes un diccionario con las primas base: {"Auto": 5000, "Vida": 8000}. Un nuevo producto sale al mercado. Agrega al diccionario la llave "Gastos_Medicos" con valor 12000 y actualiza la prima de "Auto" a 5500 usando las funciones de diccionarios.

##### Intermedio (For / If): "Clasificación de Riesgo"

Tienes un diccionario con clientes y su índice de masa corporal (IMC): {"Ana": 22.5, "Luis": 31.0, "Carlos": 27.8}. Recorre el diccionario con un for. Si el IMC es mayor a 30, añade a la persona a una lista de "Riesgo Alto"; de lo contrario, añádela a "Riesgo Normal".

##### Intermedio (While): "Cobranza Mensual"

Tienes un diccionario de deudas: {"PolizaA": 1500, "PolizaB": 500}. El cliente realiza un pago mensual fijo de $500 que se reparte para liquidar primero la Póliza A y luego la B. Usa un ciclo while que reste $500 en cada iteración de la deuda total hasta que todas las pólizas estén en 0.

#### Tema 4: Conjuntos (Auditorías y Cruces)

##### Básico (Funciones): "Venta Cruzada (Cross-Selling)"

Tienes dos conjuntos con IDs de clientes. Seguros de Auto: {101, 102, 103}. Seguros de Vida: {103, 104, 105}. Usa operaciones de conjuntos para imprimir a los clientes que tienen AMBOS seguros y a los clientes que tienen AL MENOS un seguro.

##### Intermedio (For / Set): "Detección de Fraude por Frecuencia"

Tienes una lista de IDs de autos que han reportado siniestros este año: ["A1", "B2", "A1", "C3", "A1", "B2"]. Convierte la lista a un conjunto para obtener los autos únicos. Luego, usa un ciclo for sobre ese conjunto para contar cuántas veces aparece cada auto en la lista original, detectando al auto con más reportes.

##### Intermedio (If / Set): "Auditoría de Pagos"

Tienes un conjunto de clientes que deben_pagar = {"Juan", "Maria", "Pedro", "Ana"} y un conjunto que ya_pagaron = {"Pedro", "Juan"}. Usa operaciones de conjuntos e if para verificar si hay personas con pagos pendientes. Si la diferencia no está vacía, imprime los nombres de los morosos.

### PRACTICA 4 CIENCIA DE DATOS

#### Tema 1: Listas (Vectores y Preprocesamiento)

##### Básico (Funciones): "Normalización Min-Max (Paso 1)"

Tienes un vector de ingresos mensuales: [15000, 22000, 18000, 45000, 12000]. Utiliza las funciones nativas para encontrar el valor máximo y el mínimo de la lista, e imprímelos para preparar tu posterior normalización de datos.

##### Intermedio (For / If): "Limpieza de Datos (Imputación)"

Has extraído datos de una columna de edades, pero hay valores nulos representados como -1: [25, 30, -1, 22, -1, 40]. Usa un ciclo for y un if para calcular el promedio de las edades válidas (mayores a 0) y reemplaza los -1 con ese promedio.

##### Intermedio (While): "Descenso del Gradiente Simulado"

Tu modelo tiene un Error Cuadrático de 15.5. Sabes que en cada época (iteración) el error disminuye un 10%. Usa un ciclo while para calcular cuántas épocas (vueltas) necesita entrenar el modelo hasta que el error sea menor a 1.0. Guarda el error de cada época en una lista.

#### Tema 2: Tuplas (Tensores y Métricas)

##### Básico (Funciones): "Dimensiones de una Imagen RGB"

Las dimensiones de una imagen satelital están dadas en una tupla (Alto, Ancho, Canales): (1080, 1920, 3). Calcula el número total de píxeles (multiplicando los primeros dos valores) y formatea el texto indicando si es una imagen a color (Canales = 3) o escala de grises (Canales = 1).

##### Intermedio (For): "Cálculo de MSE (Mean Squared Error)"

Tienes una lista de tuplas que compara (Valor_Real, Valor_Predicho) por tu red neuronal: [(10, 12), (20, 18), (30, 31)]. Usa un ciclo for para recorrer la lista, calcular el error de cada par (Restar, elevar al cuadrado) y sumar todos para obtener el MSE total.

##### Intermedio (For / If): "Validación de Hiperparámetros"

El rango permitido para la tasa de aprendizaje (Learning Rate) es una tupla fija (0.001, 0.1). Tienes una lista de tasas a probar: [0.0005, 0.01, 0.5, 0.05]. Recorre la lista con un ciclo y usa if para imprimir cuáles valores son VÁLIDOS (dentro del rango de la tupla) y cuáles son INVÁLIDOS.

#### Tema 3: Diccionarios (DataFrames y Features)

##### Básico (Funciones): "Fusión de Datasets"

Tienes dos diccionarios con características (features) de un usuario. datos_demograficos = {"edad": 28, "pais": "MX"} y datos_actividad = {"clics": 150, "compras": 2}. Únelos en un solo diccionario llamado perfil_usuario usando métodos de diccionarios.

##### Intermedio (For / If): "Bolsa de Palabras (Stop-words)"

Tienes un diccionario con la frecuencia de palabras de un tweet: {"el": 4, "modelo": 1, "de": 3, "IA": 2}. Usa un ciclo para crear un nuevo diccionario que elimine las "stop words", es decir, mantén solo las palabras que tengan más de 3 letras o cuya frecuencia sea menor a 3.

##### Intermedio (For Anidado): "Promedio de Columnas (Pandas Manual)"

Tienes un diccionario que simula un DataFrame tabular: {"Ingreso": [10, 20, 30], "Edad": [20, 25, 30]}. Usa un ciclo for que recorra las llaves (columnas) y, por cada una, calcule e imprima el promedio de los valores de su respectiva lista.

#### Tema 4: Conjuntos (Clases y Fugas de Datos)

##### Básico (Funciones): "Extracción de Clases (Labels)"

Tienes el vector de predicciones de un modelo de clasificación de flores: ["Setosa", "Versicolor", "Setosa", "Virginica", "Versicolor"]. Conviértelo en un conjunto para saber exactamente cuántas y cuáles son las clases únicas (labels) con las que está trabajando el modelo.

##### Intermedio (If / Set): "Alerta de Data Leakage"

Tienes el conjunto de datos con los que entrenaste el modelo ids_train = {1, 2, 3, 4, 5} y los datos para probarlo ids_test = {4, 5, 6, 7}. Usa una operación de conjuntos para encontrar la intersección. Si el resultado no está vacío, usa un if para imprimir un mensaje de "ERROR CRÍTICO: FUGA DE DATOS DETECTADA".

##### Intermedio (For / Set): "Coeficiente de Similitud de Jaccard"

Tienes los resultados de dos sistemas de recomendación. modelo_A = {"Item1", "Item2", "Item3"} y modelo_B = {"Item2", "Item3", "Item4"}. Calcula el índice de Jaccard, que es el número de elementos en la Intersección dividido por el número de elementos en la Unión de ambos conjuntos.
