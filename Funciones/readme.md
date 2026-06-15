# Funciones en Python

* Las funciones son piezas de código reusable.

* Las funciones pueden ser llamadas o invocadas cuando son necesitadas.

* Ayuda a desglosar un problema en partes más manejables.

## Estructura General de una función.

### La estructura general de una función en Python implica el uso de la palabra reservada def y la indentación (sangría) para delimitar el bloque de código:

### Palabra reservada def: Le indica a Python que estás creando una función.


* **Nombre de la función:** Un identificador único.

* **Lista de parámetros:** Variables entre paréntesis separadas por comas (puede estar vacía).

* **Cuerpo de la función:** El bloque de código indentado que define lo que hace.

* **Retorno (opcional):** La instrucción return para devolver un valor (si no se usa, Python devuelve None por defecto).

Estructura General de una función:

```Python
def nombrefuncion(parametro1, parametro2):
    # Cuerpo de la función indentado
    pass
```

**Ejemplo:**

```Python
def suma(num1, num2):
    return num1 + num2

```
### ¿Cómo se llama a una Función? 

Una función puede ser llamada dentro de cualquier otra parte del código y si esta tiene parámetros, debes anexar los valores (argumentos) que reciba la función separados por comas ,.

### ¿Se puede definir una Función dentro de otra Función? 

Sí, a diferencia de C++, en Python sí puedes definir una función dentro de otra función (conocidas como funciones anidadas). Esto es muy útil para ocultar lógica interna o crear "closures". 

> Python también soporta funciones anónimas utilizando la palabra reservada lambda.

Ejemplos de diferentes tipos de funciones.
El ejercicio de hoy implica una serie de ejemplos que muestran algunas de las características de las funciones en Python.

### RECUERDA. Un parámetro es la variable definida dentro de los paréntesis al crear la función.

### Por el contrario, un argumento es el valor real que se le envía a la función cuando esta es llamada.

##  1. Función sin retorno y sin parámetros.

Esta es la estructura más básica. La función ejecutará una acción directa (como imprimir en pantalla), pero no devolverá ningún valor al programa principal (devuelve None por debajo). Al tener los paréntesis vacíos (), tampoco recibe "ingredientes" externos; toda su información es interna.
​
Ejemplo (Imprimir una suma fija internamente):

```Python
# Declaración de función sin retorno explícito y sin parámetros ()
def imprimir_suma_fija():
    # La función define sus propios datos internamente
    a = 8
    b = 12
    suma = a + b
    
    # Ejecuta la acción y termina
    print(f"La suma calculada internamente es: {suma}")

# Bloque principal
if __name__ == "__main__":
    # Al llamarla, simplemente ejecuta su bloque de código encapsulado
    imprimir_suma_fija()
    
    # Podemos llamarla varias veces, pero siempre hará exactamente lo mismo
    imprimir_suma_fija()
```

## 2. Funciones sin retorno y con parámetros
Aquí seguimos ejecutando una acción sin devolver un resultado para operaciones matemáticas, pero ahora los paréntesis contienen "ingredientes" (parámetros). Esto hace que la función sea dinámica.
​
Ejemplo (Imprimir la suma de dos números):

```Python
# Declaración de función que exige dos parámetros
def imprimir_suma(a, b):
    suma = a + b
    print(f"La suma calculada internamente es: {suma}")

if __name__ == "__main__":
    # Llamamos a la función inyectándole los "ingredientes" (5 y 10)
    imprimir_suma(5, 10)
    
    # Podemos reutilizarla con datos distintos
    imprimir_suma(100, 250)

```

## 3. Funciones con retorno y sin parámetros
​
Aquí utilizamos explícitamente la instrucción return. Esto significa que la función trabaja como una "calculadora" que promete entregarnos un dato. Al no tener parámetros, busca la información internamente y nos entrega un resultado limpio.

Python
# Declaración de función que devuelve un valor pero no pide parámetros ()
def obtener_suma_fija():
    valor1 = 20
    valor2 = 30
    
    # El return procesa internamente y devuelve el resultado
    return valor1 + valor2

