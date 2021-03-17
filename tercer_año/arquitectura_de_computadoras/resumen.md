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