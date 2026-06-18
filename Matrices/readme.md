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


### Aplicaciones Trigonométricas en Actuaría

Aunque la trigonometría nace de la geometría de los triángulos, en el Modelado Actuarial moderno se utiliza para analizar ciclos (tiempo) y direcciones de riesgo (espacio vectorial).

A continuación, analizaremos las dos aplicaciones principales en la industria aseguradora y financiera.

### 1. Modelado de Estacionalidad en Siniestros (Ondas Senoidales)

El Problema Actuarial: Los siniestros no ocurren de manera lineal. Los accidentes de auto aumentan en temporada de lluvias; los reclamos de gastos médicos mayores (SGMM) se disparan en invierno por enfermedades respiratorias.
La Solución: Los actuarios utilizan la función Seno (np.sin) combinada con una tendencia lineal para crear modelos predictivos cíclicos. Esto les permite saber exactamente cuánto dinero líquido deben tener en la reserva cada mes.

### 2. Cobertura de Portafolios (Similitud del Coseno)

El Problema Actuarial: Para respaldar las pólizas, las aseguradoras invierten millones en la bolsa de valores. El actuario debe asegurarse de que el portafolio esté "diversificado". Si invierte en dos empresas que se comportan igual y el mercado cae, la aseguradora quiebra.
La Solución Matemática: La Similitud del Coseno. Sorprendentemente, el Coeficiente de Correlación de Pearson (el estadístico más usado en finanzas) es matemáticamente equivalente al Coseno del ángulo entre dos vectores (si centramos sus promedios a cero).

* Si $\cos(\theta) = 1$ (0 grados): Riesgo máximo. Los activos hacen exactamente lo mismo.

* Si $\cos(\theta) = 0$ (90 grados): Riesgo neutro. Los activos son independientes.

* Si $\cos(\theta) = -1$ (180 grados): Cobertura perfecta. Si un activo pierde dinero, el otro gana exactamente la misma proporción.

## Practica #6

**Instrucción General:** Para resolver todos los ejercicios, debes importar la librería fundamental al inicio de tu script:
```python
import numpy as np
# Para algunos cálculos también necesitarás:
from numpy.linalg import norm
```

---

## Sección A: Ejercicios para Actuaría (Riesgo y Finanzas)

1. **Ciclo de Reclamos Anuales (Siniestralidad Básica):**
   * **Enunciado:** La aseguradora "Alfa" nota que los reclamos de seguros de auto oscilan a lo largo del año. Modela el factor de estacionalidad mensual utilizando un vector de 12 meses (del 1 al 12).
   * **Instrucción de uso:** Crea el vector con `np.arange(1, 13)`. Calcula el factor aplicando `np.sin(2 * np.pi * meses / 12)`.

2. **Correlación de Portafolios (Riesgo Neutro):**
   * **Enunciado:** Tienes dos activos financieros. Quieres saber si están correlacionados. El Activo A tiene rendimientos `[0.05, 0.02, -0.01]`. El Activo B tiene rendimientos `[-0.01, 0.05, 0.02]`.
   * **Instrucción de uso:** Calcula la similitud del coseno usando el producto punto (`np.dot(A, B)`) dividido por el producto de sus normas (`norm(A) * norm(B)`).

3. **Proyección de Tasas con Desfase:**
   * **Enunciado:** Proyecta el comportamiento de las tasas de interés de un préstamo a 5 años (60 meses). La tasa base es del 5%, pero fluctúa con el mercado según una función coseno.
   * **Instrucción de uso:** Genera un vector de tiempo `t = np.arange(1, 61)`. La tasa proyectada es `0.05 + 0.01 * np.cos(t)`.

4. **Cobertura de Divisas (Ángulo de Riesgo):**
   * **Enunciado:** Inviertes en Dólares `[1, 2, 3]` y en Euros `[-1, -2, -3]`. Calcula el ángulo entre ambos vectores para verificar si son una cobertura perfecta (180 grados).
   * **Instrucción de uso:** Encuentra el coseno usando la similitud, aplica `np.arccos(coseno)` para obtener radianes, y conviértelo a grados con `np.rad2deg()`.

