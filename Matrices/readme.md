# Guía Didáctica: El motor de NumPy - La clase `ndarray`

## 1. ¿Qué es un `ndarray`?
En NumPy, la palabra **`ndarray`** es la abreviatura de **"N-dimensional array"** (Arreglo N-dimensional). Es el corazón de la librería y la estructura de datos fundamental sobre la cual ocurren todas las matemáticas avanzadas en Python.

Puedes imaginar un `ndarray` como una cuadrícula o contenedor matemático donde **todos los elementos deben ser exactamente del mismo tipo** (generalmente enteros o flotantes).

### Niveles de Dimensión (N-dimensional):
1. **1D (Una dimensión):** Se comporta como una lista simple de números en una línea. En matemáticas, a esto se le conoce como un **Vector**.
2. **2D (Dos dimensiones):** Se comporta como una hoja de cálculo (tipo Excel) que tiene filas y columnas. A esto se le llama **Matriz**.
3. **3D o más:** Se comporta como un cubo compuesto por cuadrículas apiladas. A esto se le conoce genéricamente como un **Tensor**.

---

## 2. ¿Por qué usar `ndarray` en Actuaría y Ciencia de Datos?

* **Desempeño y Velocidad:** Mientras que una lista normal de Python puede guardar diferentes tipos de datos mezclados, el `ndarray` exige uniformidad. Esto permite a la computadora almacenar la información de forma ultra-compacta en la memoria y realizar cálculos casi al instante.
* **Vectorización:** Permite aplicar fórmulas matemáticas a millones de datos al mismo tiempo sin tener que escribir lentos ciclos `for`. Ejemplo: `matriz * 2` multiplica todos los elementos de golpe.

---

## 3. Funciones Principales de la Clase `ndarray`

A continuación, se presentan las 4 categorías más importantes de métodos que usarás en el día a día para manipular estos arreglos.

### Preparación del entorno
```python
import numpy as np

# Creamos una matriz (2D) de prueba para nuestros ejemplos
matriz = np.array([[1, 5, 3], 
                   [4, 2, 6]])
```

### Categoría A: Funciones de Forma y Manipulación
Alteran la estructura del contenedor (la "cuadrícula") sin cambiar los datos en sí.

* **`reshape()`**: Reorganiza las dimensiones del arreglo.
  ```python
  # Cambia de una matriz 2x3 a una matriz 3x2
  nueva_forma = matriz.reshape(3, 2)
  print(nueva_forma)
  # Resultado:
  # [[1 5]
  #  [3 4]
  #  [2 6]]
  ```

* **`flatten()`**: "Aplasta" cualquier matriz de múltiples dimensiones en un vector 1D.
  ```python
  plano = matriz.flatten()
  print(plano)
  # Resultado: [1 5 3 4 2 6]
  ```

* **`transpose()` o `.T`**: Transpone la matriz (convierte filas en columnas). Vital en álgebra lineal.
  ```python
  transpuesta = matriz.T
  print(transpuesta)
  # Resultado:
  # [[1 4]
  #  [5 2]
  #  [3 6]]
  ```

### Categoría B: Funciones Matemáticas y Estadísticas
Permiten hacer cálculos descriptivos sobre miles de celdas. Puedes usar el parámetro `axis` para calcular por filas o columnas.

* **Suma, Promedio y Desviación Estándar:**
  ```python
  print(matriz.sum())       # 21 (Suma todo)
  print(matriz.mean())      # 3.5 (Promedio general)
  
  # Uso de 'axis' (ejes)
  print(matriz.sum(axis=1)) # [ 9 12] (Suma de cada fila)
  print(matriz.sum(axis=0)) # [ 5  7  9] (Suma de cada columna)
  ```

* **Mínimos y Máximos:**
  ```python
  print(matriz.max())       # 6
  print(matriz.min())       # 1
  ```

### Categoría C: Funciones de Búsqueda y Ordenamiento
Para explorar datos y encontrar la ubicación de valores clave (esencial para identificar escenarios de mayor riesgo).

* **`sort()`**: Ordena los elementos del arreglo.
  ```python
  # Ordena los elementos de cada fila de menor a mayor
  matriz_ordenada = matriz.copy()
  matriz_ordenada.sort(axis=1)
  print(matriz_ordenada)
  # Resultado:
  # [[1 3 5]
  #  [2 4 6]]
  ```

* **`argmax()` y `argmin()`**: Devuelven la **posición (índice)** del valor máximo o mínimo, no el valor en sí.
  ```python
  arr_1d = np.array([10, 50, 20, 90, 30])
  print(arr_1d.argmax()) 
  # Resultado: 3 (Porque el 90 está en el índice 3)
  ```

### Categoría D: Funciones de Transformación de Tipo
* **`astype()`**: Fuerza a que todos los elementos cambien a un tipo de dato específico (ej. float a int).
  ```python
  arr_decimal = np.array([1.1, 2.8, 3.5])
  
  # Convertimos los flotantes a enteros (trunca los decimales)
  arr_entero = arr_decimal.astype(int)
  print(arr_entero)
  # Resultado: [1 2 3]


Operaciones Vectoriales y Álgebra Lineal con NumPy

El presente documento expone los fundamentos prácticos del álgebra lineal utilizando la librería NumPy en el lenguaje Python. Se analizan las operaciones vectoriales elementales mediante el uso de la estructura de datos `ndarray`.

A continuación, se detalla el análisis del siguiente bloque de código:

```python
import numpy as np
from numpy.linalg import norm

# 1. Creación de vectores tridimensionales
v1 = np.array([1., 2., 3.])
v2 = np.array([2, 0, 1.])

