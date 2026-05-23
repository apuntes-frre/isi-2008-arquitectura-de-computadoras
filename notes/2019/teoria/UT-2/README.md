# Sistemas Numéricos

## Contenido

- [Señales Lógicas y Analógicas](#señales-lógicas-y-analógicas)
- [SISTEMAS DE NUMERACION](#sistemas-de-numeracion)
- [Naturaleza Posicional del Sistema Decimal](#naturaleza-posicional-del-sistema-decimal)
- [Naturaleza Posicional del Sistema Binario](#naturaleza-posicional-del-sistema-binario)
- [FORMATO DE LOS NUMEROS EN LAS MAQUINAS](#formato-de-los-numeros-en-las-maquinas)
- [CODIFICACION DE LA INFORMACION](#codificacion-de-la-informacion)
- [Introducción](#introducción)
- [CODIFICACIÓN DE LA INFORMACIÓN EN LA MÁQUINA](#codificación-de-la-información-en-la-máquina)
- [CODIFICACIÓN DE LA INFORMACIÓN NUMÉRICA](#codificación-de-la-información-numérica)
- [Códigos Ponderados](#códigos-ponderados)
- [Códigos No Ponderados](#códigos-no-ponderados)
- [ALGUNOS CÓDIGOS NÚMERICOS MÁS USUALES](#algunos-códigos-númericos-más-usuales)
- [ALGUNOS COMENTARIOS SOBRE LOS CÓDIGOS](#algunos-comentarios-sobre-los-códigos)
- [CODIFICACIÓN DE LA INFORMACIÓN NO NUMÉRICA](#codificación-de-la-información-no-numérica)
- [Codificación de los Caracteres](#codificación-de-los-caracteres)
- [CARÁCTER](#carácter)
- [PALABRA](#palabra)
- [BYTE](#byte)
- [Representación de los Números](#representación-de-los-números)
- [CODIFICACION DE LAS INSTRUCCIONES](#codificacion-de-las-instrucciones)
- [CODIGOS REDUNDANTES](#codigos-redundantes)
- [Códigos Autodetectores](#códigos-autodetectores)
- [Códigos Autocorrectores](#códigos-autocorrectores)
- [Control y Corrección](#control-y-corrección)

## Señales Lógicas y Analógicas

El procesamiento de la información en un calculador electrónico consiste en tratar, transferir y memorizar señales eléctricas. En los *calculadores analógicos* se utilizan señales de variación continua. Por ejemplo, una magnitud cualquiera será representada por una tensión eléctrica, tensión que deberá mantenerse, durante el procesamiento, tan proporcional como sea posible a la magnitud representada. En los *calculadores digitales*, la información procesada que es de tipo binario, está materializada por señales eléctricas de dos estados, que pueden hacerse muy distintos uno del otro, por ejemplo un nivel de tensión para el estado 1 y otro, muy diferente para el estado 0.

Inmediatamente resalta una primera ventaja de la representación digital respecto de la analógica: la información digital se transmite mejor. Es bastante fácil realizar sistemas con dos estados estables, capaces de memorizar un bit. Por el contrario memorizar el valor de una señal eléctrica es mucho más difícil (se memorizan muy temporalmente las tensiones eléctricas cargando condensadores).

Lógica de Nivel

Puede representarse la información digital elemental sobre una línea eléctrica, manteniendo una tensión A para materializar el 1 lógico y una tensión B para el 0 lógico. En realidad no son valores precisos de la tensión, sino franjas alrededor de estos valores (figura 1). Se llama “zona prohibida” a la zona intermedia, en ella, el valor lógico de la señal eléctrica es indeterminado.

Se dirá que se trabaja con *lógica positiva* cuando la tensión que representa el 1 lógico es superior a la tensión del 0 lógico y, en caso contrario, se trabajará con *lógica negativa*. La mayoría de las veces el 0 lógico será la masa o la tensión 0 voltios (figura 2). La elección de los *niveles* de tensión resulta de la tecnología escogida para la realización de los circuitos.

Se dice que se trabaja con una lógica de impulsos cuando la magnitud eléctrica representativa de la información dura un tiempo muy corto. Una primera técnica consiste en utilizar un impulso positivo para representar un 1, un impulso negativo para el 0, y la tensión 0 para la ausencia de información (figura 3).

La mayoría de las lógicas de impulsos emplean solamente impulsos positivos (o negativos) e imponen leer las informaciones en instantes dados, t<sub>1</sub>, t<sub>2</sub>, t<sub>3</sub>, etc. Si un “top” coincide con un impulso, se trata de un 1 lógico, en caso contrario es un 0 lógico (figura 4).

Convencionalmente se anotan las líneas de nivel por una semiflecha, las líneas de pulsos por una flecha. Una señal eléctrica analógica puede variar a lo largo del tiempo de una manera continuada, gradual, sin saltos bruscos, entre dos valores extremos, que determinan un rango, y en un instante dado puede tener un valor dentro de dicho rango.

## SISTEMAS DE NUMERACION

Para empezar conviene tener presente que, en cualquier sistema de representación, un mismo conjunto de símbolos puede tener distintos significados según la convención que se siga.

Ejemplo: Los diez símbolos decimales pueden usarse para distintas convenciones de representación 170527 puede significar:

1.  el número decimal ciento setenta mil quinientos veintisiete.
2.  La fecha de nacimiento 17 de mayo de 1927
3.  17 horas 05’27”, etc.

Este multisignificado también existe para las representaciones binarias numéricas que se dan dentro de las máquinas.

Ejemplo: una combinación binaria como 10000110, puede significar:

1.  El número decimal equivalente 134 si corresponde a un número natural
2.  El número decimal equivalente 86 si es un número BCD
3.  El número que identifica una celda de memoria, etc.

*Números con precisión finita:* otra consideración a tener en cuenta en la representación y operaciones de números en una máquina está relacionada con el hecho de que los mismos solo pueden constar de una cantidad fija de dígitos.

*Módulo:* es el número máximo de enteros diferentes que pueden representarse en un registro físico. La noción de módulo es útil para poner formalmente de manifiesto la capacidad limitada de representación de los dispositivos físicos usados.

## Naturaleza Posicional del Sistema Decimal

La denominación “decimal” o de “base diez”, se refiere a los diez dígitos o símbolos (0 a 9) que combinados permiten simbolizar los números, conforme a una convención que atribuye un valor individual y otro posicional a cada símbolo.

Cada dígito indica cuantos subconjuntos (0,1,..,9) que agrupan igual número de elementos (uno, diez, cien, mil, …) se han utilizado para formar un número decimal. Existen tantos tipos distintos de subconjuntos como dígitos contenga un número. Por ejemplo, los símbolos 107 implican que el número de elementos representados está formado por un subconjunto que agrupa cien, mas siete subconjuntos que solo contienen un elemento cada uno, no existiendo ningún subconjunto de diez elementos.

107 = 1.100 + 0.10 + 7.1 = 1.10<sup>2</sup> + 0.10<sup>1</sup> + 7

Características de un Sistema Numérico Posicional:

- Consta de un número finito de símbolos distintos, número que define la “base” o “raíz” de cada sistema.
- Cada símbolo aislado representa un número especificado de unidades.
- Existe un símbolo (cero) para indicar la ausencia de elementos a representar.
- Los símbolos pueden ordenarse en forma monótona creciente.
- Formando parte de un número compuesto por varios símbolos, un mismo símbolo tiene una significación o “peso” distinto según su posición.
- La posición extrema derecha corresponde a unidades (peso uno), a partir de ella, cada posición tiene el peso de la que está a su derecha multiplicada por la base.

## Naturaleza Posicional del Sistema Binario

El método empleado es el mismo que el usado para base diez, solo varía el tamaño de los grupos, y el hecho de estar permitido formar un solo agrupamiento de cada tamaño. En consonancia con ello, únicamente existen dos símbolos: 1 y 0, cuyo significado es el mismo que los respectivos símbolos decimales.

Con los mismos se puede representar cualquier número, resultando así un sistema numérico en *base dos* o *binario.*

Cada uno de los símbolos que forman un número binario se llama “dígito binario” o BIT (de “binary digit”).

1101011 = 1.2<sup>0</sup> + 1.2<sup>1</sup> + 0.2<sup>2</sup> +1.2<sup>3</sup> + 0.2<sup>4</sup> + 1.2<sup>5</sup> + 1.2<sup>6</sup> = 107

Luego 1101011b = 107d (“b” binario y “d” decimal)

**Base:** Determina la cantidad de símbolos distintos para representar los números, “los símbolos son finitos pero los números no”.

**Complemento** A la base (en binario complemento a 2)

 A la base -1 (En binario complemento a 1)

**Complemento a la base:** Es lo que le falta al número para llegar a la base, es decir, la base – el número, el 1 seguido de tantos ceros como dígitos tenga el número. Potencia de la base inmediatamente superior al número.

**Complemento a la base -1:** se define como el complemento a la base, pero restando 1, es decir, se obtiene restando 1 a la base. En el complemento a 1 los unos se cambian por ceros, y los ceros por unos.

**Tipos de Datos:** Las computadoras digitales manejan 4 tipos básicos de datos.

- Números enteros con signo (representación numérica).
- Números reales con signo (representación numérica).
- Número de decimales codificados en binario BCD (representación numérica).
- Caracteres (representación alfanumérica).

El número de bits que se usan para representar cada uno de estos tipos de datos y el significado de cada uno varía según el tipo de dato a representar y el sistema computacional que se utilice (HW y SW).

## FORMATO DE LOS NUMEROS EN LAS MAQUINAS

Un operador aritmético no puede procesar más que números que le sean presentados según uno o unos *formatos* bien definidos.

Componentes del Formato:

- *Dimensión:* Las máquinas de palabra, que trabajan generalmente en sistema binario, admiten formato de *longitud fija*, según que la información ocupe una palabra, media palabra, dos palabras, etc., se hablará de *longitud simple, media longitud, doble longitud*, etc. Las máquinas de carácter, que operan en sistema decimal, trabajan generalmente con formatos de *longitud variable*, bajo los cuales un número va codificado con un número variable de caracteres.

- *Formato*: analizaremos tres tipos de formato, el *formato fijo* o formato en coma fija y el *formato flotante* o formato en coma flotante, para los números binarios, por otro lado, los formatos de longitud variable, para los números decimales.

La Coma Fija

Es la manera más natural de escribir un número binario en una palabra de memoria: Los números se consideran como enteros y se le deja al programador el cuidado de situar la coma. Pueden representarse los números negativos de acuerdo con uno de los tres convenios.

1.  Signo-magnitud
2.  Complemento a 1
3.  Complemento a 2

La forma más simple de representación que emplea un bit de signo es la representación *signo-magnitud*. En una palabra de N bits, los N-1 bit menos significativos almacenan la magnitud del entero; mientras que el bit más significativo indica el signo del número, siendo 0 la representación positiva y 1 la negativa.

**0**0010010 = +18

**1**0010010 = -18

Ahora, una palabra de 8 bits puede representar valores en un rango -127 a +127.

Desventajas:

- La adición y la sustracción requieren considerar ambos signos y sus magnitudes relativas para poder llevar a cabo la operación.
- Existen 2 representaciones para el cero.

**0**0000000 = 0<sub>10</sub>

**1**0000000 = -0<sub>10</sub>

Hay otras dos representaciones que utilizan el bit más significativo para el signo. Difieren una de la otra y de la representación *signo-magnitud*, en la manera que los otros bits se interpretan. Estas representaciones se conocen como *complemento a 1* y *complemento a 2*. Ambas permiten algoritmos más eficientes para la adición y sustracción. La representación de *complemento a 2*, además, tiene una sola representación para el cero.

Para llevar a cabo la operación de *complemento a 1* sobre el conjunto de dígitos binarios solo hay que reemplazar los dígitos 0 con dígitos 1 y los dígitos 1 con dígitos 0.

Así:

X = 01010001

Complemento a 1 de X = 10101110

La representación en *complemento a 1* de los dígitos binarios es como sigue. Los enteros positivos se representan de la misma manera como en la representación *signo-magnitud*. Un entero negativo está representado por el *complemento a 1* de un entero positivo con la misma magnitud.

Por ejemplo:

18 = 00010010

-18 = Complemento a 1 de 18 = 11101101

Puesto que todos los enteros positivos tienen el bit más significativo igual a 0, todos los números negativos tienen necesariamente el bit más significativo igual a 1. De esta manera, el bit de más a la izquierda sigue funcionando como bit de signo.

La operación de *Complemento a 2* consiste en dos pasos:

1.  Llevar a cabo la operación de *complemento a 1*.
2.  Tratar el resultado como un entero binario sin signo, sumarle 1.

La representación en *complemento a 2* de enteros positivos es la misma como en las representaciones de *signo-magnitud* y *complemento a 1*. Un número negativo es representado por el complemento del entero positivo con la misma magnitud. Por ejemplo:

18 = 00010010

Complemento a 1= 11101101

*+ 1*

-18 = Complemento a 2 de 18 = 11101110

Esta representación tiene una anomalía no encontrada con *signo-magnitud* o *Complemento a 1*. El patrón de bits 1 seguido por N-1 ceros es su propio *complemento a 2*. Para mantener consistencia en el bit de signo, a este patrón de bits se le asigna el valor -2<sup>*N*</sup>.

Por ejemplo, para las palabras de 8 bits:

-128 = 10000000

Complemento a 1 = 01111111

*+ 1*

10000000 = -128

Con esta interpretación, todos los enteros positivos tienen el bit más a la izquierda en 0 y todos los negativos tienen el bit más a la izquierda en 1. De esta manera el bit más significativo sigue funcionando como bit de signo.

En las representaciones de *Complemento a 1* y *Complemento a 2* encontramos que el negativo del negativo de ese número es el mismo ( -(-18) = 18 )

Si se representaran números binarios sin signo, para ***n*** bits ****se obtendrían 2<sup>n</sup> combinaciones; vale aclarar que todas estas combinaciones son positivas. ****Ahora bien, cuando se representan números con signo, la mitad del rango corresponde a números positivos y la otra mitad a números negativos (signo-magnitud y complemento a la base menos 1), es decir, desde -2<sup>n-1</sup> + 1 hasta 2<sup>n-1</sup> – 1; para el caso de complemento a la base es necesario añadir un elemento más a la parte negativa, ya que existe una sola representación para el 0.

**En las operaciones en coma fija se dan algunas peculiaridades. La suma de dos números fijos puede ocasionar lo que se llama** ***desbordamiento*** **o** ***sobrepasamiento de capacidad*****.**

**La multiplicación de dos números de** ***n*** **cifras da un número de** ***2n*** **cifras, como máximo, que será representado en coma fija de doble longitud.**

|     |     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|-----|
|     | 0   | 1   | 1   | 0   | 1   | 0   |
| \+  | 0   | 1   | 0   | 0   | 1   | 0   |
| 1   | 0   | 0   | 1   | 1   | 0   | 0   |

Características de la representación en coma fija:

- *Rango*: se determina por la diferencia entre el mayor y el menor elemento.
- *Precisión*: es la distancia entre dos números consecutivos en una serie numérica.
- *Error*: se obtiene dividiendo la precisión por 2.

La Coma Flotante

Con la notación en coma fija puede representarse un rango de números enteros centrados en el cero. También pueden representarse números decimales asumiendo una coma fija. El problema de esta representación es que los números muy grandes o muy pequeños requieren mucho espacio. Esta limitación se soluciona mediante otra representación llamada *coma flotante*, la cual consiste en representar los números bajo la forma: SM x α<sup>E</sup> donde

S: el signo del número

M: la mantisa del número

E: Es el exponente del número

α: se escoge generalmente igual a la base del sistema de numeración

Esta notación es corriente en la escritura cuando representamos 125000000 por 125x10<sup>6</sup>. Tal representación no es única, puesto que también puede escribirse: 12,5x10<sup>7</sup> ó 1250x10<sup>5</sup>, etc. De entre estas representaciones se selecciona una, llamada *normalizada*, que permite conservar el mayor número de cifras significativas. Para normalizar un número se desplaza su mantisa hacia la izquierda o derecha según corresponda hasta que el primer digito sea significativo, y se reduce o aumenta el exponente, respectivamente, en un número igual al número de desplazamientos que han sido necesarios. (en hipótesis de que el exponente expresa una potencia de 2).

|     |     |     |     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|-----|-----|-----|
| 0   | 0   | 0   | 1   | 2   | 5   |     | 0   | 6   |
| 0   | 0   | 1   | 2   | 5   | 0   |     | 0   | 5   |
| 0   | 1   | 2   | 5   | 0   | 0   |     | 0   | 4   |
| 1   | 2   | 5   | 0   | 0   | 0   |     | 0   | 3   |

En virtud de la normalización que sigue a toda la operación, la mantisa se ve siempre reajustada, de tal suerte que los desbordamientos de capacidad no pueden afectar más que al exponente. Además del desbordamiento de capacidad por exponente demasiado grande, puede ocurrir un *sub-desbordamiento de capacidad* cuando el exponente se hace demasiado pequeño para poder ser representado. La mayoría de las máquinas sustituyen entonces el resultado correspondiente por cero, lo que supone una excepción a las reglas de normalización.

Obsérvese que el número de dígitos de la mantisa está directamente ligado a la precisión de los cálculos, mientras que el número de dígitos del exponente determina los valores extremos que la máquina es capaz de representar.

Hay diferentes convenios de representación de los números flotantes binarios en la máquina. De manera general se sitúan las informaciones más significativas en cabeza: primeramente, el signo, luego el exponente y por último la mantisa.

La mantisa puede ser considerada como entera, o como fraccionaria. 125x10<sup>6</sup> se escribirá según el convenio utilizado.

Representación Binaria

Se sigue el mismo procedimiento anterior con la particularidad de que a continuación de la coma decimal siempre va un 1, por lo cual no es necesario representarlo (se sabe que está ahí). Así es posible reducir el almacenamiento en un bit.

Cuando es necesario utilizar el número, se lo toma de la memoria y se le incorpora el 1. El bit eliminado se conoce con el nombre de bit implícito.

1110101 = 0,1110101 x 2<sup>7</sup>

Considerando el bit implícito la mantisa se almacenará como 0,110101

Cadenas Decimales de Longitud Variable

Los dígitos decimales van generalmente codificados por los cuatro bits de menor peso de los caracteres de 6 o de 8 bits. También se encuentran representaciones condensadas con dos dígitos decimales por octeto. Un número se forma con una cadena de tales caracteres. El signo del número puede ser codificado por un carácter y situado en la cabeza o, más corrientemente, en la cola de la cadena de caracteres que lo constituye. Asimismo puede ser incluido en los bits de mayor peso del primero o del último carácter significativo.

Estas cadenas de caracteres son generalmente de longitudes variables y direccionadas por su último carácter que será tratado en primer lugar para considerar los posibles arrastres. El primer carácter puede tener una marca de fin de número en sus bits de mayor peso; en ausencia de marca de fin de número, la instrucción debe precisar al calculador la longitud de la cadena.

## CODIFICACION DE LA INFORMACION

## Introducción

Para poder transmitir información existen dos problemas fundamentales: el *Hardware* ****y el *Lenguaje de Comunicación*. Haciendo una analogía entre las computadoras y la comunicación humana podemos decir que, si bien todas las personas del mundo tienen el mismo hardware para la comunicación hablada (labios, lengua, dientes y el resto del complejo aparato bucal) para transmitir y los oídos para recibir, la comunicación oral es posible solamente cuando dos personas conocen el mismo lenguaje, es decir la misma manera de **codificar la información**.

Así como el habla sería imposible sin lenguajes comunes, la comunicación entre computadoras sería imposible sin coordinación de códigos de caracteres.

Todas las computadoras digitales actuales usan un **lenguaje binario** para representar la información, internamente. Debido a que algunos de los dispositivos con los que se deben comunicar las computadoras están diseñados para uso humano (específicamente teclados, monitores e impresoras), es importante que estos **periféricos** utilicen un código de comunicación compatible con la comunicación humana.

Existen varios métodos para alcanzar dicha compatibilidad y cada uno utiliza un modo diferente de codificar los números y las letras, que conforman la base de la comunicación escrita entre las personas.

Actualmente es frecuente encontrar en los **sistemas de cómputo**, dispositivos provistos por distintos fabricantes. La posibilidad de conectar estos dispositivos existe únicamente si éstos utilizan un código común para la transmisión y recepción de la información.

Son claras las ventajas de conseguir que todas las computadoras utilicen el mismo código de comunicación. Aún cuando la calidad de los códigos varía enormemente, casi cualquier estándar universal sería mejor que ninguno. Si bien hay códigos que prácticamente son aceptados por todos los fabricantes, aún no existe un estándar que optimice el aprovechamiento tanto de los recursos del hardware como las nuevas teorías sobre codificación e información.

En sentido genérico **CÓDIGO** significa: Sistema de signos y de reglas que permite formular y comprender un mensaje.

La codificación consiste en establecer una ley de correspondencia, llamada **CÓDIGO**, entre las informaciones por representar y las posibles configuraciones binarias, de tal manera que a cada información corresponda una y generalmente solo una, configuración binaria.

El proceso de **CODIFICAR** significa: Transformar, mediante las reglas de un código, la formulación de un mensaje.

Llamamos **CODIFICACIÓN** al proceso de convertir un símbolo complejo en un grupo de símbolos más simples. Ejemplo: convertir una letra del alfabeto en un código de cinco bits.

**DECODIFICAR**: Aplicar inversamente las reglas de su código a un mensaje codificado para obtener la forma primitiva de este.

**DECODIFICACIÓN** es el proceso inverso al de codificación, se convierte a un código donde la cantidad de símbolos es menor, pero cada una contiene más información.

**TRANSCODIFICACIÓN:** Aplicación de un cambio de código a una información ya codificada. Ejemplo: EBCDIC a ASCII.

**BITS:** Teniendo en cuenta que las computadoras manejan un lenguaje binario analizaremos los **DÍGITOS BINARIOS** como caracteres para comunicación de datos.

La condición binaria es la que posee una calidad BIVALUADA. En el sistema binario de numeración esas condiciones están representadas por los dígitos 0 y 1. Se denomina **BIT** (contracción de **BI**NARY ****DIGI**T**) al dígito binario, independientemente del valor asignado (0 o 1). Un **BIT** es la unidad de información más pequeña posible, que no puede tomar más que dos valores, generalmente 1 ó 0.

Los dígitos binarios llevan, ambos, la misma cantidad de información, ya que la presencia de uno significa la ausencia del otro.

Un proceso fundamental en la codificación binaria es determinar la cantidad de BITS necesarios para representar las informaciones. De manera que podamos identificar una entre varias posibles.

Como un bit puede ser l o 0, podremos utilizarlos para seleccionar una información entre dos; con dos bits, una entre cuatro; tres bits una entre ocho; etc. Las posibilidades aumentan como potencias de dos:

Un bit 2<sup>1</sup> = 2 elecciones

Dos bits 2<sup>2</sup> = 4 elecciones

Tres bits 2<sup>3</sup> = 8 elecciones

Si quisiéramos conocer cuantos bits necesitamos para una de ocho situaciones utilizamos logaritmos en base 2, así: log <sub>2</sub> 8 = 3.

En general el número de bits (I) que necesitaremos para poder codificar una determinada cantidad de informaciones (N) estará determinado por:

I = Log <sub>2</sub> N

Como ejemplo, para poder representar en forma binaria los 26 caracteres de nuestro alfabeto necesitaríamos:

I = Log <sub>2</sub> 26 = 4,7 bits I = 5 bits

## CODIFICACIÓN DE LA INFORMACIÓN EN LA MÁQUINA

Analizaremos los siguientes puntos:

1.  Codificación de la Información Numérica

2.  1.  Códigos Ponderados
    2.  Códigos No Ponderados

3.  Codificación de la Información No Numérica

4.  1.  Codificación de los Caracteres

        1)  1.  1.  Caracteres Imprimibles
                2.  Caracteres No Imprimibles

5.  1.  Codificación de las Instrucciones

## CODIFICACIÓN DE LA INFORMACIÓN NUMÉRICA

Estudiaremos la representación de los símbolos del sistema decimal de numeración mediante símbolos binarios (BIT).

¿Cuántos bits necesitarnos para representar los 10 símbolos del sistema decimal de numeración?

- I = Log <sub>2</sub> l0 = 3,162 … ≡ 4

Esto nos indica que cualquier código que utilicemos para representar los números del sistema decimal precisará, como mínimo, 4 Dígitos Binarios (Bits). Cuando el código utilice más dígitos que los que necesita lo denominaremos **CODIGO REDUNDANTE**.

## Códigos Ponderados

Se denomina código ponderado a aquel que respeta, para la representación de cada dígito decimal, el “peso” que corresponde a cada dígito binario de acuerdo a la posición que ocupa. Ejemplos: BCD (8421), AIKEN (2421), 84-2-1.

**Nota I: En cualquiera de los códigos numéricos (ponderados y no ponderados) un número decimal se codificará cada dígito decimal por separado.**

Ejemplo: el número 345 se codificará

 3 4 5

En BCD 0011 0100 0101 345<sub>(10</sub> = 001101000101<sub>(BCD</sub>

En AIKEN 0011 0100 1011 345<sub>(10</sub> = 001101001011<sub>(AIKEN</sub>

Nota II: Si bien los símbolos utilizados se corresponden con los del sistema binario, la representación codificada no tiene nada que ver con el SISTEMA BINARIO DE NUMERACION.

- **BCD (Pesos 8, 4, 2, 1)**

El código **BCD** (DECIMAL CODIFICADO BINARIO) respeta para cada dígito decimal el “peso” que corresponde a cada dígito binario de acuerdo a la posición que ocupa, teniendo en cuenta el “peso” asignado en el sistema binario de numeración.

- 2, 4, 2, 1

**Nota III:** El código 2, 4, 2, 1 permite dos combinaciones de los dígitos 2, 3, 4, 5, 6 y 7. Cualquiera es válida, más aún, en un mismo número de varios dígitos iguales pueden usarse codificaciones distintas.

**AIKEN (Pesos 2, 4, 2, 1):** Construcción de la tabla de código Airen

<table>
<tbody>
<tr>
<td></td>
<td></td>
<td colspan="4">Aiken</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td>2</td>
<td>4</td>
<td>2</td>
<td>1</td>
<td></td>
<td>2</td>
<td>4</td>
<td>2</td>
<td>1</td>
</tr>
<tr>
<td>0</td>
<td></td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>1</td>
<td></td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>2</td>
<td></td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>0</td>
<td></td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>0</td>
</tr>
<tr>
<td>3</td>
<td></td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td></td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td>4</td>
<td></td>
<td>0</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td></td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>0</td>
</tr>
<tr>
<td>5</td>
<td></td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td></td>
<td>0</td>
<td>1</td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td>6</td>
<td></td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td></td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>0</td>
</tr>
<tr>
<td>7</td>
<td></td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td></td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>1</td>
</tr>
<tr>
<td>8</td>
<td></td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>0</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>9</td>
<td></td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

- **Exceso en Tres**

La representación en el código exceso de 3, cada dígito decimal se representa como en BCD pero excedido en 3. Ejemplo la representación del 2 es la BCD del 5.

## Códigos No Ponderados

En estos códigos la representación de cada dígito decimal es en principio arbitraria o responde a características que no son el “peso” de acuerdo a la posición que ocupan. Ejemplos GRAY.

- **Construcción de la tabla del Código de GRAY**

1.  Se colocan los dos bits (0 y 1) y se traza una línea debajo de ellos (espejo), se copian los bits como si se reflejaran en dicho espejo.

 0

1

1

0

2.  Se completa la siguiente columna con 1 por debajo del espejo y con 0 por encima del mismo.

0 0

0 1

1 1

1 0

3.  Se repite la operación de reflejado con los cuatro números obtenidos.

 0 0

0 1

1 1

1 0

1 0

1 1

0 1

0 0

4.  Se completa la tercera columna con 1 debajo del espejo y 0 por encima.

 0 0 0

0 0 1

0 1 1

0 1 0

1 1 0

1 1 1

1 0 1

1 0 0

5.  Se vuelve a realizar la operación hasta completar los diez dígitos.

## ALGUNOS CÓDIGOS NÚMERICOS MÁS USUALES

|  |  |  |  |  |  |  |
|----|----|----|----|----|----|----|
| Dígito Decimal | B C D (8421) | Exceso de tres | A I K E N (2421) | 8 4 -2 -1 | BIQUINARIO | Código de Gray |
| 0 | 0000 | 0011 | 0000 | 0000 | 0100001 | 0000 |
| 1 | 0001 | 0100 | 0001 | 0111 | 0100010 | 0001 |
| 2 | 0010 | 0101 | 0010 | 0110 | 0100100 | 0011 |
| 3 | 0011 | 0110 | 0011 | 0101 | 0101000 | 0010 |
| 4 | 0100 | 0111 | 0100 | 0100 | 0110000 | 0110 |
| 5 | 0101 | 1000 | 1011 | 1011 | 1000001 | 0111 |
| 6 | 0110 | 1001 | 1100 | 1010 | 1000010 | 0101 |
| 7 | 0111 | 1010 | 1101 | 1001 | 1000100 | 0100 |
| 8 | 1000 | 1011 | 1110 | 1000 | 1001000 | 1100 |
| 9 | 1001 | 1100 | 1111 | 1111 | 1010000 | 1101 |

## ALGUNOS COMENTARIOS SOBRE LOS CÓDIGOS

1.  Los códigos Exceso de 3, el 2421 y 84-2-1 son autocomplementarios. o sea que el complemento a 9 del número decimal se obtiene cambiando los ceros por unos y los unos por ceros.

2.  El código Biquinario es un CODIGO REDUNDANTE donde cada dígito decimal se representa con cinco ceros y dos unos.

3.  El código de Gray o BINARIO REFLEJADO tiene la particularidad que de un dígito decimal al siguiente cambia siempre un solo dígito por vez.

El código de Gray y Biquinario son códigos NO PONDERADOS.

## CODIFICACIÓN DE LA INFORMACIÓN NO NUMÉRICA

## Codificación de los Caracteres

Luego de ver como pueden representarse los números, analizaremos ahora como extender el sistema de codificación al conjunto de signos de la máquina de escribir: letras, signos de puntuación, operadores y caracteres especiales.

**Condiciones que se Imponen para la Codificación de Caracteres**

1.  La representación debe englobar a las de las cifras en una de las formas descriptas (BCD, 2421, etc.) y permitir distinguir las cifras rápidamente de los otros caracteres.
2.  La representación debe permitir añadir nuevos caracteres específicos para una aplicación determinada.
3.  En el caso de las transmisiones, la representación debe incluir un sistema de redundancia que permita la detección de errores.

## CARÁCTER

El concepto de caracter aparece como la cantidad de BITS necesarios para representar los diferentes símbolos del alfabeto (letras, cifras, signos de puntuación, etc.).

De acuerdo al código utilizado cada caracter puede codificarse con un número variable de BITS, pero dentro de un sistema todos los caracteres se representan con el mismo número de bits.

El código ASCII se definió inicialmente con 6 bits, esto permitía representar 2<sup>6</sup> = 64 caracteres. Posteriormente la ANSI (Instituto Nacional Norteamericano de Normas) definió un nuevo ASCII (que se mantiene como norma) de 7 bits. Esta nueva definición permite codificar 128 caracteres; haciéndolo más apto, fundamentalmente para la transmisión donde parte de los “caracteres” codifican funciones de control.

El código EBCDIC creado por IBM utiliza 8 bits para representar cada caracter.

## PALABRA

La palabra es un conjunto de caracteres, fijo o variable, según el caso, que la computadora trata como unidad.

Es una unidad de información de rango superior al caracter. Generalmente contiene un número entero de caracteres.

La palabra es la unidad de información procesada por la máquina.

## BYTE

El término BYTE (octeto), se utiliza para describir un conjunto de 8 bits consecutivos que se toman como unidad.

El BYTE muchas veces no es práctico para manipular datos en problemas de programación, recurriéndose al concepto de PALABRA (WORD), de acuerdo a la siguiente relación:

1 BYTE = 8 bits

1 PALABRA = 2 Bytes

1 DOBLE PALABRA = 4 Bytes

1 CUADRUPLE PALABRA = 8 Bytes

1 DECABYTE = l0 Bytes

***Otras agrupaciones de bytes:*** PARRAFO = 16 Bytes

PAGINA = 256 Bytes

SEGMENTO = 64 Kbytes

El KILOBYTE (KB): Unidad de capacidad de memoria que representa 2<sup>10</sup> unidades de información, por lo tanto una memoria de 1 KB podrá al maceran 1024 caracteres.

**CODIGO EBCDIC (Expanded Binary Code Decimal Interchange Code)**

Este código fué diseñado y utilizado exclusivamente por IBM. Su importancia radica en que sirvió como base para los códigos posteriores normalizados.

Utiliza 8 dígitos binarios para representar cada caracter. La correspondencia entre las informaciones por representar la correspondiente secuencia binaria se encuentra en tablas con distintos formatos.

Con respecto a los caracteres alfabéticos y signos de puntuación no tiene características que lo destaquen, salvo que podemos encontrar pequeñas alteraciones al ser utilizados en países con distintos alfabetos.

**Representación de la Información Numérica (EBCDIC)**

Cada dígito decimal es representado internamente con 8 bits, distribuidos de la siguiente forma:

|        |        |
|--------|--------|
| ZONA   | DIGITO |
| 4 Bits | 4 Bits |

***ZONA:*** Ocupa los 4 bits de orden superior del Byte, tiene una secuencia binaria fija para cualquier número: 1111<sub>(2</sub> = F <sub>(16</sub>

***DIGITO:*** En este espacio se representa el número decimal codificado en BCD.

Los datos numéricos codificados en **EBCDIC con zona**, no son técnicamente aptos para ser procesados aritméticamente. Si necesitamos realizar operaciones aritméticas con ellos, se debe eliminar la parte correspondiente a la ZONA de cada byte. Esta operación se llama **empaque** y la información resultante, información **empacada** (**empaquetada**) o decimal sin zona. Los datos numéricos con zona se denominan información **desempacada** o **zoneada**.

EJEMPLO: Queremos representar el número 36945 en EBCDIC

|     |     |     |     |     |     |     |     |     |     |                            |
|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|----------------------------|
| F   | 3   | F   | 6   | F   | 0   | F   | 4   | F   | 5   | Decimal con Zona (zoneado) |

|     |     |     |     |     |     |     |     |     |     |                             |
|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----------------------------|
| 0   | 0   | 0   | 0   | 3   | 6   | 0   | 4   | 5   | F   | Decimal sin Zona (empacado) |

Medio Byte correspondiente al signo

**F o C (positivo), B o D (negativo)**

|     |     |     |     |     |     |     |     |     |     |                      |
|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|----------------------|
| 0   | 0   | 0   | 0   | 3   | 6   | 0   | 4   | 5   | D   | = -36,045 (empacado) |

En las representaciones internas de memoria, de los números, el punto decimal (coma) no se representa, queda implícitamente considerado en el lugar correspondiente, nunca forma parte física de la cifra, es el programador quien debe tenerlo en cuenta cuando efectúe la salida de los resultados.

**CODIGO ASCII (American Standard Code for Information Interchange)**

Se trata de un código que utiliza 7 bits para representar cada caracter. Parte de las configuraciones binarias son utilizadas para codificar funciones de control.

La mayor parte de las máquinas actuales utilizan este código normalizado, pero generalmente agregar un octavo bit, que les permite extender el código para representaciones no previstas o para utilizarlo como bit de control de paridad en las transmisiones.

El éxito de este código se basa en que cumple con todas las condiciones impuestas para la codificación de caracteres:

- Utiliza relaciones para establecer el código.

- Los valores correspondientes a las letras de alfabeto y a los restantes caracteres, siguen una secuencia binaria continua, la computadora no tiene que dejar su propio lenguaje binario para realizar operaciones secuenciales con esos caracteres.

- Agrupamiento de las funciones de control, con solo analizar los dos primeros bits de una combinación cualquiera codificada, la computadora puede determinar si se trata de una función de control (dos ceros) o de un caracter (uno de los dos no es cero).

## Representación de los Números

En este código, al igual en el EBCDIC, la representación de la información numérica contempla representar los símbolos del sistema decimal de numeración en forma binaria. Cada dígito se codifica con 7 bit que también se encuentran asociados en dos grupos ZONA Y DIGITO.

La zona es siempre 011 y dígito corresponde a la representación BCD del número.

Aquí surge el mismo inconveniente visto en el código EBCDIC, la dificultad para realizar operaciones matemáticas con los números representados con la ZONA, la solución es la misma que la indicada para el código anterior. Como la mayor parte de las máquinas utilizan 8 bits para cada dígito no surgen conflictos al producirse el EMPAQUE.

## CODIFICACION DE LAS INSTRUCCIONES

La codificación de las instrucciones se desarrollará en conjunto con la Arquitectura del procesador.

## CODIGOS REDUNDANTES

Es difícil pensar en un equipo que funcione sin fallas durante un tiempo indefinido. Para cualquier máquina se define un Tiempo Medio Entre Fallas (MTBF), el objetivo de los desarrollos tecnológicos es incrementar ese tiempo.

Teniendo en cuenta esa premisa, es de esperar que la información pueda verse alterada en transcurso de la transmisión o almacenamiento, si nuestro equipo tiene la posibilidad de detectar o, mejor aún, corregir esas modificaciones es evidente que aumentará la confiabilidad del mismo. Estos códigos utilizan un número de bits superior al estrictamente necesario para codificar la información.

## Códigos Autodetectores

Código en el que mediante un determinado número de bits de redundancia se puede detectar si la información recibida es correcta o no. El ejemplo mas clásico de este tipo de códigos es de CONTROL DE PARIDAD.

- **Control de Paridad**

Este código, si bien no permite detectar errores dobles, es el más utilizado debido a su simplicidad y a que en los ordenadores la probabilidad de que ocurra un error es muy pequeña, por lo tanto que ocurran 2 es mucho menos probable.

Consiste en agregar a los bits de información transmitidos un bit mas (generalmente el primero de la izquierda), que hace que la cantidad de unos transmitidos sea PAR (PARIDAD PAR) o IMPAR (PARIDAD IMPAR).

## Códigos Autocorrectores

Mediante el uso de estos códigos, el receptor puede determinar si la información recibida es correcta o no y en este caso corregir el error producido durante la transmisión.

- **Control 2 en 3**

Para transmitir una información cualquiera de “**n**” bits, se envían 3 veces esos “**n”** bits, en forma sucesiva. El receptor de la información, al efectuar el análisis de la misma, se le puede presentar tres situaciones distintas:

1)  Las tres son idénticas. La información se toma como correcta.

2)  Dos son iguales y una distinta. El código se comporta como **AUTOCORRECTOR**, selecciona una de las dos iguales y la toma como correcta.

3)  Las tres son distintas. El código se comporta como **AUTODETECTOR**, la máquina detecta que hay error pero no puede determinar cual es la información correcta.

    - **Códigos de Hamming**

Codificación

Estos códigos permiten detectar y corregir uno o más errores producidos durante la transmisión para palabras de cualquier número de bits. Analizaremos el método para construir un código de Hamming para corregir un solo error.

El primer paso consiste en determinar, para un código de “**i**” dígitos binarios de información, cuantos bits de de control de paridad “**p**” son necesarios para detectar y corregir un error único. Si consideramos que tenemos **i** dígitos de información y **p** bits de control y con la premisa que los casos que se puede presentar son de ningún error o un solo error por vez, tendremos **i + p + 1** condiciones que deben identificarse usando los **p** bits de control de paridad. Teniendo en cuenta que con **p** bits podemos formar 2<sup> p</sup> combinaciones, entonces la cantidad de bits de control de paridad debe ser tal que satisfaga que:

2<sup> p</sup> ≥ i + p + 1

Mediante esta expresión podemos construir la siguiente tabla:

|     |     |     |     |     |     |     |     |     |     |     |     |     |     |                     |
|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|---------------------|
| i   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  | 11  | 12  | …   | Bits de información |
| p   | 2   | 3   | 3   | 3   | 4   | 4   | 4   | 4   | 4   | 4   | 4   | 5   | …   | Bits de control     |
| n   | 3   | 5   | 6   | 7   | 9   | 10  | 11  | 12  | 13  | 14  | 15  | 17  | …   | Bits del mensaje    |

La forma en que se distribuyen los bits de información y los de control, para conformar el mensaje, es en principio arbitraria.

Analizaremos una distribución en el mensaje de la siguiente forma, considerando un mensaje de 4 bits de información y que por lo tanto necesitará 3 bits de control:

|  |  |  |  |  |  |  |  |
|----|----|----|----|----|----|----|----|
| Posición Mensaje | 7 | 6 | 5 | 4 | 3 | 2 | 1 |
|  | i<sub>3</sub> | i<sub>2</sub> | i<sub>1</sub> | p<sub>2</sub> | i<sub>0</sub> | p<sub>1</sub> | p<sub>0</sub> |

**Los bits de control se colocan en las posiciones que corresponden a las potencias de dos.**

Se desea que los dígitos de control (en nuestro ejemplo 3) que indican el resultado del test de paridad sobre los dígitos de paridad, den (en binario) la posición del dígito erróneo.

Para determinar el valor que tomará cada bit de paridad se construye una tabla de combinaciones binarias de tantas columnas como la cantidad de bits de paridad determinada para la codificación. Para el caso anterior serían 3 columnas (p<sub>0</sub>, p<sub>1 </sub>y p<sub>2</sub>).

<table>
<tbody>
<tr>
<td></td>
<td>p<sub>2</sub></td>
<td>p<sub>1</sub></td>
<td>p<sub>0</sub></td>
<td></td>
</tr>
<tr>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td rowspan="3">Cada bit de paridad controla la posición que coincide con un 1 en su columna en la tabla binaria. Es decir:</td>
</tr>
<tr>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td>2</td>
<td>0</td>
<td>1</td>
<td>0</td>
</tr>
<tr>
<td>3</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>p<sub>0</sub> controla las posiciones: 1, 3, 5 y 7</td>
</tr>
<tr>
<td>4</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>p<sub>1</sub> controla las posiciones: 2, 3, 6 y 7</td>
</tr>
<tr>
<td>5</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>p<sub>2</sub> controla las posiciones: 4, 5, 6 y 7</td>
</tr>
<tr>
<td>6</td>
<td>1</td>
<td>1</td>
<td>0</td>
<td></td>
</tr>
<tr>
<td>7</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td></td>
</tr>
</tbody>
</table>

Para mayor cantidad de bits de paridad se agregan más columnas a la tabla. El bit de paridad debe hacer que la cantidad de bit unos controlados sea par.

Para el caso de un byte (8 bits) de información, corresponde un mensaje de 12 bits.

## Control y Corrección

Cuando el mensaje es enviado, el receptor calcula el valor de los bits de control de la siguiente forma:

c<sub>0</sub> **=** 1 3 5 7

c<sub>1</sub> = 2 3 6 7

c<sub>2</sub> **=** 4 5 6 7

**Los números corresponden a la posición de cada bit utilizado para el cálculo de los bits de control (ejemplo: “3” corresponde al bit ubicado en la posición 3) y el símbolo designa la operación OR exclusiva.**

Si el bit de control es igual a 0 es correcto, si es 1 es incorrecto. La posición del error se determina según los valores obtenidos en los bits de control ordenados en forma decreciente, es decir c<sub>2</sub>, c<sub>1 </sub>y c<sub>0</sub>. Si todos los bits de control son igual a cero no se detecta error en el mensaje.

EJEMPLO: Información a transmitir:

p = 3 (2<sup> p</sup> ≥ i + p + 1)

|  |  |  |  |  |  |  |
|----|----|----|----|----|----|----|
| 7 | 6 | 5 | 4 | 3 | 2 | 1 |
| 1 | 1 | 0 | \_\_ | 1 | \_\_ | \_\_ |
| i<sub>3</sub> | i<sub>2</sub> | i<sub>l</sub> | **p**<sub>**2**</sub> | i<sub>0</sub> | **p**<sub>**l**</sub> | **p**<sub>**0**</sub> |

**p**<sub>**0**</sub>**: 1, 3, 5, 7** ***0*****, 1, 0, 1 (para mantener la paridad para toma el valor 0)**

**p**<sub>**l**</sub>**: 2, 3, 6, 7** ***1*****, 1, 1, 1 (para mantener la paridad para toma el valor 1)**

**p**<sub>**2**</sub>**: 4, 5, 6, 7** ***0*****, 0, 1, 1 (para mantener la paridad para toma el valor 0)**

Mensaje transmitido:

|     |     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|-----|
| 7   | 6   | 5   | 4   | 3   | 2   | 1   |
| 1   | 1   | 0   | 0   | 1   | 1   | 0   |

Supongamos que al receptor llega el siguiente mensaje: 1101110

Al calcular, el receptor, los bits de paridad determina:

c<sub>0</sub> **=** 1 3 5 7 = 0 1 0 1 = 0 **Correcto**

c<sub>1</sub> = 2 3 6 7 = 1 1 1 1 = 0 **Correcto**

c<sub>2</sub> **=** 4 5 6 7 = 1 0 1 1 = 1 **Incorrecto**

1 0 0 (<sub>2</sub> **=** 4 indica la posición del error.

c<sub>2</sub> c<sub>1</sub> c<sub>0</sub>

|     |     |     |     |     |     |     |                                                     |
|-----|-----|-----|-----|-----|-----|-----|-----------------------------------------------------|
| 7   | 6   | 5   | 4   | 3   | 2   | 1   |                                                     |
| 1   | 1   | 0   | 0   | 1   | 1   | 0   | Error en la posición 4 (se cambia el valor del bit) |
