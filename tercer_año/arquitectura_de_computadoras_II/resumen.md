# Arquitectura de computadoras II

## Notas

* Profesora practico: Delfina Velez Ibarra (0703883@ucc.edu.ar)
* Libro de Patterson (?)
* Nuevo micro de base ARMv8

## Introduccion

Micro path del ARMv4 (el viejo):

![](./img/armv4.png)

La arquitectura del ARMv4 y ARMv8 son muy similares, solo que el v4 es de 32 bits y el v8 es de **64 bits** y en v8 ahora tenemos **32 registros**, es decir, el doble que en v4.

A pesar de ser una nueva version, las **instrucciones** siguen siendo de **32 bits** como en v4.

Diagrama basico de un **instruction fetch**:

![](./img/fetch_instruction.png)

(Leemos una instruccion, y como la memoria esta dividida en bytes sumamos 4 posiciones al PC para leer la siguiente instruccion.)

**LEGv8**: Lenguaje de programacion para codear sobre un ARMv8, un poco modificado por fines didacticos (**Subset** de **instrucciones** de ARMv8 con diferencias por temas **didacticos**).

Las operaciones tipo R son operaciones entre **registros** (Son las mas conocidas en un ARM, suma, resta, etc.)

![](./img/operaciones_r.png)

Ahora se usan 5 bits para redireccionar los registros (Creo que es el proceso de armar la palabra hexadecimal).

`Nota: El registro 31 (x31 o x) siempre guarda el valor 0`

Otro conjunto de operaciones que podemos hacer en un ARM es el conjunto de operaciones en **memoria**. (load / store)

![](./img/memory_op.png)

Por ultimo tenemos las operaciones de **salto** (Branch)

![](./img/salto.png)

(Cuando hacemos un branch, la arquitectura primero verifica q se ejecuta un branch si el ALU levanta el flag zero (condicional, leyendo dicha flag). Luego, mediante el label y la posicion actual del PC vemos cuantas instrucciones necesitamos mover el PC para saltar al label en cuestion y sumamos ese numero multiplicado por 4, o corrido 2 veces hacia la izq al PC)

Arquitectura del LEGv8:

![](./img/legv8.png)

Las posibles instrucciones que podemos hacer en el datapath mostrado anteriopmente son las siguientes (5 bits):

![](./img/instrucciones_legv8.png)

**Estructura de las instrucciones:**

![](./img/estruc_ins.png)

Las instrucciones tienen siempre 32 bits, solo que dependiendo del tipo de instruccion (tipo R, memoria o branch) los "bloques" o "campos" de dicha instruccion van a estar en distinto orden.

**Campos**

* **opcode**: tipo de operacion (R, memory, branch)
* **Rm**: la direccion del segundo registro (5 bits porque tenemos 32 registros, es decir del 0 al 31)
* **shamt**: operacion shift (6 bits porq podemos mover registros de 64 bits)
* **Rn**: Direccion del primer registro operando
* **Rd**: Direccion del registro de destino.

Ejemplo:

![](./img/ejemplo_palabra.png)

Los recursos utilizados por el ARMv8 / LEGv8 para realizar una operacion tipo R son los marcados con negro:

![](./img/r_tipo_r.png)

Estructura de las instrucciones tipo D (Load/Store)

![](./img/d_instruction.png)

Estructura de las instrucciones tipo branch:

![](./img/branch_ins.png)

* RT: en el caso de ser un salto condicional, este campo tiene el registro a verificar.

Instrucciones tipo I (Como tipo R pero operan con un registro y un inmediato):

![](./img/i_instruction.png)

Instrucciones tipo white immediate (Nos permite guardar un valor inmediato en un registro y especificar en que parte del registro guardar dicho valor inmediato.)

![](./img/wi_instruction.png)

* MOVZ: Mueve el inmediato a la posicion indicada, dejando todas las demas en 0
* MOVK: Mueve el inmediato a la posicion del registro indicada, dejando todas las demas tal como estaban en un principio.

## Libro patterson

La computacion avanza y mejora todo el tiempo. Mientras mas hardware se implanta, mas rapido andan los sistemas y aplicaciones mas complicadas se pueden ejecutar.