5. **Ajuste de Primas por Frecuencia Cíclica:**
   * **Enunciado:** Una póliza agrícola depende de la temporada de lluvias. Calcula un vector que penalice la prima base ($1000) multiplicándola por la tangente de los meses de lluvia crítica (meses 6 a 8). *Precaución matemática: la tangente tiende a infinito en pi/2.*
   * **Instrucción de uso:** Crea un vector `meses = np.array([6, 7, 8])`. Evalúa `1000 * np.tan(meses)`.

6. **Distancia de Escenarios de Riesgo (Magnitud):**
   * **Enunciado:** Tienes un vector con las pérdidas esperadas `[100, 200, 50]` y otro con el capital de reserva `[150, 150, 150]`. Calcula la "distancia euclidiana" entre tu reserva y la pérdida real para saber el faltante total de capital.
   * **Instrucción de uso:** Resta ambos vectores y calcula la norma del vector resultante: `norm(reserva - perdidas)`.

7. **Normalización de Pesos de Inversión:**
   * **Enunciado:** Un portafolio tiene inversiones en tres sectores: `pesos = np.array([10000, 50000, 40000])`. Conviértelo en un vector "unitario" (donde su magnitud total sume 1) para usarlo en un algoritmo de optimización.
   * **Instrucción de uso:** Divide el vector original por su propia norma: `pesos_unitarios = pesos / norm(pesos)`.

8. **Simulación de Varianza Estocástica:**
   * **Enunciado:** Simula el estrés financiero de un portafolio. Multiplica un vector de precios base por un factor de ruido generado por el seno de un ángulo aleatorio entre 0 y 360 grados.
   * **Instrucción de uso:** Define el ángulo aleatorio, conviértelo a radianes con `np.deg2rad()`, calcula su `np.sin()`, y multiplícalo por tu vector de precios.

9. **Ángulo de Desviación de Presupuesto:**
   * **Enunciado:** Tu presupuesto proyectado de gastos médicos era `[10, 10, 10]` (en millones), pero el real fue `[12, 10, 15]`. ¿Cuál es el ángulo de desviación entre lo que planeaste y lo que ocurrió?
   * **Instrucción de uso:** Calcula la similitud del coseno entre ambos vectores y aplica `np.rad2deg(np.arccos())` para encontrar la desviación en grados.

10. **Atenuación de Riesgo a Largo Plazo:**
    * **Enunciado:** Modela cómo el riesgo de impago de una hipoteca (Default) disminuye con el tiempo, oscilando levemente. 
    * **Instrucción de uso:** Utiliza un vector de tiempo de 360 meses. Aplica una función atenuada: `riesgo = np.exp(-tiempo/100) * np.cos(tiempo)`. (Combina álgebra lineal, trigonometría y exponenciales).

---

## Sección B: Ejercicios para Ciencia de Datos (Machine Learning y Análisis)

1. **Recomendación de Películas (Similitud Básica):**
   * **Enunciado:** El usuario A calificó Acción, Comedia y Drama con `[5, 1, 1]`. El usuario B con `[4, 2, 1]`. Crea un pequeño algoritmo que calcule la similitud del coseno para decidir si les recomiendas la misma película.
   * **Instrucción de uso:** Implementa `np.dot(A, B) / (norm(A) * norm(B))` e imprime el resultado decimal.

2. **Detección de Plagio (Vectores de Texto):**
   * **Enunciado:** Convirtiendo textos a números, el documento original tiene el conteo de palabras `[10, 5, 2]`. El documento de un estudiante tiene `[9, 5, 3]`. Calcula si el ángulo entre ellos es menor a 15 grados (lo que indicaría posible plagio).
   * **Instrucción de uso:** Calcula la similitud, usa `np.arccos()` y luego `np.rad2deg()`. Usa un `if` para imprimir la alerta.