if __name__ == "__main__":
    # La función no imprime nada por sí sola, debemos atrapar su valor en una variable
    resultado = obtener_suma_fija()
    
    print(f"El valor retornado por la función es: {resultado}")
```

4. Función con retorno y con parámetros.
Este es el estándar de oro en el diseño de algoritmos modulares. Inyectamos datos externos, la función realiza el cálculo a puerta cerrada y nos entrega un resultado usando return.

Ejemplo (Calcular y devolver la suma de datos inyectados):

Python
# Declaración con retorno explícito y con parámetros
def calcular_suma(a, b):
    # Procesa los "ingredientes" recibidos y devuelve el resultado matemático
    return a + b

if __name__ == "__main__":
    # Inyectamos los valores 15 y 25. 
    # Debemos atrapar el resultado en una nueva variable.
    resultado_total = calcular_suma(15, 25)
    
    # Ahora podemos usar ese dato en el flujo principal
    print(f"El resultado procesado y devuelto es: {resultado_total}")
    
    # También podemos imprimir el retorno directamente sin guardarlo
    print(f"Otra suma rápida es: {calcular_suma(50, 50)}")

___

# Práctica #5: Laboratorio de Funciones en Python (Actuaría)

## I. Funciones sin retorno y sin parámetros def nombre():

### Ejercicio 1: Inicializador de Tablas de Mortalidad

Enunciado: Antes de calcular primas de seguros de vida, es necesario cargar las bases biométricas. Escribe una función llamada inicializar_tabla_mortalidad que simule este proceso imprimiendo en consola: "[Sistema] Tabla de mortalidad CNSF cargada exitosamente en memoria."


### Ejercicio 2: Alerta de Auditoría

Enunciado: En la gestión de riesgos, a veces se detienen los procesos para revisión. Diseña una función alerta_auditoria que no reciba parámetros, pero al llamarse imprima: "Cálculo suspendido: Los modelos de reservas requieren validación por el actuario responsable".


### Ejercicio 3: Menú de Ramos de Seguro

Enunciado: Crea una función mostrar_menu_ramos para el cotizador de una aseguradora. Debe imprimir el siguiente texto estructurado: "--- COTIZADOR ACTUARIAL ---" seguido de "1. Vida | 2. Gastos Médicos Mayores | 3. Daños".

## II. Funciones sin retorno y con parámetros def nombre(parametros):

### Ejercicio 4: Emisión de Póliza

Enunciado: Escribe una función emitir_poliza que reciba dos parámetros numéricos: la suma_asegurada y la prima_emitida. La función debe imprimir un resumen del contrato: "Póliza emitida. Suma Asegurada: $[suma], Prima a pagar: $[prima]".


### Ejercicio 5: Notificación de Siniestro

Enunciado: Diseña una función notificar_siniestro que reciba una cadena de texto (string) con el tipo de evento (ej. "Colisión", "Inundación"). Debe imprimir en pantalla: "Alerta de Reserva: Se ha reportado un siniestro de tipo [Evento]".


### Ejercicio 6: Ajuste de Inflación Visual

Enunciado: Crea una función mostrar_tasa_inflacion que reciba un número decimal pequeño (ej. 0.045). La función debe transformar ese número multiplicándolo por 100 e imprimir el aviso: "[Economía] La tasa de inflación proyectada es del [Valor]%".

## III. Funciones con retorno y sin parámetros def nombre(): return

### Ejercicio 7: Tasa Libre de Riesgo

Enunciado: Todo modelo financiero requiere una tasa base. Crea una función obtener_tasa_libre_riesgo que retorne estrictamente el valor decimal 0.05 (representando un 5% de los CETES). Atrapa el retorno en el flujo principal e imprímelo.

### Ejercicio 8: Simulación de Probabilidad de Muerte (qx)

Enunciado: En modelos estocásticos, las probabilidades fluctúan. Diseña una función simular_probabilidad_fallecimiento que no reciba parámetros, pero retorne un número fraccionario aleatorio entre 0.001 y 0.01. Atrapa el valor en el programa e imprímelo.

### Ejercicio 9: Edad de Jubilación Legal

Enunciado: Para calcular reservas de pensiones, se utiliza una edad de corte. Escribe una función obtener_edad_jubilacion que devuelva el número entero 65. Captura este valor y utilízalo en un print indicando que el cálculo de rentas vitalicias iniciará a esa edad.

## IV. Funciones con retorno y con parámetros def nombre(parametros): return

### Ejercicio 10: Prima Pura de Riesgo

Enunciado: La fórmula básica del seguro es multiplicar la frecuencia por la severidad. Crea una función calcular_prima_pura que reciba la frecuencia (probabilidad de que ocurra el siniestro) y la severidad (costo promedio del siniestro). Multiplícalos y retorna el resultado para mostrarlo en el programa principal.

### Ejercicio 11: Valor Presente Simple

Enunciado: Escribe una función calcular_valor_presente que reciba un monto_futuro y una tasa_descuento. Aplica la fórmula monto_futuro / (1 + tasa_descuento) para traer el dinero a valor actual por un periodo. Retorna el resultado redondeado a 2 decimales.

### Ejercicio 12: Indemnización con Deducible (Clamp)

Enunciado: Diseña una función calcular_indemnizacion que reciba el daño_evaluado de un siniestro y el deducible contratado por el cliente. Resta el deducible al daño. Usa un condicional (if) para asegurar que, si el deducible es mayor al daño, la indemnización no sea negativa, sino que retorne 0.
___

# Practica #5 Ciencia de Datos (Data Science)

## I. Funciones sin retorno y sin parámetros def nombre():

### Ejercicio 1: Inicializador del Entorno de Datos
Enunciado: Simular la carga automática de una configuración de entorno para análisis de datos. La función imprimirá en consola que el set de datos por defecto (ej. Dataset Iris) ha sido montado en la memoria caché local.


### Ejercicio 2: Limpiar Historial de Logs
Enunciado: Diseña una función encargada de simular la liberación de memoria RAM tras un entrenamiento pesado. Al llamarse debe imprimir en pantalla: "Los registros temporales y logs de entrenamiento han sido removidos para liberar memoria RAM".


### Ejercicio 3: Menú de Modelos Predictivos
Enunciado: Diseña una función para una interfaz de terminal científica que muestre los algoritmos disponibles para ejecutar: "1. Regresión Lineal | 2. Árbol de Decisión | 3. Random Forest".

## II. Funciones sin retorno y con parámetros def nombre(p1, p2):

### Ejercicio 4: Inspección de Dimensiones (Shape)
Enunciado: Escribe una función que reciba dos parámetros enteros: filas y columnas. Debe imprimir las dimensiones tabulares de la matriz de datos que se va a procesar.

### Ejercicio 5: Registro de Métrica de Evaluación
Enunciado: Cuando se evalúa un modelo de Inteligencia Artificial, se escoge una métrica. Diseña una función que reciba una cadena de texto con el nombre de la métrica (ej. "Accuracy" o "MSE") e imprima: "¡Evaluación finalizada! La métrica seleccionada para el modelo es: [Métrica]".

### Ejercicio 6: Ajustar Tasa de Aprendizaje (Learning Rate)
Enunciado: Escribe una función que reciba un número decimal pequeño (entre 0.0001 y 1.0) que represente la velocidad de aprendizaje de un algoritmo. La función debe multiplicar el valor por 100 para imprimirlo como porcentaje en consola.

## III. Funciones con retorno y sin parámetros def nombre(): return valor

### Ejercicio 7: Generador de Ruido Estocástico (Data Augmentation)
Enunciado: Para hacer que un modelo sea robusto se le inyecta ruido matemático. Diseña una función que no reciba parámetros pero retorne un número decimal pequeño aleatorio que simule el sesgo térmico o ruido de una muestra.

### Ejercicio 8: Umbral de Clasificación por Defecto (Threshold)
Enunciado: En problemas de clasificación binaria (ej. determinar si un correo es Spam o No), el límite de decisión por defecto suele ser 0.5. Crea una función que retorne este valor estático para ser usado en las condiciones del programa principal.


### Ejercicio 9: Sincronización de Épocas (Epochs)
Enunciado: Escribe una función que simule leer el progreso del entrenamiento de una red neuronal y devuelva el número entero 100 (indicando que llegó a la época 100). Captura el valor e imprímelo.

## IV. Funciones con retorno y con parámetros def nombre(p1): return valor

### Ejercicio 10: Normalización Min-Max Escalada
Enunciado: Escribe una función que reciba el valor numérico actual de un dato, el valor mínimo de la columna y el valor máximo de la misma. Aplica la fórmula: (valor - minimo) / (maximo - minimo) y retorna el valor transformado a escala entre 0 y 1.

### Ejercicio 11: Error Absoluto Elemental (MAE)
Enunciado: La distancia entre la predicción de la computadora y el valor real mide el error. Diseña una función que reciba la prediccion (float) y el valor_real (float), calcule la resta y devuelva el resultado en valor absoluto absoluto usando la función nativa de Python abs().


### Ejercicio 12: Control de Valores Atípicos (Clip/Tratamiento de Outliers)
Enunciado: Los valores extremos dañan los análisis estadísticos. Diseña una función que reciba el valor de un sueldo, un limite_inferior y un limite_superior. Si el sueldo es menor al inferior, se iguala al inferior; si supera al superior, se reduce al superior. Retorna el valor corregido.

___

### Que es una función prototipo. 

**Es la cabecera o primera línea de una función, seguido de un punto y coma. Adicionalmente debemos hacer la definición de la función**

***Generalidades de las funciones prototipo:***

* Es una función que solo contiene el tipo de retorno, nombre de la función y sus parámetros, seguido de un punto y coma.
* Una función en C++ se define arriba de la función main(), pero es más común crear una función prototipo **arriba** de la función main(), y definir la función, es decir, el código necesario de la función **debajo** de la función main().
* Porque se divide en dos? Le informa al compilador que existe una función y ayuda al compilador a ser más eficiente.

> En C++ una función debe ser declarada _arriba_ de la función main(), en otros lenguajes la función puede
> estar arriba o debajo de la función main(), pero, en C++ solo puede estar arriba, si deseamos poner
> nuestras funciones por debajo de la función, se debe usar la definición de la función prototipo.

***Estructura General de una función prototipo***

```C++
<tipo_retorno> nombrefuncion(Lista Parametros);
```

Ejemplo:

```cplusplus
int suma(int num1, int num2);
```

### Definición de una función que usa en conjunto con la función prototipo.

**Propósito:** Es la implementación completa de la función, incluyendo el cuerpo, que define todas las instrucciones que cumplen el propósito de la función.

```C++
<tipo_retorno> nombrefuncion(Lista Parametros)
{
	// instrucciones de lo que actualmente hace la función
}
```

Ejemplo

```cplusplus
int suma(int num1, int num2)
{
	return num1+num2;
}
```
### Diferencias clave entre definición y declaración de funciones

1. Contenido:
* Declaración: Solo especifica la firma de la función.
* Definición: Incluye el cuerpo de la función con el código real.
2. Propósito:
* Declaración: Informa al compilador sobre la existencia de la función y su interfaz.
* Definición: Informa al compilador de cómo funciona la función.
3. Ubicación:
* Declaración: Por lo general, se encuentra en archivos de encabezado (.h).
* Definición: Por lo general, se encuentra en los archivos fuente (.cpp).

___

### Ejemplo de una funcion prototipo.

Una funcion prototipo tiene multiples propositos, el mas basico es el hecho de poder mover la definicion de la funcion en la parte inferior de la funcion **main()** que genera un codigo de mas facil lectura.  

```C++
// ConsoleApplication12.cpp : This file contains the 'main' function. Program execution begins and ends there.
//

