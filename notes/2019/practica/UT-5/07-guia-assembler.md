# Guía de Trabajos Prácticos — Assembler

> Arquitectura de Computadoras — U.T.N. F.R.Re. — Ciclo lectivo 2019. Unidad Temática V.
> Programación en Assembler para el microcontrolador PIC 16c84. Incluye ejercicios propuestos,
> ejercicios complementarios, preguntas de repaso y ejemplos de las principales instrucciones.

## Contenido

- [Ejercicios Propuestos](#ejercicios-propuestos)
  - [Ejercicio 1](#ejercicio-1)
  - [Ejercicio 2](#ejercicio-2)
  - [Ejercicio 3](#ejercicio-3)
  - [Ejercicio 4](#ejercicio-4)
  - [Ejercicio 5](#ejercicio-5)
  - [Ejercicio 6](#ejercicio-6)
  - [Ejercicio 7](#ejercicio-7)
  - [Ejercicio 8](#ejercicio-8)
  - [Ejercicio 9](#ejercicio-9)
  - [Ejercicio 10](#ejercicio-10)
- [Ejercicios Complementarios](#ejercicios-complementarios)
  - [Ejercicio 1](#ejercicio-1-1)
  - [Ejercicio 2](#ejercicio-2-1)
  - [Ejercicio 3](#ejercicio-3-1)
  - [Ejercicio 4](#ejercicio-4-1)
  - [Ejercicio 5](#ejercicio-5-1)
  - [Ejercicio 6](#ejercicio-6-1)
  - [Ejercicio 7](#ejercicio-7-1)
  - [Ejercicio 8](#ejercicio-8-1)
  - [Ejercicio 9](#ejercicio-9-1)
  - [Ejercicio 10](#ejercicio-10-1)
  - [Ejercicio 11](#ejercicio-11)
  - [Ejercicio 12](#ejercicio-12)
- [Preguntas de Repaso de la Unidad](#preguntas-de-repaso-de-la-unidad)
- [Ejemplos de las Principales Instrucciones de Assembler](#ejemplos-de-las-principales-instrucciones-de-assembler)
  - [Manejo de bits](#manejo-de-bits)
  - [Operaciones con literales](#operaciones-con-literales)
  - [Instrucciones de salto](#instrucciones-de-salto)
  - [Manejo de registros](#manejo-de-registros)

## Ejercicios Propuestos

### Ejercicio 1

Realice un programa en assembler que intercambie los contenidos entre las direcciones 0x0C y 0x1D.

### Ejercicio 2

Realice un programa en Assembler que permita sumar el contenido de las siguientes direcciones 2Ah,
2Bh, 2Ch y 2Dh guardando el resultado en 0Dh. Considerar que las direcciones ya se encuentran
cargadas con valores.

### Ejercicio 3

Construya un programa en assembler que realice la multiplicación de las direcciones 2Ah y 2Fh.
Considerar la carga previa de los valores en dichas direcciones.

### Ejercicio 4

Determinar si el contenido de la dirección 0x2A es múltiplo de 5. De serlo, deben ponerse a 1 todos
los bits de la dirección 0x1C, de lo contrario, deben ser 0.

### Ejercicio 5

Determinar si el contenido de la dirección 0x2A es múltiplo del número almacenado en la dirección
0x15. De serlo, deben ponerse a 1 todos los bits de la dirección 0x1C, de lo contrario, deben ser 0.

### Ejercicio 6

Realice un programa en assembler que recorra el intervalo [0Fh; 22h] y cuente los números impares
dejando dicha cantidad en la posición 2Eh.

### Ejercicio 7

En las direcciones de memoria 10h y 11h se encuentran almacenados dos números con la siguiente
estructura:

- (10h) = `0000 xxxx` donde `xxxx` es un número válido en BCD.
- (11h) = `0000 xxxx` donde `xxxx` es un número válido en BCD.

Realice un programa en ASSEMBLER para microcontroladores PIC 16c84 que sume los contenidos de las
posiciones 10h y 11h dejando el resultado en la dirección 20h. Nota: el resultado debe tener la
siguiente forma:

- (20h) = `000r xxxx` donde `xxxx` es un número válido en BCD y `r` indica el acarreo.

Por ejemplo si:

- (10h) = `0000 0111` [0 7 en BCD]
- (11h) = `0000 0101` [0 5 en BCD]

Entonces:

- (10h) + (11h) = `0001 0010` [1 2 en BCD]

### Ejercicio 8

Las direcciones de memoria 0x2A y 0x2B en hexadecimal almacenan números enteros positivos. Se pide
un programa en assembler que realice la división entera de estas posiciones almacenando el cociente
en la dirección 0x2C y el resto en la posición 0x2D.

- (0x2A) / (0x2B) → cociente: 0x2C
- (0x2A) / (0x2B) → resto: 0x2D

### Ejercicio 9

Realice un programa en Assembler de microcontroladores PIC 16c84 que recorra el intervalo
[0x0f; 0x20] y cuente la cantidad de contenidos que tengan ceros en los bits 0, 1, 4 y 5. Dicha
cantidad debe almacenarse en la dirección 0x0c, incluya los comentarios correspondientes en cada
línea de programa. Escriba el programa utilizando el lenguaje de máquina del microcontrolador.

### Ejercicio 10

> Nota de transcripción: en el documento original este ejercicio aparece nuevamente rotulado como
> «7.-». Se lo renumera aquí como Ejercicio 10 para mantener la secuencia.

A continuación se muestra el contenido de la memoria de programa y el contenido del intervalo
[1A; 2F] de la memoria de datos de un microcontrolador PIC 16c84 (las direcciones y contenidos se
encuentran en hexadecimal).

| EPROM de programa — DIR | CONT  |     | RAM de datos — DIR | CONT |
| ----------------------- | ----- | --- | ------------------ | ---- |
| 000                     | 30 15 |     | 1A                 | 2A   |
| 001                     | 00 8D |     | 1B                 | 28   |
| 002                     | 30 1A |     | 1C                 | 26   |
| 003                     | 00 84 |     | 1D                 | 24   |
| 004                     | 08 00 |     | 1E                 | 22   |
| 005                     | 00 8E |     | 1F                 | 20   |
| 006                     | 08 0D |     | 20                 | 1E   |
| 007                     | 07 04 |     | 21                 | 1C   |
| 008                     | 00 84 |     | 22                 | 1A   |
| 009                     | 08 00 |     | 23                 | 18   |
| 00A                     | 00 8F |     | 24                 | 16   |
| 00B                     | 08 0E |     | 25                 | 14   |
| 00C                     | 00 80 |     | 26                 | 12   |
| 00D                     | 08 0D |     | 27                 | 10   |
| 00E                     | 02 04 |     | 28                 | 0E   |
| 00F                     | 00 84 |     | 29                 | 0C   |
| 010                     | 08 0F |     | 2A                 | 0A   |
| 011                     | 00 80 |     | 2B                 | 08   |
| 012                     | 0A 84 |     | 2C                 | 06   |
| 013                     | 03 8D |     | 2D                 | 04   |
| 014                     | 19 03 |     | 2E                 | 02   |
| 015                     | 28 18 |     | 2F                 | 00   |
| 016                     | 03 8D |     |                    |      |
| 017                     | 28 04 |     |                    |      |
| 018                     | 00 00 |     |                    |      |

Escriba el programa fuente correspondiente y determine cuáles son los valores, después de ejecutar
el programa, contenidos en los registros W, FSR, PC y en el intervalo de memoria RAM que se
especifica en la tabla.

## Ejercicios Complementarios

### Ejercicio 1

Realice un programa en Assembler para Microcontroladores PIC que recorra el intervalo [0x0F, 0x2E] y
cuente la cantidad de posiciones cuyo contenido sea menor que 5. Dicha cantidad debe almacenarse en
la posición 0Ch.

Se pide:

1. Diagrama de Flujo correspondiente.
2. Programa en Assembler.
3. Contenidos de los registros PCL, W, FSR después de finalizada la ejecución del programa.

### Ejercicio 2

Realice un programa en Assembler para Microcontroladores PIC que mueva los contenidos del intervalo
[0x0C, 0x1B] al intervalo [0x1C, 0x2B] dejando el valor complementado en cada posición del primer
intervalo.

Ejemplo:

| Intervalo 1 — DIR | Contenido |     | Intervalo 2 — DIR | Contenido |
| ----------------- | --------- | --- | ----------------- | --------- |
| 0x0C              | 0x13      | →   | 0x1C              | 0xEC      |
| …                 | …         | →   | …                 | …         |
| 0x1B              | …         | →   | 0x2B              | …         |

Se pide:

1. Diagrama de Flujo correspondiente.
2. Programa en Assembler.
3. Contenidos de los registros PC, W, FSR después de finalizada la ejecución del programa.

### Ejercicio 3

Realice un programa en Assembler para Microcontroladores PIC que ordene de menor a mayor (en las
mismas direcciones de memoria RAM) los contenidos de las posiciones 0x0C, 0x0D y 0x0E. En caso de
que todos los contenidos de dichas direcciones sean iguales no debe realizar el ordenamiento
mencionado.

### Ejercicio 4

Se cuenta con dos intervalos de memoria, el primero comprendido entre [0x10, 0x19] y el segundo
comprendido por [0x20, 0x29]. Realice un programa en Assembler para Microcontroladores PIC que
efectúe la operación (0x0C)³ (elevar al cubo el contenido de la posición 0x0C).

- Si el resultado es positivo, deberá mover los contenidos del primer intervalo al segundo.
- Si el resultado es negativo, deberá realizar la operación XOR con el literal 0xFF de los contenidos
  del primer intervalo y almacenar los resultados en el mismo intervalo.
- Si el resultado es cero, deberá poner a cero todos los contenidos del segundo intervalo.

Se pide:

1. Diagrama de Flujo correspondiente.
2. Programa en Assembler.
3. Contenidos de los registros PC, W, FSR después de finalizada la ejecución del programa.

### Ejercicio 5

Realice un programa en assembler para PIC 16c84 que desplace a izquierda los contenidos del intervalo
[0x0F; 0x1E], teniendo en cuenta que el número de veces que tiene que desplazar cada posición está
determinado por la cantidad de unos que posea la dirección homóloga del intervalo que empieza en la
dirección 0x1F.

### Ejercicio 6

Dado el intervalo [0x20; 0x2F], se sabe que tiene cargado en cada dirección ciertas cadenas binarias
de unos y ceros. Se debe realizar un programa que al finalizar deje al intervalo con las cadenas
binarias en orden inverso:

Por ejemplo: si una dirección posee `00110010`, luego de correr el programa tendrá `01001100`.

### Ejercicio 7

Dado el intervalo [0x0C; 0x13] hacer que intercambien valores la primera posición con la última, la
segunda con la anteúltima y así hasta terminar con todas las posiciones tal y como lo muestra el
siguiente esquema:

```
0x0C ←┐
0x0D ←┼┐
0x0E ←┼┼┐
0x0F ←┼┼┼┐
0x10 ←┘│││
0x11 ←─┘││
0x12 ←──┘│
0x13 ←───┘
```

### Ejercicio 8

Se tienen dos intervalos [0x0D; 0x1D] y [0x1E; 0x2F]. A cada posición del primer intervalo se debe
poner a cero solo si el contenido homólogo del segundo intervalo es cero. Realizar el programa
correspondiente en Assembler para PIC 16C84.

### Ejercicio 9

El siguiente programa recorre el intervalo [0x0f; 0x2c] intercambiando en cada posición de memoria
los ceros por unos y viceversa. El inconveniente es que, si bien el programa está completo, las
instrucciones están desordenadas.

- Ordene las instrucciones de manera que el programa pueda realizar el intercambio de bits mencionado
  (incluya el comentario de cada instrucción).
- Al finalizar la ejecución del programa, ¿cuáles son los valores de los registros FSR, INDF, PC y W?

```asm
program movlw 0x1e
indf    equ 0x00
        incf fsr,1
ORG 10
        movlw 0x0f
aux     equ 0x0C
        movwf fsr
        decfsz aux,1
        end
        movlw 0xff
        goto change
        LIST p= 16c84
change  xorwf indf,1
fsr     equ 0x04
        movwf aux
```

### Ejercicio 10

Analice el siguiente programa en ASSEMBLER para microcontroladores PIC 16c84 y explique qué función
cumple.

```asm
        LIST p= 16c84
;-----------------------------------------------------------------
fsr     equ 0x04
test    equ 0x03
indf    equ 0x00
cont    equ 0x22
aux     equ 0x2f
;-----------------------------------------------------------------
        ORG 0x00
;-----------------------------------------------------------------
        clrf  cont
        movlw 0x0d
        movwf fsr
        movlw 0x15
        movwf aux
bucle   decf  indf,1
        comf  indf,1
        btfsc test,2
        incf  cont,1
        incf  fsr,1
        decfsz aux,1
        goto  bucle
        end
```

### Ejercicio 11

Escriba el programa anterior en el Lenguaje de Máquina del Microcontrolador PIC 16C84.

### Ejercicio 12

El siguiente programa realiza el producto entre los contenidos de dos posiciones de memoria.
Determine si es correcto, en caso de no serlo marque los errores y escriba la versión corregida del
programa, incluyendo el comentario de cada instrucción.

```asm
        List p= 16c84
; ---------------------
num1    equ 0x0f
num2    equ 0x3f
resul   equ 0x20
estado  equ 0x04
;----------------------
        ORG 0
        movf  num2,0
        btfsc estado,3
        goto  cero
        movf  num1,0
bucle   decf  num2,0
        addwf num1,0
        decfsz num2,1
        goto  bucle
        movwf resul,1
        goto  cero
cero    clrf  resu
fin     nop
        end
```

## Preguntas de Repaso de la Unidad

1. Dibuje la arquitectura del Microcontrolador PIC 16c84.
2. ¿Cuántas memorias tiene el Microcontrolador PIC 16c84?
3. Describa el ciclo de instrucción del Microcontrolador PIC 16c84.
4. Describa los modos de direccionamiento del Microcontrolador PIC 16c84.
5. Esquematice los modos de direccionamiento directo e indirecto del Microcontrolador PIC 16c84.
6. ¿Qué son los ciclos "Q"?
7. Enuncie las características principales de la arquitectura HARVARD.
8. Explique la función de los bits C, DC y Z del registro de estado.
9. Explique cómo funciona la instrucción `rrf` y `rlf`.
10. ¿El Microcontrolador PIC 16c84 maneja números negativos?
11. ¿Cuál es el formato del registro de instrucción del Microcontrolador PIC 16c84?
12. ¿Cómo se detecta si un número es mayor que otro en el Microcontrolador PIC 16c84?
13. ¿Cómo se puede implementar el direccionamiento indexado en el Microcontrolador PIC 16c84?
14. ¿Cuántos accesos a memoria tiene el direccionamiento indirecto en el Microcontrolador PIC 16c84?
15. ¿Por qué se dice que el registro INDF (dirección 0x00 de RAM de datos) es solo una referencia?

## Ejemplos de las Principales Instrucciones de Assembler

### Manejo de bits

Principales instrucciones que manejan un bit determinado de registros de 8 bits.

```asm
        LIST p= 16c84   ;Indica el modelo de PIC que se usa. Es una directiva del ensamblador.
; --------------------------------------------------------------------------
                        ;Zona para etiquetas.
v1      equ 0x0c
; --------------------------------------------------------------------------
        ORG 0           ;Comando que indica al Ensamblador la dirección de la
                        ;memoria de programa donde situar la siguiente instrucción.
; --------------------------------------------------------------------------
        movlw 0xff      ;0xff -> W
        movwf v1        ;(W) -> v1
        bcf   v1,5      ;pone a cero el bit 5 de v1
        clrf  v1        ;borra el contenido de v1
        bsf   v1,2      ;pone a uno el bit 2 de v1
        end             ;fin de programa
```

### Operaciones con literales

Principales instrucciones que manejan operandos inmediatos.

```asm
        LIST p= 16c84   ;Indica el modelo de PIC que se usa. Es una directiva del ensamblador.
; --------------------------------------------------------------------------
                        ;Zona para etiquetas.
; --------------------------------------------------------------------------
        ORG 0x00        ;Comando que indica al Ensamblador la dirección de la
                        ;memoria de programa donde situar la siguiente instrucción.
; --------------------------------------------------------------------------
        movlw 0x03      ;0x03 --> W
        addlw 0x04      ;(W) + 0x04 --> W
        andlw 0x05      ;(W) and 0x05 --> W
        iorlw 0x0f      ;(W) or 0x0f --> W
        xorlw 0xff      ;(W) xor 0xff --> W
        movlw 0x01      ;0x01 --> W
        sublw 0x01      ;0x01 - (W) --> W
        end             ;fin de programa
```

### Instrucciones de salto

Principales instrucciones condicionales de salto.

```asm
        LIST p= 16c84   ;Indica el modelo de PIC que se usa. Es una directiva del ensamblador.
; --------------------------------------------------------------------------
                        ;Zona para etiquetas.
v1      equ 0x0c
; --------------------------------------------------------------------------
        ORG 0x00        ;Comando que indica al Ensamblador la dirección de la
                        ;memoria de programa donde situar la siguiente instrucción.
; --------------------------------------------------------------------------
        clrf   v1       ;pone a cero el contenido de v1
        btfsc  v1,3     ;salta una inst. si el bit 3 de v1 es cero
        nop             ;no opera
        movlw  0xff     ;mueve el literal 0xff al acumulador
        movwf  v1       ;mueve el contenido del acumulador a v1
        btfss  v1,7     ;salta una inst. si el bit 7 de v1 es uno
        nop             ;no opera
        clrf   v1       ;pone a cero el contenido de v1
        incf   v1,1     ;incrementa en una unidad v1
        decfsz v1,1     ;decr. en uno v1 y si el cont. es 0, salta
        nop             ;no opera
        movwf  v1       ;mueve el contenido del acumulador a v1
        incfsz v1,1     ;incr. en uno v1 y si el cont. es 0, salta
        nop             ;no opera
        end             ;fin de programa
```

### Manejo de registros

Principales instrucciones que manejan como operandos registros de 8 bits.

```asm
        LIST p= 16c84   ;Indica el modelo de PIC que se usa. Es una directiva del ensamblador.
; --------------------------------------------------------------------------
                        ;Zona para etiquetas.
r1      equ 0x0c
; --------------------------------------------------------------------------
        ORG 0           ;Comando que indica al Ensamblador la dirección de la
                        ;memoria de programa donde situar la siguiente instrucción.
; --------------------------------------------------------------------------
        movlw 0x81      ;0x81 -> W
        movwf r1        ;(W) -> r1
        movlw 0xff      ;0xff -> W
        andwf r1,0      ;(W) AND (r1) -> W
        addwf r1,0      ;(W) + (r1) -> W
        comf  r1,1      ;complementa (r1) -> r1
        decf  r1,1      ;(r1) - 1 -> r1
        iorwf r1,1      ;(W) OR (r1) -> r1
        incf  r1,1      ;(r1) + 1 -> r1
        rlf   r1,1      ;rota r1 a la izq. a través del acarreo
        rrf   r1,0      ;rota r1 a la der. a través del acarreo
        subwf r1,0      ;(r1) - (W) -> W
        swapf r1,1      ;intercambia nibbles
        xorwf r1,0      ;(W) XOR (r1) -> W
        clrf  r1        ;borra el cont. de r1 (todos los bits a 0)
        clrw            ;borra W
        movf  r1,1      ;(r1) -> r1
        nop             ;no opera
        end             ;fin de programa
```