**Ley de moore**: La cantidad de recursos de hardware (transistores) que se puede integrar en un chip se duplican cada 18 meses, por lo que se reducen los tamaños y nanometros necesarios para incrustar dichos recursos, estos van a ser mas pequeños y mas baratos.

`Nota: Hoy en dia casi todo es un sistema computacional.`

**La era postPC**: Hoy en dia las PC's no son relevantes en cuanto a cantidad de procesadores que se producen. La mayor cantidad de procesadores se fabrican para dispositivos IOT.

![](./img/postpc.png)

**Entendiendo performance**: Es muy importante tener en cuenta la performance, ya que un pequeño error o feature no optimizada puede generar ineficiencias abismales.

**Las 8 grandes ideas**:
* La ley de moore.
* Uso de abstraccion para simplificar diseño.
* Hacer el caso comun lo mas rapido posible.
* Performance via paralelismo
* Performance via pipeling
* Performance via prediccion
* Jerarquia de memorias
* Confiabilidad via redundancia

**Arquitecturas de 1 ciclo**: 1 instruccion se realiza en 1 ciclo

**Niveles de codigo programable:**
* Codigo de alto nivel
* Assembly
* Representacion del hardware (binario)

`Nota: El costo de elaborar un procesador depende mayormente del area del mismo`

* **Tiempo de respuesta**: Cantidad de tiempo tomado para resolver una actividad
* **Rendimiento**: Cantidad / Tasa de actividades realizadas por unidad de tiempo.
* **Performance**: Calculo para comparar dos procesos y ver cual es mas performante. proceso_1 / proceso_2

**CPU Clocking**: En un procesador de **un ciclo**, toda la instruccion se ejecuta en un solo ciclo. Un "Clock" es una señal de sincronismo.

* **Periodo** de un clock: Duracion de un ciclo de reloj
* **Frecuencia** de un clock: Ciclos por segundo

Casi todos los sistemas se realizan sobre CMOS: El semiconductor complementario de óxido metálico (CMOS) es una pequeña cantidad de memoria en una placa base del equipo que almacena la configuración del Sistema básico de entrada/salida (BIOS).

![](./img/power.png)

**Arquitecturas no convencionales de CPU's**:
* Intel x86
* CISC (Intel)
* RISC (ARM y todos los demas)


**Caracteristicas de los RISC**

* Tiene como meta ejecutar **una instruccion por ciclo** (en un ciclo de sincronismo entra una instruccion nueva y en el mismo ciclo sale otra instruccion) o tiene un ciclo de instruccion **constante** (Conjunto de instrucciones que entran por clock).
* Procesador orientado exclusivamente a **operaciones entre registros** (Porque el acceso a memoria es muy **lento**). Por lo que la cantidad de registros **aumenta** considerablemente.
* Modo de **direccionamiento** (Distintas formas de hacer referencia a una direccion de memoria) muy **sencillo** (Idealmente solo 1).
* **Formatos** de **instrucciones simples** (faclies de ver, entender y codificar)
* **Set** de **instrucciones reducido**.

**Implementaciones de ARM**

![](./img/imp_arm.png)

`Nota: En x86, una instruccion no se codifica con una cantidad fija de bits.`
![](./img/x86_instrucciones.png)

**"Falacias"**

* Mediante instrucciones mas potentes obtengo mejor performance (Las instrucciones complejas son dificiles y caras de implementar).
* Compatibilidad hacia atras no genera un cambio en el set de instrucciones (A medida que mejoran los procesadores, se van aumentando la cantidad de instrucciones)

## Semiconductores y acceso / organizacion de memoria.

Sistema de memoria: elemento capaz de **almacenar** y **retener** informacion. Estos sistemas siempre tienen un **medio fisico**. Los sistemas de memoria que veremos son los basados en **estructuras semiconductoras** (no los magneticos, ni los otpicos)

Los sistemas semiconductores tienen una determinada interfaz

![](./img/semiconductores_interfaz.png)

No todas las memorias semiconductoras son **iguales**.

![](./img/memorias.png)

