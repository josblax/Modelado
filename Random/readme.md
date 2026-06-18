# Funciones Principales de la Librería `random` en Python

La librería `random` es una herramienta fundamental para realizar simulaciones, crear escenarios estocásticos, hacer muestreos y aplicar imprevisibilidad controlada en nuestros modelos. 

A continuación, se dividen sus funciones principales en cuatro categorías clave, con ejemplos de aplicación orientados a Ciencia de Datos y Actuaría.

## 1. Generación de Números (Enteros y Decimales)

Estas funciones son la base para obtener números al azar dentro de un rango determinado.

* **`random.random()`**: Devuelve un número decimal (flotante) aleatorio entre `0.0` y `1.0` (sin incluir el 1.0).
* **`random.randint(a, b)`**: Devuelve un número entero aleatorio $N$ tal que $a \le N \le b$. *(Ambos extremos están incluidos)*.
* **`random.uniform(a, b)`**: Devuelve un número decimal aleatorio entre $a$ y $b$.

### Ejemplos de uso:
```python
import random

# Generar una probabilidad pura (ej. 0.854...)
probabilidad = random.random()
print(f"Probabilidad de siniestro: {probabilidad:.4f}")

# Simular el lanzamiento de un dado de 6 caras
dado = random.randint(1, 6)
print(f"El dado cayó en: {dado}")

# Generar una tasa de interés aleatoria entre 4.5% y 8.5%
tasa = random.uniform(4.5, 8.5)
print(f"Tasa de interés proyectada: {tasa:.2f}%")
