# Guía de Trabajos Prácticos — Unidad de Control

> Arquitectura de Computadoras — U.T.N. F.R.Re. — Ciclo lectivo 2019. Unidad Temática IV. Incluye
> guía de trabajos prácticos de clase y ejercicios complementarios.

## Contenido

- [Trabajos Prácticos de Clase](#trabajos-prácticos-de-clase)
  - [Ejercicio 1](#ejercicio-1)
  - [Ejercicio 2](#ejercicio-2)
  - [Ejercicio 3](#ejercicio-3)
  - [Ejercicio 4](#ejercicio-4)
  - [Ejercicio 5](#ejercicio-5)
  - [Ejercicio 6](#ejercicio-6)
  - [Ejercicio 7](#ejercicio-7)
- [Ejercicios Complementarios](#ejercicios-complementarios)
  - [Ejercicio 1](#ejercicio-1-1)
  - [Ejercicio 2](#ejercicio-2-1)
  - [Ejercicio 3](#ejercicio-3-1)
  - [Ejercicio 4](#ejercicio-4-1)

## Trabajos Prácticos de Clase

### Ejercicio 1

Un computador está disponible sin un contador de programa (CP). En vez de ello, todas las
instrucciones contienen tres partes: Código de operación, Dirección del operando y Dirección de la
instrucción siguiente. El Código de operación consta de 6 bits y el computador tiene una memoria de
8192 palabras.

- a) ¿Cuántos bits debe tener el registro de palabra de memoria si una instrucción es almacenada en
  una palabra? Muestre el formato de la instrucción.
- b) Enumere las micro-operaciones para el ciclo de búsqueda de la instrucción de este computador. Si
  necesita registros auxiliares en la UC, defínalos.

### Ejercicio 2

Dibuje el R.I. (indicando la cantidad de bits de cada parte) de una máquina que posee una memoria de
2050 palabras, 4 registros índice, trabaja con direccionamiento directo, indirecto e inmediato y
puede ejecutar 130 operaciones diferentes. Esquematice la máquina y la conexión entre esos
registros.

### Ejercicio 3

Un computador de una dirección y de una instrucción por palabra, tiene una longitud de palabra de 24
bits. El computador puede ejecutar 19 instrucciones y tiene tres registros índices. La memoria
central posee 70000 palabras. Dibujar el diagrama de una palabra de computador, localizando los
espacios de cada una de las partes de la instrucción. No use el bit de signo (dígito del extremo
izquierdo de la palabra).

### Ejercicio 4

Una computadora tiene una memoria de 95000 palabras. El set de instrucciones consta de 500
operaciones distintas. Posee tres tipos de direccionamiento (Inmediato, Directo e Indirecto). La zona
D del registro de instrucción es de 12 bits. Además, tiene 8 registros índice y dos registros base.
La ALU tiene 6 registros accesorios o auxiliares. Determinar:

- a) Formato de la Instrucción indicando la cantidad de bits de cada parte.
- b) La cantidad de bits de los siguientes registros:
- c) Registro de Palabra de Memoria.
- d) Registro de Selección.
- e) Registros Índice.
- f) Registro Base.
- g) Acumulador.
- h) Registros Auxiliares.
- i) Contador de Programa.
- j) Tamaño de la Palabra de Memoria.
- k) Cantidad de bits del Bus de Datos.
- l) Cantidad de bits del Bus de Direcciones.
- m) Esquema de la máquina.

### Ejercicio 5

Un computador digital tiene una memoria con 32 bits por palabra. El conjunto de instrucciones consta
de 251 operaciones diferentes. Cada instrucción se almacena en una palabra de memoria y consiste en
una parte de código de operación y una parte de dirección. Determine:

- a) ¿Cuántos bits se necesitan para el código de operación?
- b) ¿Cuántos bits se dejan para la parte de dirección de la instrucción?
- c) ¿Cuántas palabras pueden acomodarse en la unidad de memoria?
- d) ¿Cuál es el mayor número binario de punto fijo con y sin signo que puede ser almacenado en una
  palabra de memoria?

### Ejercicio 6

