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


```

## Trabajo con Secuencias (Listas, Tuplas, etc.)

Increíblemente útiles para extraer o manipular datos de un conjunto existente.

* random.choice(secuencia): Elige un único elemento al azar.

* random.choices(secuencia, weights=None, k=1): Devuelve una lista de tamaño k con elementos elegidos con reemplazo (pueden repetirse). El parámetro weights asigna distintas probabilidades.

* random.sample(secuencia, k): Devuelve una lista de tamaño k con elementos elegidos sin reemplazo (elementos únicos).

* random.shuffle(lista): Mezcla los elementos de una lista in situ (modifica la lista original).

```python
import random

clientes = ["Ana", "Beto", "Carlos", "Diana", "Elena"]

# 1. Elegir un ganador para un sorteo
ganador = random.choice(clientes)
print(f"Ganador: {ganador}")

# 2. Simular 10 compras con pesos (Ana compra el 80% de las veces)
compras = random.choices(clientes, weights=[80, 5, 5, 5, 5], k=10)
print(f"Simulación de 10 compras: {compras}")

# 3. Hacer una auditoría a 2 clientes únicos (sin repetir)
auditados = random.sample(clientes, 2)
print(f"Clientes a auditar: {auditados}")

# 4. Barajar la lista original para cambiar turnos de atención
random.shuffle(clientes)
print(f"Nuevos turnos de atención: {clientes}")
```

## Distribuciones Estadísticas

Para modelar comportamientos del mundo real, necesitamos que la aleatoriedad siga una distribución matemática específica.

random.gauss(mu, sigma): Genera un número decimal basado en una Distribución Normal. Recibe la media (mu) y la desviación estándar (sigma).

random.expovariate(lambd): Genera un número basado en la Distribución Exponencial. Modela tiempos de espera.

```python
import random

# Simular la estatura de una persona (Media = 1.70m, Desviación = 0.1m)
estatura = random.gauss(1.70, 0.1)
print(f"Estatura simulada: {estatura:.2f} m")

# Simular el tiempo de espera (en minutos) hasta el próximo accidente
# Si ocurren en promedio 2 accidentes por hora (lambda = 2/60)
tiempo_espera = random.expovariate(2/60)
print(f"Minutos hasta el próximo accidente: {tiempo_espera:.1f} min")

```
## La Semilla (Seed)

random.seed(a): Fija el estado inicial del generador de números. Garantiza que la "aleatoriedad" sea repetible para auditorías o experimentos compartidos.

```python
import random

# Fijamos la semilla en 42 (un estándar en la industria de datos)
random.seed(42)
prueba_1 = random.randint(1, 100)

# Volvemos a fijar la misma semilla
random.seed(42)
prueba_2 = random.randint(1, 100)

# ¡Ambas pruebas darán el mismo resultado exacto!
print(f"Prueba 1: {prueba_1}")
print(f"Prueba 2: {prueba_2}")

```