* Memorias de **lectura-escritura**
    * Acceso **aleatoreo** 
        * **static ram**: Los bits duran eternamente (Es mas cara, 6 transistores) 
        * **dinamic ram**: Los bits duran microsegundos (Mhz --> frecuencia de refresco). Siempre se reescriben los bits.
    * Acceso **no aleatoreo**
* Memorias de lectura-escritura **no volatil**
* Memorias de **solo lectura**

**Algunas definiciones**:

Una memoria es buena dependiendo de estos parametros

**Tiempo de acceso**: Tiempo dado desde la request de un dato hasta la response del mismo (lectura o escritura, el tiempo de lectura es mas rapido que el de escritura).

**Tiempo de ciclo**: Tiempo que debe transcurrir entre 2 operaciones iguales.

![](./img/acceso_ciclo.png)

**Organizacion de un sistema de memoria**

Un sistema de memoria es un arrreglo o matriz de bits.

![](./img/memory_org.png)

Cada fila es una **palabra** (**Unidad de acceso** del sistema de memoria, 8 bits que entran en un sistema de E/S) Estas unidades de direccionan mediante direcciones de acceso de memoria.

La **capacidad de memoria** se calcula mediante `cantidad de palabras * 8 bits`

Ya que las memorias son muy grandes (Muchas palabras), para acceder a dichas palabras se utiliza decodificadores y multiplexores

Al momento de implementar memorias, se debe de tener en cuenta el ancho y alto de las mismas, por lo que ordenan las palabras en matrices, y se usan los multiplexores y decodificadores para elegir la posicion deseada.

![](./img/decodificador_memoria.png)

![](./img/memoria_matrices.png)

`Nota: Las memorias RAM pueden tener distintos layouts, es decir mas o menos bloques de memoria.` 

Estas distintas memorias (o son los bloques?) se pueden incrustar en una PC para **agrandar** ya sea el ancho de las palabras (**conexion en paralelo**) o la cantidad de palabras (**Conexion en serie**) y asi hacer mas grande el **mapa de memoria**.

![](./img/paralelo.png)

En ambos chips de memoria se accede utilzando la misma señal de address, asegurandonos que en ambos chips obtendremos fragmentos de la misma palabra.

![](./img/serie.png)

(A10 y A11 no van negados)

(Se niega 2 veces desde el decodificador hasta el bloque de memoria por los ruidos electricos)

`NOTA: ACTIVA POR BAJO`

El limite de bits en el addres que puedo implementar me lo da el microprocesador.

(Hasta aca vimos la logica de codificacion, señales de words)

## Memoria en sistemas computacionales 

**Principio de Localidad de las referencias**

La **posibilidad** de acceso a una direccion de memoria **decrece** a medida que me voy alejando del acceso actual del procesador. 

Permite determinar que los programas en realidad acceden a una **pequeña porcion** del mapa de direcciones de la memoria en un **momento determinado**.

* **Localidad temporal**: como en los loops (**lazos**), las direcciones ya accedidas son muy probables a ser vueltas a acceder.
* **Localidad espacial**: En un programa es muy probable acceder a direcciones de memoria cercanas a la actual

Este principio nos permite: 
* "adivinar" cual va a ser la siguiente direccion de memoria.
* Guardar las direcciones de memoria mas probables a ser accedidas en sistemas de jerarquias altos (veloces y caros), muy cerca del procesador.

![](./img/costos_memoria.png)

**Aumentando el ancho de banda de una memoria (Ver de nuevo el fragmento la clase)**

(Los procesadores salen mas caro porq aumentan el cache)

![](./img/ancho_banda.png)

**Memoria cache (Leer del libro)**

Nivel / jerarquia superior de memoria, es el mas cercano al procesador.

No es de acceso aleatoreo, es asociativo. Si no tiene una direccion de memoria se abre.

Si se tiene el dato pedido, se devuelve un bloque (conjunto de palabras)

La cache esta distribuida en lineas, referenciadas por tags. cada linea tiene un bloque (conjunto de x palabras). HAY MUCHOS MAS BLOQUES QUE LINEAS.

![](./img/cache.png)

**Criterio de correspondencia / tipo de cache**

* **Cache de Mapeo directo**: Hay solo una forma de guardar los datos en cache con respecto a la memoria principal.

![](./img/mapeo_directo.png)

Direccion de acceso: tag | verification | index | word offset | byte offset |