#include <iostream>
#include <vector>
using namespace std;
// funcion prototipo
void imprime(vector<int> v);

int main()
{
    vector<int> v;
    v.push_back(1);
    v.push_back(2);
    imprime(v);
}
// Definiciones de la función
void imprime(vector<int> v)
{
    for (auto elemento : v)
    {
        cout << elemento << " , ";
    }
    cout << endl;
}
```

### Ejemplo práctico integral: Establece las operaciones básicas de un cajero automático:


> Realice un programa en C++ que represente las operaciones básicas de un cajero automático, que son consulta de saldo de una cuenta, y retiro de efectivo de una cuenta.

> Para el proceso de consulta, deberá mostrar en pantalla el saldo, usando una función donde imprima el valor del saldo. Considere que la variable donde guarde el saldo, debe ser una variable global.

> Para el proceso de retiro deberá preguntar por la cantidad a retirar en pantalla, validar que la cantidad no exceda al saldo, usar parámetro por referencia para modificar el saldo, en caso de que el retiro se ejecute.

> Si obtiene el saldo y no excede la cantidad de la que puede disponer, deberá “simular” la operación de entrega de efectivo y descontar la cantidad del saldo y enviar petición de actualización del saldo a la central.



```C++

#include <iostream>
#include <iomanip>
using namespace std;
//variable global. Se definen fuera de cualquier función
int opcion;
double saldoActual = 5000, retiro, deposito;
// función prototipo
void menu();
void imprimeSaldo(double saldo1);
void retirar(double saldo1);
void depositar(double deposito);
 
