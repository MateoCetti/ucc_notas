# Ingenieria de Software 2

- [Ingenieria de Software 2](#ingenieria-de-software-2)
- [[07-03-22] - Modelado y Diagrama de casos de uso](#07-03-22---modelado-y-diagrama-de-casos-de-uso)
  - [Modelo](#modelo)
    - [Herramientas de modelado](#herramientas-de-modelado)
    - [Diagramas de casos de uso](#diagramas-de-casos-de-uso)
- [[08-03-22] Repaso Ing. Soft. 1](#08-03-22-repaso-ing-soft-1)
  - [Calidad](#calidad)
- [[15-03-22] Visión general de UML](#15-03-22-visión-general-de-uml)
  - [UML](#uml)
  - [Modelado de casos de uso](#modelado-de-casos-de-uso)
    - [Elementos](#elementos)
    - [Pre y post condiciones](#pre-y-post-condiciones)
  - [Procesos de desarrollo](#procesos-de-desarrollo)
  - [proceso unificado de desarrollo de software](#proceso-unificado-de-desarrollo-de-software)
    - [El cliclo de vida del proceso unificado](#el-cliclo-de-vida-del-proceso-unificado)
- [[21-03-22] Casos de uso con trazo fino y grueso](#21-03-22-casos-de-uso-con-trazo-fino-y-grueso)
  - [Trazo fino](#trazo-fino)
  - [Trazo grueso](#trazo-grueso)
  - [Diagrama de clases de dominio](#diagrama-de-clases-de-dominio)

**Profe practico**: Gerardo Fernando Córdoba.

**Profe teorico**: Natalia Mira (ncmira@gmail.com) 

# [07-03-22] - Modelado y Diagrama de casos de uso

Siempre nos vamos a encontrar con **requerimientos**, cualquier sea la rama que nos especifiquemos. Es muy importante aprender a **identificarlos** y **procesarlos**

**Objetivos**

* Comprender la **importancia** de **modelar**.
* Aprender a utilizar el **diagrama** de **casos de usos**.
* **Resolver** una problematica real utilizando el diagrama de casos de uso

## Modelo

Es una **representacion** en un cierto medio de algo que ayuda a **visualizar** el **sistema** o idea.

El modelo no busca tener todo el detalle, sino que trata de captar lo **importante** mediante un **punto** de **vista** **especifico** para simplificar / abstraer.

Se busca **reducir** la **complejidad** inherente de los sistemas grandes.

**Abstraer -> especificar -> Describir**

### Herramientas de modelado

**UML** (Lenguaje unificado de modelado)
* Distintos tipos de **diagramas**.
  * **Estructurales**: Elementos del sistema y sus relaciones .
  * **Comportamiento**: Funcionalidad del sistema en el tiempo.

### Diagramas de casos de uso

Especifica requerimientos funcionales. Se trata de identificar:
* **Actores**.
* **Casos de uso**.
* **Relaciones entre actores y casos de uso**.
* **Relaciones entre casos de uso y casos de uso**.
* Tambien pueden haber **relaciones** **entre actores**(?)

**Tipos** de **relaciones**:
* **include**: Si se da un caso de uso, el otro tambien se tiene que dar
* **Extend**: Agrega funcionalidad a otro caso de uso, que puede ejecutarse o no, es decir es **optativo**.
* **Generalizacion**: Herencia / Como POO.

![](img/dcu_relaciones.png)

# [08-03-22] Repaso Ing. Soft. 1

* En el transcurso de la materia se hara un especial enfasis en el analisis de los requerimientos de un sistema, en el modelado y diseño del mismo.
* Se utilizara mediante trabajos practicos un proceso de desarrollo especifico utilizado por la profesora
* Se aplicaran conceptos y tecnicas para lograr diseños de calidad


## Calidad
* Modularidad
* Usabilidad
* Confiabilidad
* Robustez
* Complejidad
* Arquitectura
* Reusabilidad
* Portabilidad
* Mantenibilidad

El proceso de desarrollo consta (en terminos generales) de:
* Definir un objetivo
* Definir el alcance
* Definir los modulos o subsistemas (Quizas listar primero las funcionalidades)
* Realizar modelos de casos de uso
* Realizar diagramas de objetos de dominio (?)

# [15-03-22] Visión general de UML

Un modelo es la **abstraccion** de un sistema que nos permite ocuparnos de **detalles relevantes** para un proposito para abordar sistemas complejos.

Para realizar un modelado exitoso hay que utilizar un **lenguaje visual** que sea **sencillo** de **interpretar** y procesar.

Algunos de los **beneficios** de realizar modelado de sistemas son los siguientes:

* Nos ayudan a **visualizar** un **sistema** como es, o como queremos que sea.
* Nos permiten **especificar** la **estructura** o el **comportamiento** de un sistema.
* Nos dan una plantilla que nos **guía** en la **construcción** del sistema.
* **Documentan** las **decisiones** que hemos tomado.
* Nos **facilitan** la **comunicación** con el **cliente**.

```
Nota: La elección de qué modelos crear tiene una profunda influencia en cómo atacamos un problema y cómo delineamos una solución.
```

```
Nota: Un único modelo no es suficiente. Cualquier sistema es enfocado mejor con un conjunto de modelos independientes, pero relacionados.
```

**Conceptos** del modelado

* **Sistema software**: Descripto por un conjunto de modelos
* **Modelo**: Simpllificacion para comprender major un sistema
* **Diagrama**: Representacion grafica de un modelo (UML usa grafos)
* **Vista**: Subconjunto de diagramas de un modelo que analiza un aspecto concreto

En el contexto del software hay **cinco vistas** complementarias que son las mas importantes para visualizar, especificar, construir y documentar una arquitectura software
* Vista de **casos de uso**
* Vista de **diseño**
* Vista de **interacción**
* Vista de **implementación**
* Vista de **despliegue**

Cada una de estas vistas involucra modelado **estructural** y modelado de **comportamiento**.

![](img/vistas.png)

```
Nota: En el modelado Orientado a Objetos la vision actual del desarrollo de software toma una perspectiva orientada a objetos.
```

```
Nota: La Ingeniería dirigida por modelos (MDE) es un enfoque para el desarrollo de software donde los modelos en lugar de los programas son los principales resultados del proceso de desarrollo. Los programas que se ejecutan en una plataforma de hardware / software se generan automáticamente a partir de los modelos.
```

## UML

Es un **lenguaje** de **modelado**, de propósito general, usado para la visualización, especificación, construcción y documentación de sistemas Orientados a Objetos.

Decimos que es un **lenguaje** ya que provee un **vocabulario** y **reglas** para **combinar** los **elementos** del vocabulario con el propósito de comunicar. 

## Modelado de casos de uso

Muestra un **conjunto** de **Casos de Uso**, **actores** y sus
**relaciones**.

Permite establecer el **comportamiento** **deseado** del sistema. Especifica los **requerimientos funcionales** del Software.

Algunos **beneficios** del modelado de casos de uso son los siguientes:

![](img/beneficios_casos_uso.png)

### Elementos

**Casos de uso**

Los Casos de Uso se **determinan** observando y precisando, actor por actor, las secuencias de **interacción**, los escenarios, desde el punto de vista del usuario

Un **escenario** es una instancia de un caso de uso.

**Actores**

Representa un rol que interactúa con el sistema, puede ser un **usuario** humano u **otro sistema** o dispositivo de **hardware**. El nombre del actor debe **describir** el **papel desempeñado**.

Hay actores **principales** (IZQ): son los que **usan** el sistema **directamente**; para quienes desarrollamos el sistema. 

Hay actores **secundarios** (DER): son aquellos de los que el **sistema** necesita **ayuda** para poder cumplir con el objetivo del Caso de Uso. Son aquellos que **mantienen** o **administran** el sistema.

**Relaciones**

**Extension**

Especifica como un Caso de Uso puede insertarse y así **extender** la
**funcionalidad** de **otro**. Se usan para modelar partes **optativas**, alternativas, etc.

Se dibuja con una flecha cuya dirección va **desde** el Caso de Uso de
extensión (**adicional**) **al** Caso de Uso **base**.

![](img/extend.png)

**Inclusion**

Se usan cuando su **intervención** es **necesaria** para **completar** un
**curso** completo de **eventos**.

Se dibuja con una flecha **desde** el Caso de Uso concreto o **base** **al** use case abstracto (**adicional**).

![](img/include.png)

**Generalizacion**

Un Caso de Uso más **especifico** puede **especializar** a un Caso de Uso
más **general**.

Se dibuja con una flecha **desde** el Caso de Uso **hijo al padre**.

![](img/general.png)

### Pre y post condiciones

![](img/pre_post_c.png)

Una **pre-condición** es una **restricción** sobre **cuando** un Caso de Uso puede **empezar**. No es el evento que inicia el Caso de Uso.


Una **post-condición** para un Caso de Uso debe ser **verdadera**, **independientemente** de cual **flujo** sea **ejecutado**.

## Procesos de desarrollo

Hay 3 tipos: **Evolutivo**, **planificado** y de **reutilización**

Cual elegir dependera de ciertos criterios ca considerar:

1. Nivel de **flexibilidad** de los **requerimientos**
2. escala y el **alcance** del **desarrollo**
3. que conviene más teniendo en cuenta lo que exige el cliente (Plazos y tamaño del proyecto)
4. Definir los **usuarios finales** claramente
5. Considerar **donde** se **ubica** el **equipo** de desarrollo

```
Nota: En cualquier modelado es importante destacar correctamente el objetivo del sistema a elaborar.
```

## proceso unificado de desarrollo de software

Es un proceso **ORIENTADO A OBJETOS**
El proceso es:
* Guiado por **casos de uso**:
  * Los sistemas se crean para dar servicio a los usuarios.
  * Un CASO de USO es una pieza de **FUNCIONALIDAD** de un sistema que le proporciona a algún **USUARIO** un RESULTADO o **VALOR**.
* Centrado en la **arquitectura**:
  * La arquitectura de un sistema software es un **extracto** de los modelos del sistema que da una **idea** de qué **forma** tiene el **sistema** completo.
* Con un ciclo de vida **iterativo** e **incremental**:
* Se repiten VARIOS **MINIPROYECTOS**, cada miniproyecto **AMPLIA** EL **PRODUCTO**.

### El cliclo de vida del proceso unificado

Un ciclo de vida se **repite** a lo largo del tiempo. Tras cada ciclo de vida se genera una **versión nueva** del producto, un ciclo de vida se divide en **fases**, cada fase se divide en **iteraciones** y en cada iteración se realizan **flujos** de trabajo

![](img/cv_pu.png)

Cada **ciclo** constas de **cuatro fases**: **inicio**, **elaboración**, **construcción**, y **transición**.

![](img/fases.png)

El **producto** generado a partir de un PU no es sólo **código** ejecutable, sino que son los **modelos** o **representación** del software.

# [21-03-22] Casos de uso con trazo fino y grueso

## Trazo fino
Descripcion **detallada** de la funcionalidad de uno o varios casos de uso

* **Brinda** un **contexto** del caso de uso en cuestion, 
* **Define precondiciones** para que se de un caso de uso, 
* **Define** que **acciones** realiza un actor y el sistema como un **flujo continuo** de **pasos**.
* Describe el **camino feliz** y **flujos alternatiavos** de la interaccion actor-sistema.
* Define las post condiciones que un caso de uso realiza al finalizar.
* Ayuda a ver las **relaciones** entre los diferentes **casos de uso** que definen una **funcionalidad**.

## Trazo grueso
SOLO da una **descripcion detallada** de al funcionalidad de un caso de uso, nada mas.

## Diagrama de clases de dominio

¿Que es? Es un:
* Vista general de los conceptos de negocio de mas alto nivel.
* Representacion visual de las clases conceptuales del mundo real en un dominio de interes
* Diccionario visual de abstracciones 

En un diagrama de clases de dominio graficamos **clases**, **asociaciones** y **atributos**.

Una **clase** es una idea, cosa u objeto, es un **concepto** dentro del sistema que estamos modelando.

Las **asociaciones** representan **relaciones** entre las instancias de las clases. Las relaciones pueden ser:
* 1 a 1
* 1 a M
* M a M

Las asociaciones tambien pueden tener **nombres**.

Las asociaciones tambien tienen **clases**, es decir, aquello que se forma a partir de la llevada a cabo de una relacion.

![](img/clase_asociacion.png)

Los **atributos** son:
* Valor de datos logico de un objeto
* Es donde se modela o representa el dato para luego producir la informacion que nuestros sistemas bajo estudio gestionan
* Es esa informacion que necesito registrar dado ciertos requisitos y teniendo en cuenta siempre el DOMINIO que se esta analizando.

`NOTA: Para las asociaciones, no plasmamos las foreign keys como atributos de las clases.`

![](img/solo_la%20asociacion.png)

`NOTA: Los atributos multiples no se modelan como otras clases.`

![](img/attr_multiples.png)

`NOTA: Los atributos derivables se modelan de esta forma:`

![](img/attr_derivable.png)

Clase asociativa:

![](img/clase_asociativa.png)

Asociacion derivable:

![](img/asociacion_derivable.png)