![](./img/xd.png)

Aclaraciones:
- En un bloque (en una linea) hay mas de 1 palabra del procesador.
- Bloques mas grandes reducen la probabilidad de miss
- Si los bloques on muy grandes, puede haber polucion (reveer en la clase del 27/08)
- larger miss penalty

Si el cache falla, demoramos mas ciclos en traer la info del siguiente nivel jerarquico de memoria, por lo que demoramos mas tiempo.

* **Caches asociativas**

* Es imposible de implementarse debido a su alto costo
* Cualquier bloque puede entrar en cualquier linea de cache
* Todas las lineas deberan ser vistas en una busqueda

`Nota: En terminos reales, las caches son asociativas por conjuntos de n-ways o n-vias`

![](./img/vias_conjuntos.png)

ojo con el algoritmo de sustitución, este puede ser una entrada con bit valido en 0, metodo LRU (last recently used), MRU (most recently used), random, etc.

**Cache multinivel**: Orden jerarquico dentro de las caches ordenados por la cercania o lejania de del procesador. Mientras el nivel sea mas alto, mas caro, performante y chico. Suelen tener 2 niveles. L1 (parte del CPU) y L2

## Sistemas de entrada salida (E/S)

Uno de los 3 subsistemas que conforman una gran parte de los sistemas computacionales.

Es el que me permite traer datos de la realidad o exponerlos hacia la misma.

`Nota: Perifericos no es lo mismo a modulo de E/S`

En arquitecturas viejas, los perifericos se conectaban a la PC mediante un sistema de puertos (canales de datos).

![](./img/puertos.png)

Hoy en dia se utilizan arreglos basados en **buses**. El periferico manda los datos al bus de datos o bus de E/S y el bus se encarga de mandarlo a la memoria

![](./img/bus.png)

![](./img/tipos_de_bus.png)

O se utlizan registros en la memoria principal para acceder a los perifericos (memory-mapped I/O, ARM) o se utiliza un mapa de memoria adicional (Standard I/O, intel)

**Ventajas y desventajas de C/U**

![](./img/bus_ventajas.png)

**Metodos de operacion de E/S**

![](./img/polling.png)

Hay 3 metodos para acceder a los recursos involucrados en un sistema computacional:

* **E/S programada** (Polling-driven): 

Todos los procedimentos del manejo de dispositivos E/S se manejan mediante programas especificos (instrucciones) escritos para dicho objetivo.

La principal desventaja es que se desperdician muchos ciclos en revisar el estado de modulo E/S (las instrucciones del programa estan en memoria, y el acceso a memoria es mas lento que la generacion de datos por parte del modulo E/S)

![](./img/estado.png)

* **Interrupcion**

Una interrupcion es un **recurso fisico** (interrupt request). Cuando al CPU le llega un IR, este interrumpe la ejecucion normal de un codigo para leer el dato introducido en el modulo de E/S

Al finalizar **cada** ciclo de **instruccion**, el CPU verifica si hay IR pendientes (**No se consume ciclos de instruccion**).

Si hay IR, se corta el programa ejecutado por el CPU y se salta a una posicion especifica de memoria llamada **vector de interrupciones**. Dicho vector contiene las referencias a los codigos respectivos a cada modulo de E/S que garantizan el correcto funcionamiento del mismo. Este codigo se denomina **ISR** (interrupt service routine)

![](./img/interrupcion.png)

El vector de ISR se aloja en memoria. ¿donde?

* **Direccion fija**:

Direccion establecida en la propia logica de la CPU, y no es modificable (util cuando el sistema es pequeño y la cantidad de perifericos a utilizar es poca).

* **Direccion vectorizada**

El periferico provee la direccion al CPU por medio del bus de datos. Por lo que ahora existe una señal INTERRUPTION ACKNOWLEDGE que es mandada por el bus de datos desde el cpu al periferico que indica que dicha interrupcion ha sido tomada. Una vez el modulo de E/S recibio el INT ACK, se manda al CPU la direccion del ISR para ejecutar el programa de manejo de datos de perifericos.

¿Como se procesa una interrupcion?

![](./img/proceso_int.png)

* **DMA** (Direct memory access)