# 2. Multiplicación y división por un escalar
print(2 * v1)  # array([2., 4., 6.])
print(v1 / 2)  # array([0.5, 1., 1.5])

# 3. Combinaciones lineales
print(3 * v1)           # array([ 3., 6., 9.])
print(3 * v1 + 2 * v2)  # array([ 7., 6., 11.])

# 4. Norma del vector (Magnitud)
print(norm(v1))         # 3.7416573867739413

# 5. Producto punto (Producto escalar)
print(np.dot(v1, v2))   # 5.0
print(v1 @ v2)          # 5.0 ; formulación alternativa moderna
```

## Análisis Estructural y Matemático

### 1. Creación de Vectores
La función `np.array()` inicializa un contenedor multidimensional (`ndarray`). En este escenario unidimensional con tres componentes, representa un vector en el espacio euclidiano tridimensional ($\mathbb{R}^3$), compuesto por ejes coordenados $X, Y, Z$.

### 2. Multiplicación Escalar y Vectorización
Al ejecutar `2 * v1`, se efectúa una multiplicación por un escalar. NumPy emplea un proceso denominado **Vectorización**, el cual aplica la operación aritmética a cada elemento del arreglo de manera individual, eximiendo al programador de estructurar ciclos iterativos (`for`). Geométricamente, esta operación representa la dilatación (o contracción) de la magnitud del vector sin alterar su dirección subyacente.

### 3. Combinaciones Lineales
La expresión `3 * v1 + 2 * v2` representa una combinación lineal, calculada mediante la suma elemento por elemento tras el escalamiento previo. Esta operación es la base matemática para la estructuración de portafolios financieros en la disciplina actuarial, donde cada vector representa los retornos de un activo y los escalares representan la ponderación del capital invertido.

### 4. Norma Vectorial
Importada desde el submódulo `numpy.linalg`, la función `norm()` calcula la norma Euclidiana (o norma $L^2$) del vector. Corresponde a la longitud física del mismo en el espacio, calculada mediante el Teorema de Pitágoras generalizado: $\sqrt{x^2 + y^2 + z^2}$.

### 5. Producto Punto (Operador `@`)
El producto punto (o producto escalar) multiplica las componentes homólogas de ambos vectores y suma los resultados algebraicos: $(1 	imes 2) + (2 	imes 0) + (3 	imes 1) = 5$. 
Es imperativo destacar la introducción del operador `@` (disponible desde Python 3.5), diseñado específicamente para la multiplicación de matrices y cálculo de productos punto. Su uso es considerado el estándar actual frente a `np.dot()` por cuestiones de legibilidad.

---

## Puntos Clave para el Aprendizaje

1. **Principio de Vectorización:** Las operaciones aritméticas (`+`, `-`, `*`, `/`) que involucran un `ndarray` y un escalar, o dos `ndarray` de idéntica dimensión, se ejecutan invariablemente elemento por elemento. 
2. **Uso del submódulo `numpy.linalg`:** Se recomienda su adopción sistemática, dado que provee los algoritmos optimizados para operaciones complejas de álgebra lineal (cálculo de normas, determinantes, eigenvalores e inversión matricial).
3. **Preferencia Sintáctica:** El empleo del operador `@` debe priorizarse sobre funciones tradicionales al efectuar multiplicaciones matriciales, para mantener el rigor y la claridad matemática en el código fuente.


___


## Funciones Trigonométricas en Vectores (NumPy)

En NumPy, las funciones trigonométricas se aplican de forma vectorizada. Esto significa que si le pasas un vector con 1,000 ángulos, NumPy calculará el seno de los 1,000 ángulos al mismo tiempo en una fracción de segundo.

### 1. El Catálogo de Funciones Trigonométricas

Todas estas funciones operan elemento por elemento (element-wise) sobre un ndarray:

Funciones Directas (Esperan Radianes)

* np.sin(vector): Calcula el Seno de cada elemento.

* np.cos(vector): Calcula el Coseno de cada elemento.

* np.tan(vector): Calcula la Tangente de cada elemento.

### Funciones Inversas (Devuelven Radianes)

* np.arcsin(vector): Calcula el Arcoseno.

* np.arccos(vector): Calcula el Arcocoseno.

* np.arctan(vector): Calcula la Arcotangente.

### Funciones de Conversión

* np.deg2rad(vector): Convierte un vector de Grados a Radianes.

* np.rad2deg(vector): Convierte un vector de Radianes a Grados.

* np.pi: Constante matemática de Pi ($\pi \approx 3.14159...$).


### Ejemplo Práctico: Generación de Señales (Ondas)

Muy útil en Mecatrónica, Videojuegos (movimientos oscilatorios) o Series de Tiempo Financieras para modelar estacionalidad (ej. ventas que suben en diciembre y bajan en enero).



### La Aplicación Estrella en Ciencia de Datos: "Similitud del Coseno"

¿Cómo sabe el algoritmo de Netflix que te gusta una película? ¿Cómo sabe ChatGPT qué palabras se relacionan? Utilizan vectores y la función trigonométrica del Coseno.

En álgebra lineal, el producto punto de dos vectores se define con trigonometría:
$$ \vec{A} \cdot \vec{B} = |\vec{A}| |\vec{B}| \cos(\theta) $$

Si despejamos el ángulo ($\theta$), podemos usar np.arccos() para saber qué tan separados están dos vectores en el espacio. En Inteligencia Artificial, si el ángulo entre el vector del "Cliente A" y el "Cliente B" es muy cerrado (cercano a 0 grados), significa que sus gustos o riesgos son casi idénticos.