3. **Proyección en el Espacio Latente (Producto Punto):**
   * **Enunciado:** Tienes una red neuronal. Los "pesos" de la neurona son `W = np.array([0.5, -0.2, 0.1])` y recibe los datos de entrada `X = np.array([2.0, 1.5, -1.0])`. Calcula el valor de activación crudo.
   * **Instrucción de uso:** La activación de una neurona es el producto punto. Usa `W @ X` (el operador moderno de Python).

4. **Transformación Circular de Variables (Feature Engineering):**
   * **Enunciado:** Tienes una base de datos con la hora de compra (0 a 24). Para una red neuronal, las 23:59 y las 00:01 están muy lejos numéricamente, pero muy cerca en la realidad. Transforma la hora en una coordenada circular (X, Y).
   * **Instrucción de uso:** Convierte la hora a radianes `ang = hora * (2 * np.pi / 24)`. Calcula `np.sin(ang)` para X, y `np.cos(ang)` para Y.

5. **Generador de Patrones Sintéticos (Data Augmentation):**
   * **Enunciado:** Necesitas generar datos de prueba para entrenar un modelo que detecte anomalías cardíacas (ECG). Crea una onda senoidal base.
   * **Instrucción de uso:** Genera `x = np.linspace(0, 10, 500)`. La onda es `y = np.sin(x) + np.sin(3*x)/3`.

6. **Distancia de Manhattan vs Euclidiana (KNN):**
   * **Enunciado:** En el algoritmo K-Nearest Neighbors, debes calcular distancias. Compara la distancia entre los puntos `p1 = [1, 1]` y `p2 = [4, 5]`.
   * **Instrucción de uso:** Distancia Euclidiana: `norm(p1 - p2)`. (No uses trigonometría aquí, solo álgebra vectorial).

7. **Normalización Min-Max Vectorizada:**
   * **Enunciado:** Recibes datos crudos con valores gigantes `datos = np.array([1000, 5000, 2000, 9000])`. Para que el algoritmo no colapse, "aplástalos" para que queden entre 0 y 1.
   * **Instrucción de uso:** Aplica la fórmula directamente al vector: `(datos - datos.min()) / (datos.max() - datos.min())`.

8. **Alineación de Vectores Propios (PCA - Análisis de Componentes Principales):**
   * **Enunciado:** Descubriste que la dirección principal de varianza de tus datos es el vector `v = [1, 1]`. Tienes un nuevo punto de datos `p = [2, 3]`. Calcula la "proyección" de este punto sobre la dirección principal.
   * **Instrucción de uso:** La fórmula de la proyección vectorial es: `(np.dot(p, v) / np.dot(v, v)) * v`.

9. **Cálculo de Error Medio Cuadrático (MSE):**
   * **Enunciado:** Las predicciones de tu modelo son `y_pred = np.array([1.2, 2.5, 3.8])`. Los valores reales eran `y_true = np.array([1.0, 2.0, 4.0])`. Calcula el MSE usando operaciones vectoriales.
   * **Instrucción de uso:** Resta ambos vectores, eleva el resultado al cuadrado usando `** 2`, y luego saca el promedio general con `.mean()`.

10. **Animación Rotacional Sintética (Para exportar a Unity):**
    * **Enunciado:** Vas a pasar datos tabulares a un motor gráfico. Tienes un vector de posiciones X: `[1, 2, 3]` e Y: `[1, 2, 3]`. Aplica una matriz de rotación de 90 grados para girar todas las coordenadas de golpe.
    * **Instrucción de uso:** Define el ángulo de 90 grados en radianes. Construye la matriz de rotación 2x2 usando `np.cos()` y `np.sin()`. Multiplica la matriz por el vector de coordenadas usando el operador `@`.
