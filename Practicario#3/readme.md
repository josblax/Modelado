# Derivadas

## Elabora las 10 siguientes derivadas:

1. Derivada de la función de activación logística: $f(x) = (1 + e^{-x})^{-1}$.
2. Derivada de la entropía de una variable: $f(x) = x \ln(x)$.
3. Derivada de $f(x) = e^{x^2}$.
4. Derivada de $f(x) = \ln(x^2 + 5)$.
5. Derivada de $f(x) = \sqrt{x^3 + 1}$.
6. Derivada de $f(x) = x^2 e^{3x}$.
7. Derivada de $f(x) = \tan(x^2)$.
8. Derivada de $f(x) = \frac{\ln(x)}{x}$.
9. Derivada de $f(x) = (2x + 1)^4$.
10. Derivada de $f(x) = e^{2x} \sin(x)$.

```Python
import sympy as sp
import numpy as np
import matplotlib.pyplot as plt

# Para que se vean bonitas las formulas en Jupyter Notebooks
sp.init_printing(use_latex='mathjax')

# Definicion de variables y funcion de posicion
t = sp.symbols('t')

#Definición de la ecuación de trayectoria x(t) usando la funcion sympy

x_t = sp.sqrt(t**3+t**2-1)+sp.exp(t)+1

# Desplegar la funcion

display(x_t)

# Calculo de la función de velocidad instantanea v(t)

v_t = sp.diff(x_t,t)

print("Funcion de velocidad instantanea")

display(v_t)

# Evaluacion de la velocidad instantanea en t = [2,5,8,10]

tiempos_evaluacion = [2,5,8,10]

print("Velocidades instantaneas:")

for tiempo in tiempos_evaluacion:
    #Sustituimos t por el valor de del tiempo y forzamos una evaluación decimal
    velocidad = v_t.subs(t,tiempo).evalf()
    print(f"Velocidad en t = {tiempo} s: {velocidad:.4f} m/s")

# Grafica de la trayectoria x(t)

#Convertir la funcion simbolica en una funcion evaluable con Numpy

x_numerica = sp.lambdify(t, x_t, "numpy")

# Generar los valores x (tiempo)

vector_t = np.linspace(1,10,200)

# Evaluamos todos los puntos en el eje y
vector_x = x_numerica(vector_t)

#Generamos la grafica 

plt.plot(vector_t, vector_x, color='purple', linewidth=2, label='x(t)')

```
