# Resumen de Arquitectura de computadoras

## Indice

- [Resumen de Arquitectura de computadoras](#resumen-de-arquitectura-de-computadoras)
  - [Indice](#indice)
  - [Algebra de Boole](#algebra-de-boole)
    - [Postulados](#postulados)
    - [Logica con Boole (Tablas de verdades)](#logica-con-boole-tablas-de-verdades)
    - [Teoremas](#teoremas)
    - [Funcion en Boole](#funcion-en-boole)
  - [Simplificacion por Karnaugh](#simplificacion-por-karnaugh)
    - [Adyacencia logica](#adyacencia-logica)
    - [Mapa de Karnaugh](#mapa-de-karnaugh)
  - [Sistemas combinacionales](#sistemas-combinacionales)
    - [Condiciones sin cuidado (no importa)](#condiciones-sin-cuidado-no-importa)
  - [Aplicaciones del algebra de Boole](#aplicaciones-del-algebra-de-boole)
  - [Operaciones en un CPU (sistema combinacional)](#operaciones-en-un-cpu-sistema-combinacional)
    - [Complemento a la base y a la base-1](#complemento-a-la-base-y-a-la-base-1)
    - [XOR](#xor)
    - [Suma y resta (sistema combinacional)](#suma-y-resta-sistema-combinacional)
    - [Multiplicacion (sistema combinacional)](#multiplicacion-sistema-combinacional)
    - [Decodificador (sistema combinacional)](#decodificador-sistema-combinacional)
    - [Codificador (sistema combinacional)](#codificador-sistema-combinacional)
    - [Multiplexor (sistema combinacional)](#multiplexor-sistema-combinacional)
  - [Sistemas secuenciales](#sistemas-secuenciales)
  - [Diseño de una CPU](#diseño-de-una-cpu)
  - [ARM](#arm)
    - [Assembly](#assembly)

## Algebra de Boole

Se utiliza para describir la interconexión de compuertas digitales y para **transformar** **diagramas de circuitos** en **expresiones algebraicas**

El algebra de Boole es todo conjunto de elementos que solo pueden tomar los valores 0 o 1, relacionados mediante **operaciones binarias** (no aritmeticas) llamadas **suma logica** (+), **producto logico** (*) y complementacion o **inversion** (/ -) y cumplen con los siguientes **postulados** (axiomas):

### Postulados

1. Ambas operaciones son **conmutativas**:
    - a+b = b+a
    - a.b = b.a

2. Posee 2 **elementos neutros** (0 y 1) que cumplen con la propiedad de **identidad** con la suma y producto logico respectivamente:
   - 0+a=a
   - 1.a=a

3. Cada operacion es **distributiva** con respecto a la otra:
   - a.b(b+c) = a.b + a.c
   - a+b.c = (a+b).(b+c)

4. Para cada elemento a existe un <span style="text-decoration:overline">a</span> (**a negado**) tal que:
   - a+ <span style="text-decoration:overline">a</span> = 1
   - a.<span style="text-decoration:overline">a</span> = 0

**Ejemplos con llaves**
![circuitos](./img/boole/circuitos.png)
**Postulados con llaves**

1. ![1_llaves](./img/boole/1_llaves.png)
2. ![2_llaves](./img/boole/2_llaves.png)
3. ![3_llaves](./img/boole/3_llaves.png)
4. ![4_llaves](./img/boole/4_llaves.png)

### Logica con Boole (Tablas de verdades)

1. OR
   - 0+0 = 0
   - 0+1 = 1
   - 1+0 = 1
   - 1+1 = 1
2. AND
   - 0.0 = 0
   - 0.1 = 0
   - 0.1 = 0
   - 1.1 = 1
3. NOT
   - a = 1 y <span style="text-decoration:overline">a</span> = 0

**Compuertas**: materializar operaciones logicas (?)

![compuertas](./img/boole/compuertas.png)

### Teoremas

**Principio de dualidad**
Dada una **igualdad** (=), si se cambia suma lógica (+) por producto lógico (.), producto lógico por suma lógica, ceros por unos y unos por ceros, la **igualdad permanece válida**.

Se demuestra por la **simetría** de los postulados

**Ley de la absorcion**

> a+a.b = a

![compuertas](./img/boole/absorcion.png)

**Teorena del concenso**

> x.y + <span style="text-decoration:overline">x</span>.z +y.z = x.y + <span style="text-decoration:overline">x</span>.z

**Demostracion**

> x.y + <span style="text-decoration:overline">x</span>.z +y.z = x.y + <span style="text-decoration:overline">x</span>.z +y.z. (x+<span style="text-decoration:overline">x</span>)
> 
> =  x.y + <span style="text-decoration:overline">x</span>.z +y.z + <span style="text-decoration:overline">x</span>.y.z
> 
>= x.y + x.y.z+ <span style="text-decoration:overline">x</span>.z + <span style="text-decoration:overline">x</span>.y.z
> 
>= x.y . (1+z) + <span style="text-decoration:overline">x</span>.z . (1+y)
>  
> = x.y + <span style="text-decoration:overline">x</span>.z

**Teorema de Morgan**

><span style="text-decoration:overline">/(x+y)</span> = <span style="text-decoration:overline">/x</span> . <span style="text-decoration:overline">/y</span>
> 
> <span style="text-decoration:overline">/(x.y)</span> = <span style="text-decoration:overline">/x</span> + <span style="text-decoration:overline">/y</span>

**Tablas de verdades para verificar Morgan**

![Morgan](./img/boole/morgan.png)

### Funcion en Boole
(Desde ahora <span style="text-decoration:overline">x</span> = /x)

Una **función** del álgebra de Boole es una **expresión algebraica** en las que aparecen las **variables** de las cuales la **función depende** en forma **directa o negada** y relacionadas por las operaciones de **suma lógica** y/o **producto lógico**.

>f(a,b,c) = a.b.c + /a.b./c + /b./c + a./b = (a+b+c).(/a+b+/c).(/b+/c).(a+/b) (Por dualidad)

**Terimno Canonico**

Un término es **canónico** cuando aparecen **todas las variables** de las cuales la función depende ya sea en **forma directa o negada**.

>f(a,b,c) = a.b.c + /a.b./c + /b./c + a./b = (a+b+c).(/a+b+/c).(/b+/c).(a+/b)(El primer termino es producto / suma canonica)

**Funcion canonica**

Una función es **canónica** cuando **todos** sus **términos** son **canónicos**. Puede ser expresada como suma de productos canónicos o como producto de sumas canónicas.

En una función expresada como **suma de productos canónicos**, cada producto canónico representa un **uno** de la función. Basta que **uno** de los **términos** sea uno para que la **función valga uno**.

En una función expresada como **producto de sumas canónicas**, cada **suma canónica** representa un **cero** de la función. Basta que **uno** de los **términos** sea **cero** para que la **función valga cero**.

Tanto la suma de productos como el producto de sumas constituyen la **representación algebraica de la función**. 

**Respresentacion de la funcion con tablas de verdad**

![f_tablas](./img/boole/funciones_tablas.png)

- **Suma de productos**: Usamos los 1 (miniterminos)
- **Producto de sumas**: Usamos los 0 (maxterminos)

**Representacion esquematica de la funcion**

![Funcion esquematica](img/boole/funcion_esquematica.png)

## Simplificacion por Karnaugh

**¿Por que simplificar?**

- Los esquemas de las funciones tendrian **menos** compuertas y entradas
- Las funciones de Boole pueden tener **mas** de una minima expresion
- El metodo de Karnaugh ofrece una forma mas **simple** que la algebraica para simplificar funciones (para suma de productos)

### Adyacencia logica

Los términos son adyacentes lógicamente cuando **difieren** solamente en el **estado** de **una variable**. (Ej: a./b.c + a.b.c Difieren en la variable b.) 

### Mapa de Karnaugh

cada casilla del mapa es ADYACENTE físicamente y lógicamente con la que tiene al lado.
- Los elementos de los bordes son adyacentes logicamente con los de los bordes del otro extremo
- Los elementos de las esquinas son adyacentes logicamente con los elementos de las esquinas "paralelas" (L)

![mapa](img/simplificacion/karnaugh.png)

**Agrupando**

1. Se agrupan los unos del mapa con la **menor cantidad de agrupamientos** posibles y con la **mayor cantidad** posibles **de unos por agrupamiento**.
2. Los agrupamientos de los unos pueden ser hechos de a uno, dos, cuatro, ocho, etc.

![Agrupando](img/simplificacion/agrupando.png)

**Extrayendo la funcion simplificada**

- Habrá tantos **términos** en la función como **agrupamientos** haya en el mapa.
- La variables adoptarán la forma **directa o negada** de acuerdo a si en el mapa valen **uno o cero**.
- Las variables que **cambian** dentro del agrupamiento **desaparecen**.

![Simplificando](img/simplificacion/simplificando.png)

**Resultado en el esquema**

![Nuevo esquema](img/simplificacion/esquema.png)

## Sistemas combinacionales

Es un sistema donde las salidas dependen puramente del valor de las entradas.

![](img/s_combinacional/s_combinacional.png)

(Es como una fucnion con **n salidas**)

### Condiciones sin cuidado (no importa)

Hay aplicaciones donde la funcion **no se especifica** para ciertas combinaciones de las variables.

![](img/s_combinacional/sin_cuidado.png)

Estas condiciones se pueden aprovechar para **simplificar** aun mas la funcion con **Karnaugh**.

![](img/s_combinacional/simplificado.png)

## Aplicaciones del algebra de Boole

- Sistema de alarmas
- Sistema de votacion
- Operaciones en una CPU

## Operaciones en un CPU (sistema combinacional)

### Complemento a la base y a la base-1

Dado un número N en base β que tiene n dígitos,
el complemento a (β-1) de N se define como: (β^n -1)-N Y el complemento a β de N se define como:  β^n -N 

Para obtener el complemento en base 2 (binario) simplemente cambiamos los 0's por 1's y al resultado final le sumamos 1.

### XOR

Esta compuerta es un **Xor**:

![](img/s_combinacional_2/xor.png)

Que tiene esta tabla de verdad:

![](img/s_combinacional_2/xor_tabla.png)

Y se denota asi:

![](img/s_combinacional_2/xor_d.png)

### Suma y resta (sistema combinacional)

Para poder hacer operaciones de **suma** y **resta** en un CPU, se  usa el **sumador paralelo binario** (en este ejemplo es de 4 bits).

![](img/s_combinacional_2/sumador_paralelo_binario.png)

Donde FA = FULL ADDITION y su tabla es

![](img/s_combinacional_2/fa/fa_1.png)

En forma algebraica:

![](img/s_combinacional_2/fa/fa_2_1.png)
![](img/s_combinacional_2/fa/fa_2_2.png)

En forma de compuertas

![](img/s_combinacional_2/fa/fa_3.png)


Donde los parametros de entrada son A_n, B_n y S.

A_n y B_n son los numeros a sumar/ restar.

Si S es 0, entonces el sistema suma los 2 componentes A_n y B_n. Si en cambio es 1, el Xor se encarga de transformar B_n en el complemento en base 2, para asi efectuar una resta (En este caso, C_0 seria 1, y creeria yo que C_4 no se tomaria en el resultado final).

### Multiplicacion (sistema combinacional)

La multiplicacion se diagrama asi:

![](img/s_combinacional_2/multi/multi_1.png)

Que es lo mismo que esto:

![](img/s_combinacional_2/multi/multi_2.png)

Donde HA es half addition y funciona asi:

![](img/s_combinacional_2/multi/ha.png)

### Decodificador (sistema combinacional)

El decodificador es un circuito combinatorio que convierte info binaria de n entradas a 2^n salidas:

![](img/s_combinacional_2/deco.png)
![](img/s_combinacional_2/deco_1.png)

**Implementacion**

![](img/s_combinacional_2/deco_2.png)

### Codificador (sistema combinacional)

El codificador realiza la operación inversa de un decodificador.

### Multiplexor (sistema combinacional)

Un multiplexor es un circuito combinatorio que **selecciona** información binaria de una entre **muchas líneas de entrada** y la dirige a **una sola línea de salida**.

![](img/multiplexor/multiplexor_1.png)

**Implementacion de ejemplo**:

Se puede implementar una función booleana de n variables con un multiplexor que tiene n-1 entradas de selección. Las primeras n-1 variables de la función se conectan a las entradas de selección del multiplexor. La variable que resta de la función se la utiliza para la entrada de datos.

![](img/multiplexor/multiplexor_2.png)

## Sistemas secuenciales

En los sistemas secuenciales, a diferencia de los combinacionales, las salidas dependen no solo de las entradas, sino tambien de los **estados internos**.

![](img/s_secuenciales/s_sec_1.png)

Los estados internos dependen de la **memoria** y el **tiempo**.

- Tiempo: onda periodica entre 0 y 1

![](img/s_secuenciales/time.png)
- Memoria: Flip-Flop (celda elemental de memoria de 1 bit, almacena valor posible 0 o 1)

![](img/s_secuenciales/flip_flop.png)

**Flip-Flop-D (Delay)** D_t = Q_(t+1) (?)

**Caja negra**:

![](img/s_secuenciales/black_box.png)

**Diagrama de estados**

![](img/s_secuenciales/d_estados.png)
![](img/s_secuenciales/t_v.png)
![](img/s_secuenciales/kar.png)
![](img/s_secuenciales/xd.png)

## Diseño de una CPU

Una CPU (unidad central de procesamiento) es un **gran sistema secuencial** formado por una `unidad procesadora` (que dentro contiene la unidad aritmetica y logica `ALU`) y la `unidad de control` (corrimiento?).

Todos los diseños de sistemas digitales son diseños **jerarquicos** y **modulares**.

Podemos diagramar usando el diagrama de bloques o el de sincronizacion.

![](img/CPU/diagramitas.png)

R1 y R2 son registros. Un **registro** es un conjunto de n flip-flops D.

Esta es una implementacion para un registro de 4 bits.

![](img/CPU/registro_4.png)

Aca vemos un diagrama de sincronizacion usando u contador y un decodificador.

![](img/CPU/sincro.png)

`Modulos`: Cajas negras

`Primitivas`: bloques and/or/xor/etc.

Implementacion de una **unidad procesadora**

![](img/CPU/up.png)

Dicha unidad procesadora contiene 2 modulos "grandes" que vamos a ver a continuacion:

El primero es el `ALU` (Aritmetic and logic unit). Este es un **sistema combinacional** que se encarga de realizar una operacion **aritmetica** o **logica** con los datos que reciba segun la **eleccion** que se escoja.

El ALU esta a su vez compuesto por un modulo aritmetico y uno logico que realizan sus respectivas operaciones (segun la eleccion). Las operaciones aritmeticas que se pueden realizar son las siguietntes:

![](img/CPU/aritmetica.png)

Las operaciones del modulo logico son:

![](img/CPU/logic.png)

En el alu, los 2 modulos realizan sus respectivas operaciones, pero luego, en un multiplexor se decide cual de las 2 se dirige a la salida.

![](img/CPU/alu.png)

En general, las operaciones que se pueden realizar en un modulo ALU completo son:

![](img/CPU/alu_t.png)

El otro modulo perteneciente al CPU es la **unidad  de corrimiento**. Esta puede desplazar y rotar el dato ingresado x bits hacia la izq o der. En los desplazamientos, se pierde un bit por un lado, y por el otro se coloca un 0. En las rotaciones, el bit "perdido" se inserta al otro extremo de numero.

Los desplazamientos a izquierda equivalen a la multiplicacion del numero por 2, y los desplazamientos a derecha equivalen a una divicion por 2.

La unidad de corrimiento puede ser normal, o **tambor**.

![](img/CPU/corrimiento.png)

En un CPU, utilizando todas las entradas empleadas para realizar una operacion, se puede armar una palabra hexadecimal que represente dicha operacion. 

![](img/CPU/hexa.png)
![](img/CPU/hexa_2.png)
![](img/CPU/hexa_3.png)

## ARM

El ARM es una arquitectura de los microprocesadores (no es obligatorio que los micros utilizen esta arquitectura, los celulares utilizan otra). Esta arquitectura obtuvo varias actualizaciones a lo largo de los años, siendo la mas actual la de 64 bits. Aqui solo estudiaremos la version de 32 bits.

Que la arquitectura tenga 32 bits significa que los elementos con los que trabajara seran de maximo 32 bits.

`Terminologia importante:`
- **Byte** (8 bits)
- **HalfWord** (16 bits, 2 bytes)
- **Word** (32 bits, 4 bytes)
- **Nipble** (4 bits)

La arquitectura de un ARM es como la siguiente:

![](img/arm/arm.png)

Los ARM son capaces de trabajar con SO multitareas. Por lo tanto permiten distintos modos para operar el procesador. Estos son:

- User: Sin privilegios
- ...
- Supervisor
- ...
- System: Con todos los privilegios.

**Registros visibles para cada modo:**

![](img/arm/modos.png)

* Cada registro tiene 32 bits
* 13: stack pointer
* 14: Link register
* 15: Program Counter
* CPSR -> Current Program Status Register (N.Z.C.V)

`PSR`

![](img/arm/PSR.png)

![](img/arm/PC.png)

### Assembly

Condicionales:

![](img/arm/cond.png)

Instrucciones:

![](img/arm/ins_1.png)
![](img/arm/ins_2.png)
![](img/arm/ins_3.png)

El sintaxis para las operaciones es:

`<operation> {<conditional>} {s} Rd, Rn, Operand2`

Donde los comparadores solo setean flags, Los movimientos de datos se guardan en Rd, y los shifteos se aplican sobre el operando 2.

![](img/arm/barrel_shifter.png)

Todas las instrucciones del ARM son de 32 bits, es decir que en 32 bits debemos indicar toda la operacion que el ARM tiene que realizar.

Por defecto, el ARM de arquitectura de 32 bits tiene reservado 12 bits para el operando 2, de los cuales 8 son para el valor numerico, y 4 para indicar la rotacion.

![](img/arm/operand_2_size.png)

El ARM utiliza "trucos" como estos para hacer constantes mas grandes:

![](img/arm/constantes_truco.png)

Los registros pueden tener 32 bits de capacidad (?), pero las constantes no porque deben ser de 12 bits para poder ser rotadas. podemos hacer constantes mas grandes (al guardarlas en registros) mediante varios comandos, utilizando este "truco":

![](img/arm/registros_grandes.png)

Aunque la forma recomendada de cargar constantes mayores a 8 bits en un registro es esta (load register):

![](img/arm/recomendacion_registros_grandes.png)

Empezamos a tocar memoria.

Si queremos pasar datos de la memoria al registro, usamos LDR, en cambio si queremos pasar datos del registro a la memoria, usamos STR:

![](img/arm/memoria_1.png)

Ya sea mediante STR o LDR, siempre que querramos acceder a una posicion en memoria lo tenemos que hacer mediante corchetes, y usando la siguiente sintaxis:

![](img/arm/acceder_a_memoria.png)

En donde el primer elemento, es un registro base, al que le podemos sumar o restar una constante o un registro (y este segundo registro lo podemos correr con LSR, LSL, etc. mediante el barrel shifter)

`NO ENTENDI: for haldword and signed halfword / byte, offset can be: ...`

![](img/arm/pos_pre_index.png)

La memoria tambien puede ser accedida mediante pre o pos index:

En el pre index la constante es sumada al registro base (que servira como index para acceder a la memoria) antes de aceder a dicha memoria. El registro base se puede actualizar (sumar la constante, o el registro) utilizando el signo de exclamacion como lo muestra la imagen.

En el pos index, primero se accede a la posicion de memoria indicada por el registro base, y luego este registro se lo actualiza sumando o restando la constante.

En un registro de memoria se pueden guardar 8 bits (o un byte). al guardar datos mas pesados que estos en una direccion de mememoria se utiliza el metodo [little endian](https://es.wikipedia.org/wiki/Endianness)

Se pueden guardar o cargar multiples direcciones de memoria con multiples registros mediante el siguiente comando, usando sus respectivos modos de acceso:

![](img/arm/multiple_add.png)

El arm realiza la multiplicacion mediante la **mezcla** entre operaciones de **desplazamiento** y **suma**, optimizando asi la cantidad de ciclos de reloj necesarios para realizar dicha multiplicacion.

Cuando usamos la multiplicacion es muy probable que lleguemos a un **desbordamiento**. En una arquitectura de 32 bits, para que no se produzca esto deberiamos de tener una capacidad el doble de grande que el de los dos numeros a multiplicar. Es decir que, si quisieramos multiplicar dos numeros de 32 bits, necesitariamos tener un numero con espacio para 64, y para poder multiplicar en una arquitectura de 32 bits, los numeros a multiplicar **no** deberian **sobrepasar** los **16 bits**.

En terminos generales, la ARM no proporciona nemotecnicos de **division** y por ejemplo el lenguaje C utiliza corrimientos.

**Branch**

El registro numero 15 es el **program counter** (PC) que se encarga de referenciar a la siguiente linea de codigo que se debera ejecutar. Cuando nosotros hacemos un `branch <label>` lo que hacemos es cambiar el PC a la linea correspondiente al label indicado.

El nemotecnico branch tiene un argumento que le podemos pasar que es `l`, quedando asi:

`b<l><cond> <label>`

Lo que hace este `l` es **actualizar** el registro 14 o **link register** (LR) con la direccion de la linea siguiente a la llamada a branch. Esto se hace con la funcion de cuando terminamos el "salto" **poder volver** al punto en donde saltamos (Seria como una **funcion** en un lenguaje de alto nivel).

**Uso recomendado de los registros (en funciones ?).**

![](img/arm/uso_registros.png)

- Los registros que podemos modificar libremente son r0, r1, r2, r3 (argumentos y retornos)
- Los registros del r4, al r11 se pueden usar pero sus **valores originales** deben ser **preservados** para que no se generen **conflictos** (Para eso haremos uso del registro numero 13 o **stack pointer** SP)
- El r12 se puede usar (creo)
- Los registros r13, r14 y r15 son generalmente  actualizados por la maquina en si.

Para poder usar y preservar los valores de los registros del r4 al r11 hacemos uso del registro r13 y el stack (memoria libre para guardar x cantidad de registros)

El procedimiento para realizar esto es el siguiente:

![](img/arm/stack.png)

![](img/arm/push_pop.png)

Para poder hacer subrutinas anidadas (con branches) debemos de guardar en el stack los LR

![](img/arm/subrutinas.png)
