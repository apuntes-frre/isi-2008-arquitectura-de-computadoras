# Tecnologías CISC y RISC

## Contenido

- [Secuenciamiento de las Instrucciones](#secuenciamiento-de-las-instrucciones)
- [Secuenciadores Cableados y Secuenciadores Microprogramados](#secuenciadores-cableados-y-secuenciadores-microprogramados)
- [El Distribuidor de Fases](#el-distribuidor-de-fases)
- [Decodificación de la Instrucción](#decodificación-de-la-instrucción)
- [Biestables de Estado](#biestables-de-estado)
- [Secuenciadores de Lógica Microprogramada](#secuenciadores-de-lógica-microprogramada)
- [La Memoria de Control](#la-memoria-de-control)
- [Consideraciones acerca de los secuenciadores](#consideraciones-acerca-de-los-secuenciadores)
- [Características de la Tecnología RISC](#características-de-la-tecnología-risc)
- [Tendencias en la Utilización](#tendencias-en-la-utilización)

Introducción

Este trabajo trata acerca de las estrategias utilizadas para secuenciar las instrucciones de las computadoras a nivel digital. Para ello se hace referencia al secuenciamiento de las instrucciones y los tipos de secuenciadores, para concluir con una descripción de las dos tecnologías que se utilizan en el diseño de microprocesadores: CISC y RISC.

## Secuenciamiento de las Instrucciones

El elemento fundamental en el manejo de las instrucciones a nivel digital es el SECUENCIADOR. Este genera las microórdenes según dos tipos de información de entrada al secuenciador:

- La operación a realizar
- El estado de la máquina

La operación a realizar está definida por el *código de operación*, las *condiciones de direccionamiento* y los *registros involucrados* (todos estos datos son extraídos del registro de instrucción). El estado de la máquina está determinado por los valores de los *flags* asociados a distintos registros.

Como consecuencia del análisis y proceso de la información de entrada se generan las microórdenes que conforman las salidas del secuenciador.

El secuenciamiento de las microórdenes en el tiempo puede llevarse a cabo de dos maneras distintas:

1.  El secuenciador conoce los tiempos de respuesta de los diferentes componentes, entonces incorpora retardos entre las diferentes microórdenes sucesivas de manera que se sincronicen.

2.  El secuenciador recibe señales de los diferentes componentes que indican el estado en que se encuentran (por ejemplo que han terminado una operación y que se hallan disponibles). No se lanzará una operación hasta no estar seguro de que la anterior ha finalizado.

## Secuenciadores Cableados y Secuenciadores Microprogramados

Existen dos clases de Secuenciadores:

1.  Secuenciadores cableados o de lógica cableada, realizados en forma de circuito secuencial electrónico.

2.  Secuenciadores microprogramados, que utilizan un medio de almacenamiento (memoria de control) donde se guarda un microprograma para cada instrucción.

Secuenciadores de Lógica Cableada

El objetivo es generar microórdenes desplazadas en el tiempo por retardos apropiados. Una cadena de retardos apropiados permite realizar esta función.

## El Distribuidor de Fases

El problema de desplazar las señales de control de las operaciones es que a un mismo pulso de reloj debe ser generado un cierto número de microórdenes. Al ser idénticas todas las señales de reloj, es preciso dar al secuenciador los medios para situarse por referencia al tiempo, para saber en que fase del ciclo o de la instrucción se encuentra; esta es la función del distribuidor de fases, que partiendo de los impulsos periódicos del reloj, produce señales de impulso o nivel acordes a las diferentes fases del ciclo de memoria o de la instrucción.

En un instante determinado solamente uno de los biestables B<sub>0</sub>, B<sub>1</sub>, B<sub>2</sub>, B<sub>3</sub> estará puesto a 1. El próximo impulso de reloj lo pondrá a 0 y poniendo a 1 el siguiente biestable. Suponiendo que el tiempo de basculamiento del biestable sea igual al ancho de un pulso de reloj, se puede esquematizar el siguiente cronograma.

## Decodificación de la Instrucción

La instrucción consta de diferentes campos de información de interés para el secuenciador, como el código de operación, las condiciones de direccionamiento, las direcciones de los registros, etc. Algunos de estos campos deben ser decodificados, excepto aquellos en los cuales los bits involucrados hacen referencia directa a algún tipo de registro. El decodificador de instrucción se encarga de realizar la tarea de decodificación. Puede utilizarse para ello una matriz de diodos o transistores.

## Biestables de Estado

Un aspecto importante para el secuenciamiento de instrucciones en secuenciadores de lógica cableada lo constituye el estado de la máquina. El mismo está definido por el contenido de ciertos registros llamados “flags”. Los flags pueden cambiar de valores debido a dos causas: 1) como resultado de alguna operación, 2) como resultado de la acción directa del secuenciador (por ejemplo la reserva de algún registro particular).

Trazado de Cronogramas

Todo lo visto anteriormente sirve de base para la realización de las “ecuaciones lógicas de la máquina”. Estas asociadas a los valores de los flags definen completamente al secuenciador. Para construir las ecuaciones lógicas se deben analizar paso por paso una instrucción y determinar dos aspectos fundamentales:

1)  Que microórdenes intervienen

2)  En que tiempo deben ser disparadas (en referencia a los pulsos del reloj y a las microórdenes anteriores).

Una herramienta útil para la definición de las ecuaciones lógicas de un secuenciador son los cronogramas.

## Secuenciadores de Lógica Microprogramada

La microprogramación consiste en reemplazar al secuenciador cableado por un secuenciador programado. A cada instrucción de la máquina le corresponde un microprograma almacenado en una memoria especial, llamada memoria de control.

Modelo de WILKES

El modelo de WILKES contiene la base del funcionamiento de la lógica microprogramada. La representación esquemática es la siguiente:

A la entrada del dispositivo de control tenemos el código de operación de la instrucción a ejecutar, la que se considera como la dirección de la primera micro – instrucción del microprograma asociado a la instrucción. Esa dirección se envía al registro SMC (Selección de Memoria de Control) que, cuando se decodifica, permite activar el hilo de la palabra horizontal sobre el cual está grabada la micro – instrucción de la siguiente manera:

Los unos están representados por un acoplamiento (marcado con un punto en el esquema) con el correspondiente hilo del bit vertical, los ceros por la ausencia de acoplamiento. A la salida, la micro – instrucción está compuesta por dos partes: una, el código de la micro – instrucción que da directamente las microórdenes a distribuir al conjunto de la máquina; y la otra, la dirección de la próxima micro – instrucción (DC o Dirección de Control) que se transfiere, en el siguiente pulso de reloj, al SMC. El microprograma continúa hasta la última micro – instrucción, la cual cargará en el SMC el nuevo código de Operación.

También se hace referencia en el esquema, a la posibilidad de realizar saltos condicionales, utilizando el biestable E que puede ser puesto a uno bajo determinadas condiciones por las micro – instrucciones.

## La Memoria de Control

Es la memoria que contiene los microprogramas. La velocidad de la memoria de control debe ser superior a la de la memoria principal. Esto se debe a que es preciso que un microprograma se desarrolle completamente en intervalos de tiempo correspondiente a los accesos de memoria en busca de los operandos. La memoria de control brinda flexibilidad al sistema debido a que generalmente se pueden modificar los microprogramas, agregar nuevos microprogramas e incluso sustituirla por completo.

## Consideraciones acerca de los secuenciadores

Ventajas y desventajas

La ventaja que sobresale en los secuenciadores cableados es la velocidad de ejecución de una micro – instrucción, ya que para ejecutarse solamente depende del tipo de instrucción y el estado de la máquina. No ocurre lo mismo con los secuenciadores microprogramados debido a que al tipo de instrucción y al estado de la máquina se le suma el tiempo de ejecución del microprograma.

Existen, sin embargo dos ventajas de los secuenciadores microprogramados que provocaron que los diseñadores se volcaran a la construcción de los mismos: la facilidad en el diseño y la modularidad en el crecimiento. Diseñar un secuenciador cableado es muy complejo y más aún depurarlo. Agregar una micro – instrucción representa un trabajo muy arduo en los secuenciadores cableados y a veces implica su rediseño.

En la evolución del diseño de computadoras se sopesaron la velocidad y la simpleza, y a partir de ello surgieron dos tecnologías que durante mucho tiempo fueron contrapuestas: CISC y RISC.

Tecnologías CISC y RISC

Evolución histórica

Al principio los programas se realizaban en lenguaje de máquina, esto hacía que el programador tuviese que tener un gran conocimiento del Hardware y dependía de él la mejora o no de la performance en la ejecución de sus programas.

Apareció entonces la idea de hacer que la suma de varias instrucciones sencillas se plasmaran en un microprograma haciendo más fácil la tarea del programador. Esta idea se conoció con el nombre de CISC (Complex Instructions Set Computer).

Funcionalmente la CPU creció con un modulo de decodificación. Después de efectuarse una lectura, la instrucción es decodificada según varios campos y subcampos. Como primer resultado se obtiene un puntero al microprograma, confinado con el Control Store. Inmediatamente el control se transfiere a éste y las acciones se suceden en el orden del microprograma (utilizando varios ciclos de reloj).

A principios de la década del 80, el mundo aparecía rendido a los pies del CISC, desde las PCs hasta los Mainframes, y a nadie se le ocurría otra cosa que tratar de mejorarlo. Ocupados en esta tarea alguien se dio cuenta que algo andaba mal.

Después de diferentes testeos se comprobó que a excepción de las operaciones de punto flotante, la mayor parte del esfuerzo del procesamiento se concentra en las instrucciones más simples, lo que significa que la mayor parte del tiempo no se utiliza la CPU ya que aquellas se ejecutan por medio de un microprograma.

Como contrapartida a la tecnología CISC surgió entonces la tecnología RISC (Reduced Instructions Set Computer) con las siguientes características:

- Elimina las instrucciones complejas del Instruction Set (a excepción de las operaciones de punto flotante)
- Elimina el microcódigo
- Logra ejecutar todas las instrucciones en un ciclo de reloj.
- Jerarquiza el uso del compilador

Características de la Tecnología CISC

La denominación CISC se debe a que los procesadores que utilizan esta tecnología pueden ejecutar desde instrucciones simples (como las que ordenan sumar o restar dos números que están almacenados en registros de la CPU y el resultado asignarlo a uno de estos registros), hasta instrucciones muy complejas (como movimiento de cadenas de caracteres de gran longitud y variable, en procesamiento de textos).

Las instrucciones simples, luego de su decodificación, pueden ejecutarse en un pulso de reloj, mientras que las complejas requieren un número de pulsos que dependen de la secuencia de pasos necesarios para su ejecución.

Cada paso se lleva a cabo mediante una combinación binaria (microcódigo), que aparece en las líneas de control de la UC con cada pulso de reloj, la cual activa los circuitos que intervienen en ese paso. Las sucesivas combinaciones (microcódigos) que requiere la ejecución de una instrucción compleja, deben ser provistas por una memoria de control que las almacena y que forma parte de la UC.

**Por lo tanto, un procesador CISC necesariamente debe contener una memoria de control con los microcódigos, para poder ejecutar las instrucciones complejas. Esta es una de las características CISC.**

En general; cada operación que ordena una instrucción de un procesador CISC presenta variantes para ser aplicadas a diversas estructuras de datos, desde simples constantes y variables, hasta matrices y otras. Así, una instrucción que ordena sumar tiene muchas variantes (códigos) en función de la estructura de datos sobre la cual opera. Es como si existieran tantas instrucciones que ordenan una misma operación como estructuras de datos típicas se han definido para operar, lo cual se denomina “modos de direccionamiento” de una instrucción.

**La existencia de muchos “modos de direccionamiento” para realizar la operación que ordena una instrucción, es otra de las características de complejidad de los procesadores CISC. Esto se manifiesta en que el set de instrucciones de una máquina CISC presente un número elevado de códigos de instrucción.**

Esto definitivamente incide sobre el set de instrucciones de una máquina CISC. Un set de instrucciones CISC posee alrededor de 210 instrucciones.

Asimismo, lo anterior exige instrucciones que ocupan distinta cantidad de bytes en memoria.

Un aspecto importante es el solapamiento de microórdenes (o “PIPE LINE”) ya que al haber instrucciones que requieren distinta cantidad de pulsos de reloj para su ejecución, podrán generarse errores. De esto se desprende que un procesador CISC no puede utilizar eficazmente su PIPE LINE en la producción de instrucciones.

En la concepción CISC se busca lograr el “salto semántico”, que es obtener la menor disparidad entre los lenguajes de alto nivel y el lenguaje de máquina.

Recordar al respecto, que una sentencia como Z = P + P – Q se debe traducir a una secuencia de instrucciones de máquina como I<sub>1</sub>, I<sub>2</sub>, I<sub>3</sub>, I<sub>4</sub>. Suponiendo que en un cierto lenguaje de alto nivel dicha sentencia (u otra más común) se usara frecuentemente, se podría tener un CISC que hiciera corresponder a esa sentencia una sola instrucción I<sub>x </sub>, de máquina, que reemplazara a las 4 instrucciones citadas. Esto se conseguiría escribiendo en la memoria de control una extensa secuencia de microcódigos para poder ejecutar I<sub>x</sub> .

De existir muchas equivalencias entre sentencias en alto nivel e instrucciones de máquina, el programa traductor entre ambos niveles (compilador) sería más sencillo de fabricar, y los tiempos de compilación disminuirían, que lógicamente son los objetivos de la arquitectura CISC.

Se comprende que esta concepción puede llegar al extremo de fabricar un CISC con instrucciones de máquina que sean equivalentes a sentencias muy usadas en un cierto lenguaje de alto nivel, pero que no se usarán, si se programa en otro lenguaje de alto nivel que no las utiliza.

## Características de la Tecnología RISC

Buscando optimizar la performance de los procesadores, se realizaron estadísticas de las instrucciones de máquina más usadas. Resultó que las instrucciones más simples (que son solo el 20% del repertorio de instrucciones de un procesador CISC) constituían el 80% de los programas típicos ejecutados.

El 91% de las sentencias más usadas en lenguajes de alto nivel (Fortran, Pascal, Basic, C, etc.) son las del tipo “Asignar” (un valor a una variable), “IF” (condicional), “Call” (llamar a procedimiento), “Loop” (repetir una secuencia), que en promedio constituyen el 47%, 23%, 15%, 6%, respectivamente.

La información anterior sirvió para planificar procesadores con un set de instrucciones simples (operar dos números que están en registros de la CPU, y el resultado asignarlo a uno de esos registros) que presentan muy pocos modos de direccionamiento. Por ser simples, estas instrucciones se ejecutan en un solo pulso de reloj, luego de haber sido decodificadas.

A fin de traducir un lenguaje de alto nivel a este tipo de instrucciones, empleando un mínimo de ellas, se requiere para RISC un programa compilador inteligente, muy elaborado. O sea que es necesario un compilador (software) complejo, como contrapartida de un hardware más simple.

Para mover datos de memoria a registros, y en sentido contrario, fue necesario la existencia de instrucciones que ordenen estos movimientos, que en lenguaje assembler de RISC se llaman LOAD y STORE, respectivamente. Se trata de utilizar estas instrucciones lo menos posible (usando programas compiladores “inteligentes”), pues requieren dos pulsos de reloj para ser ejecutadas, luego que fueron decodificadas.

A diferencia, en un CISC cualquier instrucción tiene la opción de requerir un dato de memoria.

El número total del set de instrucciones de un procesador RISC es reducido (entre 70 y 150 instrucciones, según el modelo).

Debido a que la mayoría de las instrucciones RISC se ejecutan en un pulso de reloj, se obtiene un PIPE LINE eficaz, terminándose de ejecutar en promedio, una instrucción por cada pulso de reloj (en promedio, debido a que las instrucciones LOAD – STORE utilizan dos pulsos). Todas las instrucciones RISC son de formato fijo, siendo que en un CISC ocupan distinta cantidad de bytes. Esto redunda en una mayor sencillez y velocidad de procesamiento.

Por constar de instrucciones cuya fase de ejecución requiere mayormente de un pulso, o a lo sumo dos, no se requiere de una memoria de control que sirva de base para la ejecución del microcódigo que debe aparecer a las salidas de la UC con cada pulso de reloj para comandar el procesador.

Esto es, los bits del código de operación de cada instrucción que llega al registro de instrucción RI para ser ejecutados por un procesador RISC, sirven de base para que un circuito de la UC los convierta directamente en la combinación de bits que deben aparecer en las salidas de la UC (microcódigo) para que en proximo pulso de reloj se ejecute la instrucción en cuestión.

Por lo tanto, la UC de un RISC no contiene memoria de control (de microcódigos). Esto, por un lado permite ganar mayor velocidad de procesamiento, pues se evita el acceso a la memoria de control. Por otro lado, beneficia mucho el diseño del chip que contiene un procesador RISC, dado que la superficie que ocupa una memoria de control de un CISC, en un RISC es aprovechada para aumentar el número de registros de uso general de la CPU. Un mayor número de registros permite utilizar menos instrucciones LOAD-STORE, lo cual redunda en menos accesos a memoria principal.

Otra característica de los procesadores RISC es la incorporación de un cache interno para datos y otro para instrucciones, que reducen los accesos a memoria principal. Esta misma idea también fue aprovechada en procesadores de base CISC como el Pentium.

Comparación entre CISC y RISC

El hecho de que la mayoría de las instrucciones sean de igual complejidad trae aparejado un mejor rendimiento del “pipe-line”. Otro factor que disminuye este rendimiento son la dependencia del resultado de una instrucción para poder ejecutar la siguiente, y un mismo recurso (por ejemplo un registro de la CPU) que es requerido por varias etapas de un “pipe-line”. Estos factores influyen menos en un RISC que en un CISC, resultando así una mayor velocidad de procesamiento.

Por ejemplo, si el resultado de una instrucción es el dato de la siguiente, puesto que la mayoría requiere dos pulsos (fases) para ejecutarse, cuando una instrucción en el pipe-line pasa a la fase de ejecución, las anteriores que entraron al pipe-line ya completaron dicha fase. Solo existe una espera, cuando el dato que opera una instrucción se cargo en un registro desde memoria en la instrucción anterior. Se trata de un pipe-line al cual llegan instrucciones de máquina planificadas por un compilador inteligente.

Los procesadores CISC pierden mucho tiempos en las instrucciones de llamado a subrutina y en las interrupciones, dado los consiguientes accesos la pila de memoria principal que requieren. Las estadísticas indican que en el llamado a procedimientos, el 98% de las veces se utilizan menos de 6 argumentos, y el 92% de las veces menos de 6 variables locales.

Asimismo, que un procedimiento llame a otro, este a un tercero, el tercero a un cuarto, etc., (anidamiento o llamadas sucesivas) sólo se llega a 8 llamadas sucesivas en el 1% de las veces.

Dado que los RISC posee un número elevado de registro estos pueden usarse para el manejo de llamados en lugar de perder tiempo para escribir y leer la pila ubicada en memoria.

|  |  |  |
|----|----|----|
| Característica | CISC | RISC |
| Memoria de control | Sí | No |
| Set de instrucciones | Grande | Reducido |
| Ciclos de reloj por instrucción | No existe un número definido | Uno o dos |
| Accesos a MP mediante microinstrucciones | Sí | No, utiliza registros auxiliares. (excepto LOAD – STORE) |
| PIPE LINE | Ineficiente | Eficiente |
| Compiladores | Simples | Complejos |
| Permite modularidad y el crecimiento del set de instrucciones | Sí | No |
| Formato de Instrucciones | Variable | Fijo |
| Implementación de paralelismo en la ejecución de las instrucciones | Compleja | Simple |
| Velocidad de procesamiento | Reducida por los accesos a memoria de control | Optimizada por el paralelismo de ejecución |
| Predicción de bifurcaciones | No | Sí |

## Tendencias en la Utilización

Si bien la década de los 80´s y principios de los 90´s estuvieron marcadas por la influencia CISC, debido a que su utilización brindó excelente respuesta a los requerimientos de los usuarios, las mejoras que introdujo la utilización de RISC, en lo referente a velocidad de procesamiento, no fueron descartadas por los diseñadores de microprocesadores.

La muestra más clara de lo referido anteriormente es la fabricación del PENTIUM, un microprocesador básicamente CISC, con características de procesamiento RISC. Este procesador que incluye una memoria de control incorpora también predicción de bifurcación, procesamiento en paralelo, división de la memoria cache en cache de datos y cache de instrucciones. Es, en definitiva, un procesador híbrido, una mezcla de las dos tecnologías.

Esta es la tendencia de los microprocesadores, la creación de híbridos que contengan las ventajas de las dos tecnologías, que durante mucho tiempo parecieron ser contrapuestas y no tener puntos de contacto.