Una computadora tiene una memoria de 32 bits por palabra. El set de instrucciones consta de 510
operaciones distintas. Posee cuatro tipos de direccionamiento (Indexado, Inmediato, Directo e
Indirecto). La zona D del registro de instrucción es de 12 bits. Además, tiene 8 registros índices
de 15 bits cada uno y tres (3) registros base de 33 bits cada uno. La ALU tiene seis (6) registros
accesorios o auxiliares. Determinar:

- a) Formato de la Instrucción indicando la cantidad de bits de cada parte.
- b) Cantidad de bits de los siguientes registros:
- c) Registro de Palabra de Memoria.
- d) Registro de Selección.
- e) Registros Índice.
- f) Registro Base.
- g) Acumulador.
- h) Registros Auxiliares.
- i) Contador de Programa.
- j) Tamaño de la Palabra de Memoria.
- k) Cantidad de bits del Bus de Datos.
- l) Cantidad de bits del Bus de Direcciones.
- m) Esquema de la máquina.
- n) Tamaño de la memoria según cada tipo de direccionamiento. ¿Cuál es la máxima capacidad de
  memoria que se puede direccionar?

### Ejercicio 7

Se cuenta con una máquina de una dirección que utiliza direccionamiento directo, con el siguiente
formato de instrucción:

![Formato de instrucción del ejercicio 7](img/uc-ej07-formato.png)

Se solicita diseñar un circuito secuencial que al detectar el código de operación 110 dispare todas
las micro órdenes en secuencia para realizar la suma del contenido de una dirección de memoria con
el contenido del acumulador. La dirección del operando se encuentra en la zona D del registro de
instrucción. Adjuntar una breve descripción de cada paso en el desarrollo del diseño.

## Ejercicios Complementarios

### Ejercicio 1

Un computador digital tiene una memoria de 32 bits por palabra. El set de instrucciones consta de
450 operaciones distintas. Posee cuatro tipos de direccionamiento (Directo, Inmediato, Indexado e
Indirecto). Además, tiene 10 registros índice de 10 bits. La ALU tiene 8 registros accesorios o
auxiliares. Determinar:

- a) Formato de la Instrucción indicando la cantidad de bits de cada parte.
- b) La cantidad de bits de todos los registros y buses asociados.
- c) Esquema de la máquina.
- d) Cantidad máxima de palabras que se podría administrar con todos los tipos de direccionamiento.

### Ejercicio 2

Dado el siguiente formato del registro instrucción:

| Campo | CO  | MD  | Ix   | B     | Ax    | D      |
| ----- | --- | --- | ---- | ----- | ----- | ------ |
| Bits  | 0–5 | 6–7 | 8–10 | 11–12 | 13–14 | 15–31  |

- Escriba las micro órdenes en secuencia para la fase de ejecución de la operación suma de dos
  posiciones de memoria utilizando direccionamiento directo.
- Realice el cronograma asociado a esa operación.

### Ejercicio 3

Una computadora dispone un Registro de Instrucción de 24 bits, 6 registros índices de 16 bits cada
uno, 4 registros accesorios, modos de direccionamiento: directo, inmediato, indirecto, indexado, y
tiene la capacidad de ejecutar 35 operaciones distintas.

- a) Dibuje la arquitectura completa con todos los registros y buses asociados.
- b) Determinar la cantidad de bits de cada parte del registro instrucción.
- c) Determinar el tamaño de cada registro.
- d) Determinar el tamaño máximo de la memoria, con cada tipo de direccionamiento.

### Ejercicio 4

Una computadora tiene una capacidad de memoria de 32Kb, 4 registros índices, modos de
direccionamiento: directo, inmediato, indirecto, indexado, y tiene la capacidad de ejecutar 18
operaciones distintas.

- a) Dibuje la arquitectura completa con todos los registros y buses asociados.
- b) Determinar la cantidad de bits de cada parte del registro instrucción.
- c) Determinar el tamaño de cada registro.
- d) Escriba las micro órdenes asociadas a la siguiente instrucción con el modo de direccionamiento
  indirecto: CARGAR(AC) con (DIRECCION).