void imprime() 
{
    std::cout << "Hello World!\n";
}
 
int main()
{
    imprime();
    do {
        menu();
        switch (opcion)
        {
        case 1:
            imprimeSaldo(saldoActual);
            break;
        case 2:
            cout << "Ingrese el monto a retirar: ";
            cin >> retiro;
            retirar(retiro);
            break;
        case 3:
            cout << "Ingrese el monto a depositar: ";
            cin >> deposito;
            depositar(deposito);
            break;
        default:
            break;
        }
    } while (opcion != 4);
}
 
void depositar(double deposito1) 
{
    saldoActual = saldoActual + deposito1;
    cout << "Su saldo actual es: " << saldoActual << endl;
 
}
 
    void retirar(double retiro1)
    {
        if (retiro1 > saldoActual)
        {
            cout << "Saldo insuficiente" << endl;
        }
        else
        {
            saldoActual = saldoActual - retiro1;
        }
        cout << "Su saldo actual es: " << saldoActual << endl;
    }
 
    void imprimeSaldo(double saldo1)
    {
        cout << "El saldo actual es: " << saldo1 << endl;
    }
 
    void menu()
    {
        cout << "Bienvenido al cajero automatico" << endl;
        cout << "1. Consultar saldo" << endl;
        cout << "2. Retirar" << endl;
        cout << "3. Depositar" << endl;
        cout << "4. Salir" << endl;
        cout << "Seleccione una opcion: ";
        cin >> opcion;
        cout << "La opcion seleccionada es: " << opcion << endl; 
    }

