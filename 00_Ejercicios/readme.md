## Enunciado del Ejercicio

### Objetivo: Explorar y comprender el uso del método .format() en Python para la interpolación de cadenas de texto (strings).

En este ejercicio, se utilizará una única plantilla de texto con espacios reservados ({}) para insertar de manera dinámica múltiples valores. A través del código, observarás cómo este método es capaz de procesar e imprimir automáticamente diferentes tipos de datos (números enteros, cadenas de texto y valores booleanos), además de manejar caracteres especiales como saltos de línea (\n) dentro de citas célebres. Finalmente, deberás resolver un pequeño reto práctico basado en lo aprendido.

Explicación del Código paso a paso
El script que has compartido es un excelente ejemplo de cómo Python maneja el formateo de texto de manera limpia y estructurada. Aquí tienes el desglose de lo que sucede en cada sección:

Definición de la plantilla: 
```python
formato = "{} {} {} {}"
```
Aquí se crea una variable llamada `formato` que contiene un *string* con cuatro llaves `{}`. Estas llaves actúan como "contenedores" vacíos. Al llamar al método `.format()` sobre esta variable, Python esperará recibir exactamente cuatro elementos para llenar esos espacios en orden de izquierda a derecha.

```python
print(formato.format(1,2,3,4))
print(formato.format("uno","dos","tres","cuatro"))
print(formato.format(True, False, False, True))
```

El método .format() es muy versátil; no importa si le pasas enteros (int), texto (str) o valores lógicos (bool). Internamente, Python convierte todos estos valores a cadenas de texto y los inserta en la plantilla.


### El manejo de errores (Línea comentada):

```python
#print(formato.format(1,2,3))
```

Esta línea está comentada por una buena razón: generaría un error. Como tu variable formato tiene cuatro llaves {}, requiere obligatoriamente al menos cuatro argumentos. Si le pasas solo tres, Python lanzará un IndexError: tuple index out of range.

### Imprime los meses del año en una línea nueva cada vez.
