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