```
___

## Parámetros x Valor y parámetros x referencia

### Parámetro por valor: 

Un parámetro cuyo Tipo NO va seguido de un signo ampersand (&) se denomina parámetro x valor. Un parámetro x valor es una variable local a la función, tal que cuando se llama a la función, recibe una **copia del valor del argumento correspondiente**.

### Parámetro por referencia:

Un parámetro cuyo Tipo va seguido de un signo ampersand (&) se denomina parámetro x referencia. Un parámetro x referencia es un alias (por ejemplo, otro nombre) para su argumento correspondiente. Y el valor del argumento que se pasa, será modificado.

Ejemplo simple:

```C++
#include <iostream>
#include <vector>

using namespace std;

void suma(int& a) 
{
    cout << "numero en suma() " 
        << a << endl;
    a++;
    cout << "numero en suma() "
        << a << endl;
}
int main()
{
    int numero = 10;
    suma(numero);
    cout << "numero en main() " <<
        numero << endl;
}
```

____
### Ejemplo: Parámetros x valor y Parámetros por referencia.

Haga un nuevo código que incluya las funciones prototipo y sus definiciones y use parametros por valor y por referencia, segun sea el caso. 

```C++

#include <iostream>
#include <iomanip>
using namespace std;
//variable global. Se definen fuera de cualquier función
int opcion;
double  retiro, deposito;
// función prototipo
void menu();
void imprimeSaldo(double saldo1);
void retirar(double saldo1, double &sa);
void depositar(double deposito, double &sa);
 
