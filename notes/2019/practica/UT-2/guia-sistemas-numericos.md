# Guía de Trabajos Prácticos — Sistemas Numéricos

> Arquitectura de Computadoras — U.T.N. F.R.Re. — Ciclo lectivo 2009. Unidad Temática II. Incluye
> ejercicios resueltos y propuestos de operaciones con distintos sistemas numéricos.

**Cátedra:** Ing. Marcelo Karanik · Damián Agostón (Becario Alumno) · AUS Emiliano Ivaniszyn.

## Contenido

- [Objetivos](#objetivos)
- [Pasaje de base por descomposición polinómica](#pasaje-de-base-por-descomposición-polinómica)
  - [Ejercicios resueltos](#ejercicios-resueltos)
  - [Ejercicios propuestos](#ejercicios-propuestos)
- [Pasaje directo de bases](#pasaje-directo-de-bases)
  - [Ejercicios resueltos](#ejercicios-resueltos-1)
  - [Ejercicios propuestos](#ejercicios-propuestos-1)
- [Operaciones aritméticas en diferentes bases](#operaciones-aritméticas-en-diferentes-bases)
  - [Ejercicios resueltos](#ejercicios-resueltos-2)
  - [Ejercicios propuestos](#ejercicios-propuestos-2)
- [Complemento a la base y a la base menos uno](#complemento-a-la-base-y-a-la-base-menos-uno)
  - [Ejercicios resueltos](#ejercicios-resueltos-3)
  - [Ejercicios propuestos](#ejercicios-propuestos-3)

## Objetivos

En la presente guía de trabajos prácticos se presentan una serie de ejercicios resueltos y
propuestos de operaciones utilizando distintos sistemas numéricos. El objetivo de esta guía es que
el alumno utilice estos trabajos prácticos a fin de comprender la representación de la información
numérica en distintas bases y la utilización de las operaciones básicas.

Para profundizar estos temas puede remitirse a la bibliografía:

- MEINADIER, J. P., _Estructura y Funcionamiento de los Computadores Digitales_. Ed. AC. 1975.
- BARTEE, T. C., _Fundamentos de computadores digitales_. Ed. Mc Graw-Hill. 1986.
- GINZBURG, M. C., _Álgebra de Boole aplicada a circuitos de Computación y codificación de
  números_. Ed. Biblioteca Técnica Superior — Bs. As. 1996.

## Pasaje de base por descomposición polinómica

### Ejercicios resueltos

Los pasajes entre bases se pueden realizar utilizando la descomposición polinómica del número. Por
ejemplo, pasar el número 2301 de base 4 a base 10 implica tomar cada dígito y multiplicarlo por la
base (en este caso 4) elevada a la posición que ocupa el dígito:

```
2 × 4³ + 3 × 4² + 0 × 4¹ + 1 × 4⁰ = 177
```

> Nota: las posiciones de los dígitos se numeran de derecha a izquierda desde 0.

Para realizar el proceso inverso (de base 10 a cualquier base) se utiliza el método de las divisiones
sucesivas. Consiste en tomar el número en decimal y hacer la división ENTERA utilizando la base a
la que se quiere pasar. Para pasar el número 177 a base 4:

```
177 / 4 = 44 ; Resto = 1
 44 / 4 = 11 ; Resto = 0
 11 / 4 =  2 ; Resto = 3
  2 / 4 =  0 ; Resto = 2
```

Las divisiones se realizan hasta obtener como cociente el número 0. Para reconstruir el número en
base 4 se toman los RESTOS obtenidos desde el último hasta el primero:

```
177 = 2301₍₄₎
```

> Nota: ningún dígito del resultado puede alcanzar el valor de la base; en el ejemplo ninguno
> alcanza el valor 4.

El mismo procedimiento sirve para cualquier base. Pasando 177 a binario:

```
177 / 2 = 88 ; Resto = 1
 88 / 2 = 44 ; Resto = 0
 44 / 2 = 22 ; Resto = 0
 22 / 2 = 11 ; Resto = 0
 11 / 2 =  5 ; Resto = 1
  5 / 2 =  2 ; Resto = 1
  2 / 2 =  1 ; Resto = 0
  1 / 2 =  0 ; Resto = 1

177 = 10110001₍₂₎
```

> Nota: el método de pasaje por divisiones sucesivas se hace solo de sistema decimal a cualquiera de
> los otros sistemas, a menos que se opere en la base a la que se quiere pasar. Es decir, si se desea
> pasar el número 177₍₈₎ a base 4 debe operarse en base 8:

```
177₍₈₎ / 4₍₈₎ = 37₍₈₎ ; Resto = 3
 37₍₈₎ / 4₍₈₎ =  7₍₈₎ ; Resto = 3
  7₍₈₎ / 4₍₈₎ =  1₍₈₎ ; Resto = 3
  1₍₈₎ / 4₍₈₎ =  0₍₈₎ ; Resto = 1

177₍₈₎ = 1333₍₄₎
```

Para comprobar se aplica la descomposición polinómica pasando ambos valores a decimal:

```
177₍₈₎  = 1 × 8² + 7 × 8¹ + 7 × 8⁰ = 127
1333₍₄₎ = 1 × 4³ + 3 × 4² + 3 × 4¹ + 3 × 4⁰ = 127
```

### Ejercicios propuestos

Dados los siguientes números en las bases indicadas, pasarlos a base 10 (decimal). Luego transformar
el número resultante a base binaria.

1. 2301₍₄₎
2. 53,11₍₆₎
3. −412₍₈₎
4. 25AB₍₁₆₎
5. 7AC₍₁₆₎
6. FFF₍₁₆₎
7. ABF₍₁₆₎
8. FE0₍₁₆₎
9. 11010001₍₂₎
10. 732₍₈₎
11. 7AC₍₁₆₎
12. 11001100101010₍₂₎

Dados los siguientes números en sistema decimal, convertirlos a las bases 2, 7, 8 y 16, expresando
de forma ordenada en una tabla.

1. 1874
2. −312
3. 85
4. 824
5. 512
6. 256
7. 1500

## Pasaje directo de bases

### Ejercicios resueltos

El pasaje directo es un procedimiento que se puede realizar solamente entre bases que, elevándolas a
alguna potencia entera, dan como resultado otras bases. Por ejemplo, un número en base 2 puede
pasarse a base 4 (2²), base 8 (2³) o base 16 (2⁴), o cualquier base que sea potencia de 2. Esto
significa que el pasaje es posible cuando:

```
b₁ᵏ = b₂
```

Donde k representa la potencia de b₁.

Para pasar 11100011110011₍₂₎ a base 8 (2³), con k = 3, se hacen grupos de 3 dígitos comenzando
desde la derecha (el último grupo se completa con ceros) y se determina el valor de cada grupo:

```
 011  100  011  110  011
  3    4    3    6    3

11100011110011₍₂₎ = 34363₍₈₎
```

El procedimiento inverso (de base mayor a base menor) descompone cada dígito en tantos dígitos como
indica k:

```
  3    4    3    6    3
 011  100  011  110  011

34363₍₈₎ = 11100011110011₍₂₎
```

Otro ejemplo: pasar 34025₍₉₎ a base 3. Como 9 = 3², k = 2, cada dígito en base nueve se descompone
en 2 dígitos de base 3:

```
  3    4    0    2    5
 10   11   00   02   12

34025₍₉₎ = 1011000212₍₃₎
```

No se puede aplicar pasaje directo de base 8 a base 16, porque no existe una potencia de 8 que dé 16
(error común al confundir potencia con múltiplo). En ese caso se usa una base intermedia. Por
ejemplo, pasar 37025₍₈₎ a base 16, primero de base 8 a binario con k = 3:

```
  3    7    0    2    5
 011  111  000  010  101

37025₍₈₎ = 0111110000101001₍₂₎
```

Luego de binario a hexadecimal con k = 4:

```
 0011  1110  0001  0101
  3     E     1     5

0111110000101001₍₂₎ = 3E15₍₁₆₎
```

Resumiendo: **37025₍₈₎ = 3E15₍₁₆₎**.

### Ejercicios propuestos

Realizar las conversiones indicadas utilizando las propiedades de las bases:

1. 34025₍₉₎ a base tres
2. AB4₍₁₆₎ a base dos
3. 347₍₈₎ a base dos
4. 1200₍₃₎ a base nueve
5. 110010101100010₍₂₎ a base dieciséis
6. 1011110101011₍₂₎ a base ocho

Pasar los siguientes números a la base indicada de forma directa.

**De Hexadecimal a Binario:** ABAC₍₁₆₎ · FAC₍₁₆₎ · C1A₍₁₆₎ · 111₍₁₆₎ · 8A2₍₁₆₎ · 4B₍₁₆₎

**De Octal a Binario:** 470₍₈₎ · 111₍₈₎ · 220₍₈₎ · 40₍₈₎ · 3120₍₈₎ · 654₍₈₎

**De Binario a Octal y a Hexadecimal:** 11110001₍₂₎ · 10100111₍₂₎ · 11101000110₍₂₎ · 1000001₍₂₎ ·
1000000100₍₂₎

**De Hexadecimal a Octal y a base 4:** 12AB₍₁₆₎ · BAAB₍₁₆₎ · 1C4B₍₁₆₎ · 7777₍₁₆₎

## Operaciones aritméticas en diferentes bases

Las operaciones aritméticas pueden ser abstraídas de la base que se esté utilizando: independientemente
de la base, los procedimientos son los mismos y solo se debe tener cuidado con la representación de
los números. La suma, la resta, la multiplicación y la división se realizan con los mismos algoritmos
utilizados en decimal.

### Ejercicios resueltos

Binario (suma):

```
        1 1 1 1
        1 1 1 0 1 ₍₂₎
    +   1 0 1 1 1 ₍₂₎
    -------------
    1 1 0 1 0 0   ₍₂₎
```

Binario (multiplicación):

```
          1 0 0 1 ₍₂₎
      ×     1 1   ₍₂₎
      -----------
          1 0 0 1
    + 1 0 0 1
      -----------
      1 1 0 1 1   ₍₂₎
```

Octal (suma):

```
      0 1
      2 2 7 ₍₈₎
    + 5 2 2 ₍₈₎
    ---------
      7 5 1 ₍₈₎
```

Octal (multiplicación):

```
            2 2 2 1 ₍₈₎
        ×     1 2 7 ₍₈₎
        -------------
        1 7 7 6 7
    +   4 4 4 2
    + 2 2 2 1
      ---------------
      3 0 6 5 0 7   ₍₈₎
```

### Ejercicios propuestos

Realizar las siguientes operaciones aritméticas en los sistemas numéricos indicados y verificar los
resultados usando el sistema decimal.

**Binario**

1. 1011101 + 1100111
2. 11101 + 10111
3. 11101 + 10101 + 10111
4. 1001 − 10010
5. 1011 − 10101101
6. 1010111 × 1011
7. 111 × 101
8. 1001 × 11
9. 1011101011010 / 110
10. 111001001 / 101
11. 1010 / 10
12. (111001 + 1010) / 111
13. (110011 × 11) − 100010

**Octal**

1. 1532 + 125
2. 227 + 522
3. 771 + 231 + 111
4. 2121 − 5342
5. 2543 − 1756
6. 10217 × 743
7. 2221 × 127
8. 2323 / 43
9. 56 / 3
10. (127 + 415) − 512
11. (124 × 16) / 12

**Base doce**

1. 5689 + 14A42
2. 4A2 − 9
3. 89A3 − 18
4. 145 × 2A
5. A21219 / 7

**Hexadecimal**

1. ABC32 + 1582
2. A741 − 7F14
3. 5A3 / 7
4. AAF + BCD1
5. 9482 × 14
6. A14 − F14
7. 12 + 14F5
8. 23AF56 / 3B
9. (F141 − A71) + B134
10. (FA01 + 127) / A

## Complemento a la base y a la base menos uno

### Ejercicios resueltos

Las operaciones de complemento a la base y complemento a la base menos uno (o complemento
restringido) son de gran utilidad para implementar circuitos de resta, división, etc.

El complemento de un número _a_ de _n_ dígitos (en cualquier base) se define como:

```
Comp(a) = 10ⁿ − a
```

Donde 10 representa la base (este valor siempre es 10 para todas las bases). Por ejemplo:

```
Comp(27)   = 10² − 27   = 100 − 27   = 73
Comp(27₍₈₎) = (10₍₈₎)² − 27₍₈₎ = 100₍₈₎ − 27₍₈₎ = 51₍₈₎
```

Como 10ⁿ resulta un 1 seguido de _n_ ceros, calcular el complemento genera al menos un arrastre en
el dígito de menor peso. Para evitarlo se usa el complemento a la base menos uno, que decrementa una
unidad antes de la resta:

```
compRest(a) = (10ⁿ − 1) − a

compRest(27)   = (10² − 1) − 27   = 99 − 27   = 72
compRest(27₍₈₎) = (10₍₈₎)² − 1₍₈₎ − 27₍₈₎ = 77₍₈₎ − 27₍₈₎ = 50₍₈₎
```

El complemento a la base se obtiene sumando 1 al complemento restringido, evitando acarreos en la
resta.

Una forma práctica de hallar el complemento restringido es preguntar cuánto le falta a cada dígito
para llegar al valor máximo de la base. Así, `compRest(27) = 72` (al 7 le faltan 2 para llegar a 9,
al 2 le faltan 7); y `compRest(27₍₈₎) = 50₍₈₎` (al 7 le falta 0 para llegar a 7, al 2 le faltan 5).

Caso particular del sistema binario: el complemento restringido consiste en cambiar ceros por unos y
unos por ceros:

```
compRest(1000101010₍₂₎) = 0111010101₍₂₎
```

Para el complemento a la base se suma uno; en binario no hace falta operación de resta alguna.

**La resta mediante sumas.** Partiendo de `comp(a) = 10ⁿ − a` se llega a `b − a = b + comp(a) − 10ⁿ`.
Por ejemplo, `485 − 34 = 451`. Reemplazando −34 por su complemento (completando a 3 dígitos: 034):

```
compRest(034) = 965 → comp(034) = 966
485 + 966 = 1451
```

El resultado está excedido en 10ⁿ (n = 3); restarlo equivale a eliminar el 1 de mayor peso → 451.
Esto sucede siempre que el minuendo sea mayor que el sustraendo. Cuando el minuendo es menor:

```
34 − 485 = −451
compRest(485) = 514 → comp(485) = 515
034 + 515 = 549
```

Como no hay un 1 de mayor peso para eliminar, debe hacerse la resta de 10ⁿ, que equivale a
complementar el resultado de nuevo: `compRest(549) = 450 → +1 = 451`, agregando por convención el
signo menos: **−451**.

**Representación con complemento de los negativos.** Se establece la cantidad de dígitos y se
reserva el dígito de mayor peso para el signo (0 positivo, 9 negativo en decimal). Para `34 − 485`:

```
0034 − 0485
compRest(0485) = 9514 → comp(0485) = 9515
0034 + 9515 = 9549   (resultado final negativo)
```

Comprobación: `compRest(9549) = 0450 → comp = 0451` (valor positivo del resultado). Cuando se trabaja
con formato de complemento para los negativos, no debe volver a complementarse el resultado.

En binario se aconseja trabajar con la representación por complemento de los negativos, reservando un
bit para el signo (0 positivos, 1 negativos). Con tres bits para el número y uno para el signo,
`0111₍₂₎ − 0101₍₂₎ = 0010₍₂₎`:

```
comp(0101₍₂₎) = 1011₍₂₎
0111₍₂₎ + 1011₍₂₎ = 10010₍₂₎   (excedido en 10₍₂₎⁴ → se elimina el primer bit)
= 0010₍₂₎
```

Si el resultado es negativo, `0101₍₂₎ − 0111₍₂₎`:

```
comp(0111₍₂₎) = 1001₍₂₎
0101₍₂₎ + 1001₍₂₎ = 1110₍₂₎
```

Complementando se obtiene el valor positivo: `comp(1110₍₂₎) = 0010₍₂₎`. Cuando se trabaja con
representación complementada de los negativos y la cantidad de dígitos es igual en minuendo y
sustraendo, después de la resta por complementos NO SE DEBE COMPLEMENTAR EL RESULTADO, ya que esa es
la representación del valor de la resta: `0101₍₂₎ − 0111₍₂₎ = 1110₍₂₎`.

### Ejercicios propuestos

Hallar el complemento a la base y a la base menos uno de los siguientes números:

1. 1011101101₍₂₎
2. 174AB23₍₁₆₎
3. 3524₍₈₎
4. 10001010₍₂₎

Realizar las siguientes restas en el sistema binario utilizando el complemento a la base (defina si
trabaja con representación complementada de los negativos o con signo y dígito):

1. 11011011₍₂₎ − 11100011₍₂₎
2. 1110001₍₂₎ − 100100101₍₂₎
3. 110101011₍₂₎ − 101010₍₂₎
4. 101100₍₂₎ − 11101110₍₂₎
5. 10110101₍₂₎ − 1010101₍₂₎
6. 101011₍₂₎ − 11100111₍₂₎

Restar en sistema binario usando complemento a la base menos uno:

1. 10111101₍₂₎ − 1101010₍₂₎
2. 1110001₍₂₎ − 1001001011₍₂₎
3. 110101011₍₂₎ − 101010₍₂₎
4. 101100₍₂₎ − 11101110₍₂₎
5. 10110101₍₂₎ − 1010101₍₂₎
6. 101011₍₂₎ − 11100111₍₂₎