void imprime() 
{
    std::cout << "Hello World!\n";
}
 
int main()
{
    double saldoActual = 5000;
    imprime();
    do {
        menu();
        switch (opcion)
        {
        case 1:
            imprimeSaldo(saldoActual);
            break;
        case 2:
            cout << "Ingrese el monto a retirar: ";
            cin >> retiro;
            retirar(retiro,saldoActual);
            break;
        case 3:
            cout << "Ingrese el monto a depositar: ";
            cin >> deposito;
            depositar(deposito, saldoActual);
            break;
        default:
            break;
        }
    } while (opcion != 4);
}
 
void depositar(double deposito1, double &sa) 
{
    sa = sa + deposito1;
    cout << "Su saldo actual es: " << sa << endl;
 
}
 
    void retirar(double retiro1, double &sa)
    {
        if (retiro1 > sa)
        {
            cout << "Saldo insuficiente" << endl;
        }
        else
        {
            sa = sa - retiro1;
        }
        cout << "Su saldo actual es: " << sa << endl;
    }
 
    void imprimeSaldo(double saldo1)
    {
        cout << "El saldo actual es: " << saldo1 << endl;
    }
 
    void menu()
    {
        cout << "Bienvenido al cajero automatico" << endl;
        cout << "1. Consultar saldo" << endl;
        cout << "2. Retirar" << endl;
        cout << "3. Depositar" << endl;
        cout << "4. Salir" << endl;
        cout << "Seleccione una opcion: ";
        cin >> opcion;
        cout << "La opcion seleccionada es: " << opcion << endl; 
    }

```
___

## Funciones Overloading

Una función **overloading** es el proceso de crear funciones múltiples con el mismo nombre pero con diferentes “firmas” o tipos y formas de lista de parámetros.

Una función con “firmas” consiste en el nombre de la función con una lista de parámetros de la función.

* Nunca una función overloading incluye un retorno. **return**.
* Los parámetros pueden variar en número, tipo y orden.


Ejemplo:

```C++
#include <iostream>
using namespace std;
// Declaración de funciones sobrecargadas
void imprime(int numInt) {
    cout << "Entero: " << numInt << endl;
}

void imprime(double numDouble) {
    cout << "Doble flotante: " << numDouble << endl;
}

void imprime(const string& st) {
    cout << "String: " << st << endl;
}

int main() {
    // Llamadas a las funciones sobrecargadas
    imprime(34);           // Llama a la versión que acepta un int
    imprime(45.78);         // Llama a la versión que acepta un double
    imprime("Hola!");      // Llama a la versión que acepta una cadena

    return 0;
}
```
### Ejemplo de la calculadora usando funciones overloading. 

Usando todas las posibles combinaciones de tipos de variable, usando funciones overloading, solo se muestra la operación suma().

```C++
// ConsoleApplication19.cpp : This file contains the 'main' function. Program execution begins and ends there.
//

#include <iostream>
#include "Header.h"
using namespace std;
// Funciones prototipo
void suma(int a, int b);
void suma(double a, double b);
void suma(float a, float b);
void suma(string a, string b);
void suma(int a, double b);
void suma(double a, int b);
void suma(int a, float b);
void suma(float a, int b);
int main()
{
	// Ejercicio 4
	suma(1, 2);
	suma(3.4, 5.6);
}
// Definicion de la funcion
void suma(int a, int b) 
{
	cout << a + b << endl;
}
void suma(double a, double b)
{
	cout << a + b << endl;
}
void suma(float a, float b) 
{
	cout << a + b << endl;
}
```

___


### Ejemplo usando una función calculaArea() para diferentes figuras geométricas. 

Usando funciones overloading crear una función llamada calculaArea(), que pueda calcular el área de al menos cuatro figuras geométricas. Hacer un menú de opciones que muestre las opciones de cálculo de área, por ejemplo: cuadrado, triangulo equilátero, circulo, rectángulo etc. Dependiendo de los datos de entrada serán los parámetros y argumentos a usar en la función, pero solo puede usar un solo nombre de función.
```C++

#include <iostream>
#include <cmath> 
using namespace std;

// Sobrecarga de la función calculaArea

// Área del cuadrado: lado * lado
double calculaArea(double lado) {
    return lado * lado;
}

// Área del triángulo equilátero: (sqrt(3) / 4) * lado * lado
double calculaArea(double base, double altura) {
    return 0.5 * base * altura;
}

// Área del círculo: pi * radio * radio
double calculaArea(float radio) {
    return 3.1416 * radio * radio;
}

// Área del rectángulo: largo * ancho
double calculaArea(int largo, int ancho) {
    return largo * ancho;
}

int main() {
    int opcion;
    cout << "Calculadora de áreas" << endl;
    cout << "1. Cuadrado" << endl;
    cout << "2. Triángulo equilátero" << endl;
    cout << "3. Círculo" << endl;
    cout << "4. Rectángulo" << endl;
    cout << "Seleccione una opción: ";
    cin >> opcion;

    switch(opcion) {
        case 1: {
            double lado;
            cout << "Ingrese el lado del cuadrado: ";
            cin >> lado;
            cout << "Área del cuadrado: " << calculaArea(lado) << endl;
            break;
        }
        case 2: {
            double base, altura;
            cout << "Ingrese la base del triángulo equilátero: ";
            cin >> base;
            cout << "Ingrese la altura del triángulo equilátero: ";
            cin >> altura;
            cout << "Área del triángulo equilátero: " << calculaArea(base, altura) << endl;
            break;
        }
        case 3: {
            float radio;
            cout << "Ingrese el radio del círculo: ";
            cin >> radio;
            cout << "Área del círculo: " << calculaArea(radio) << endl;
            break;
        }
        case 4: {
            int largo, ancho;
            cout << "Ingrese el largo del rectángulo: ";
            cin >> largo;
            cout << "Ingrese el ancho del rectángulo: ";
            cin >> ancho;
            cout << "Área del rectángulo: " << calculaArea(largo, ancho) << endl;
            break;
        }
        default:
            cout << "Opción no válida" << endl;
    }

    return 0;
}

```
___

## Funciones Recursivas

Funciones Recursivas (Algoritmos avanzados). Una función recursiva se llama a sí misma de manera directa o indirecta (vía otra función). 

Es en su mayoría como una función normal excepto que al menos se llama una vez a sí misma y contiene una solución base que es la solución más simple del problema. 

Esta solución simple es un booleano (condición lógica) que cuando esta es verdadera, es decir se cumple se detiene de llamar a la función nuevamente. 

Esto es cuando no hay más cálculos que procesar. 

Estas condiciones simples son instrucciones if-else con la instrucción return. 

### Otra definicion 

Una función recursiva se llama a sí misma de manera directa o indirecta (vía otra función).

Es en su mayoría como una función normal excepto que al menos se llama una vez a sí misma y contiene una solución base que es la solución más simple del problema.

Esta solución simple es un booleano (condición lógica) que cuando esta es verdadera, es decir se cumple se detiene de llamar a la función nuevamente. Esto es cuando no hay más cálculos que procesar.

Estas condiciones simples son instrucciones if-else con la instrucción return.

```C++
// Recursivas.cpp : This file contains the 'main' function. Program execution begins and ends there.
//

#include <iostream>
using namespace std;
int suma1=0;
int suma(int num) 
{
	if (num == 1) 
	{
		cout << "Condicion mas simple : " << num << ", suma1: " << suma1+1 << endl;
		return 1;
	}
	else 
	{
		
		 suma1 = num + suma(num - 1);
		 cout << "Retornando a llamada de : " << num << ", suma1: " << suma1 << endl;
	}
	
	return suma1;

}

int main()
{
	
	cout << "Resultado en main() : " << suma(5) << endl;
}


```

## Glosario
