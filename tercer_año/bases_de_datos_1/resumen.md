# Resumen de base de datos 1

- [Resumen de base de datos 1](#resumen-de-base-de-datos-1)
  - [SGBD](#sgbd)
    - [Modelos de datos:](#modelos-de-datos)
    - [Usuarios de bases de datos:](#usuarios-de-bases-de-datos)
    - [Estructura general del sistema](#estructura-general-del-sistema)

## SGBD

Los sistemas de gestión de bases de datos o SGBD son un tipo de software dedicado a servir de **interfaz** entre la **base de datos**, el **usuario** y las **aplicaciones** que la utilizan. El propósito general de los SGBD es el de **manejar** de manera clara, sencilla y ordenada un **conjunto de datos** que posteriormente se convertirán en **información relevante** para una organización.

**Objetivos**:

* **Abstracción de la información**. Los SGBD **ahorran** a los usuarios detalles acerca del **almacenamiento físico** de los datos. Da lo mismo si una base de datos ocupa uno o cientos de archivos, este hecho se hace **transparente** al usuario. Así, se definen varios **niveles de abstracción**.
* **Independencia**. La independencia de los datos consiste en la capacidad de **modificar** el esquema (físico o lógico) de una base de datos **sin** tener que **realizar cambios** en las **aplicaciones** que se sirven de ella.
* **Consistencia**. La base de datos representa una realidad determinada que tiene determinadas condiciones, por ejemplo que los menores de edad no pueden tener licencia de conducir. El sistema no debería aceptar datos de un conductor menor de edad. En los SGBD existen **herramientas** que facilitan la **programación** de este tipo de **condiciones**.
* **Seguridad**. La información almacenada en una base de datos puede llegar a tener un gran valor. Los SGBD deben **garantizar** que esta **información** se encuentra **segura** de permisos a usuarios y grupos de usuarios, que permiten otorgar diversas **categorías de permisos**.
* **Manejo de transacciones**. Una transacción es un programa que se ejecuta como una sola operación. Esto quiere decir que luego de una ejecución en la que se produce una falla es el mismo que se obtendría si el programa no se hubiera ejecutado. Los SGBD proveen mecanismos para **programar** las **modificaciones** de los datos de una forma mucho **más simple** que si no se dispusiera de ellos.
* **Tiempo de respuesta**. Lógicamente, es deseable **minimizar el tiempo** que el SGBD demora en proporcionar la información solicitada y en almacenar los cambios realizados.

En otras palabras, las bases de datos
- Permiten gestionar **gran cantidad** de **información** 
- Permiten definir **estructuras** para almacenar la información.
- Proveen mecanismos para su **manipulación**
- Garantizan la **fiabilidad** de la información almacenada
- Soportan **caidas del sistema**
- Controlan intentos de **accesos** no **autorizados**
- Administran el uso del SGBD compartido entre usuarios evitando resultados anómalos.

**Sistemas de archivos**

Antes de la existencia de los SGBD, para gestionar los datos se utilizaban sistemas de archivos. Esto traia varios inconvenientes como:

- **Redundancia** e **inconsistencia** de datos.
- **Dificultad** en el **acceso** a los datos
- Aislamiento de datos (diversos archivos con diferentes formatos)
- Problemas de **integridad**
- Problemas de **atomicidad**
- Anomalías en el **acceso concurrente**
- Problemas de **seguridad**

**Niveles de abstraccion**:

Niveles en los que los datos son almacenados, gestionados y visualizados.

- **Nivel fisico**: describe cómo se **almacenan** realmente los datos en disco.
- **Nivel lógico**: describe qué datos se almacenan en la **base de datos** y las **relaciones** existentes entre ellos.
- **Nivel de vistas**: los **programas** de aplicación **ocultan** detalles de los tipos de **datos**. Las vistas también pueden ocultar **información** (p. e., salarios) por razones de **seguridad**.

**Instancias y esquemas**

**Esquema**: Análogo a la información del **tipo** de una **variable** en un programa
- **Esquema físico**: diseño de la base de datos a nivel físico
- **Esquema lógico**: diseño de la base de datos a nivel lógico

**Instancia**: El **contenido real** de la base de datos en un instante de tiempo determinado (Análogo al valor de una variable)

**Independencia física de los datos**: la capacidad de modificar el esquema físico
sin cambiar el esquema lógico (?)

### Modelos de datos:
Colección de herramientas conceptuales para **describir** los **datos**, las **relaciones** entre ellos, la **semántica** de los datos y la **consistencia** entre los datos

**Modelo relacional**:

![Modelo relacional](./img/modelo_relacional.png "Modelo relacional")

- Colección de tablas para representar los **datos** y sus **relaciones**
- Cada tabla tiene **columnas**, y las columnas un nombre único
- Modelo basado en **registros**
- Es el modelo de datos más ampliamente usado

**Modelo de entidad relacion** (E-R):
![Modelo ER](./img/modelo_er.png "Modelo ER")

- Se basa en una **percepción** del **mundo real**
- Consiste en una colección de objetos básicos, **entidades** (cosa o objeto distinguible de otros
objetos) y **relaciones** (una asociación entre varias entidades)

**Modelo de datos orientado a objetos**:
  - Extiende el modelo de datos relacional incluyendo orientación a objetos y construcciones que manejan otros tipos de datos adicionales
  - Incluye los conceptos de **encapsulación**, **métodos** y la **identidad** de los objetos
  - Proporciona compatibilidad hacia arriba con lenguajes relacionales preexistentes. (?)
  - Permite atributos de tuplas con tipos complejos, incluyendo valores no atómicos como son las relaciones anidadas(?)



**Modelo de datos semiestructurados** (XML):
- Permite la **especificación** de **datos** donde los **elementos** de datos individuales del **mismo tipo** pueden tener **diferentes conjuntos de atributos**
- Originariamente era un lenguaje de marcado de documentos, no como lenguaje de base de datos.
- La posibilidad de especificar nuevas etiquetas y crear estructuras de etiquetas anidadas convierten a XML en un mecanismo perfecto para el intercambio de datos, no solo de documentos.

**Modelos antiguos**:
  - Modelo de red
  - Modelo jerárquico

**Lenguaje de manipulación de datos** (DML):
Lenguaje para acceder o **manipular** los datos organizados mediante el modelo de datos apropiado.
Existen dos clases de lenguajes
- Procedimentales: el usuario especifica que datos se necesitan y cómo han de obtenerse dichos datos
- **Declarativos** (no procedimentales): el usuario especifica qué datos se necesitan sin espcificar cómo se han de obtener

SQL (lenguaje **NO PROCEDIMENTAL**) es el lenguaje de consultas utilizado más ampliamente

**Lenguaje de definición de datos** (DDL):
Notación de especificación para **definir** el **esquema** de la base de datos

El compilador DDL genera un conjunto especial de tablas denominado **diccionario** de datos que contiene **metadatos**:
- **Esquema de base de datos**
- **Restricciones de integridad**
- **Autorización**
- etc.

**Diseño de la base de datos**:
Proceso de diseño de la estructura general de una base de datos:

- **Diseño lógico**: Decidir el **esquema** de la base de datos. El diseño de la base de datos requiere encontrar una **buena colección** de **esquemas de relación**.
  - **Decisión de negocio** – ¿Qué atributos se deberían registrar en la base de datos?
  - **Decisión informática** – ¿Qué relación de esquemas se deberían utilizar y cómo se deberían distribuir los atributos entre los distintos esquemas de relación?
- **Diseño físico**: Decidir sobre las características físicas de la base de datos

**Gestión de almacenamiento**:
El gestor de almacenamiento es un **módulo** de programa que proporciona la **interfaz** entre los **datos** de bajo nivel en la base de datos y los **programas de aplicación** y **consultas** emitidas al sistema.

El gestor de almacenamiento es responsable de:
- La interacción con el gestor de ficheros
- El almacenamiento, recuperación y actualización eficiente de los datos

**Procesamiento de consultas**
![proceso consultas](./img/procesamiento_de_consultas.png "proceso consultas")

**Gestión de transaciones**:
Una **transacción** es una **colección de operaciones** que se llevan a cabo como una **única función lógica** en una aplicación de base de datos.

El **componente de gestión de transacciones** asegura que la base de datos permanezca en un estado **consistente** (correcto) a pesar de los **fallos** del sistema (p.e., fallos de energía y caídas del sistema operativo) y de los fallos en las transacciones.

El **gestor de control de concurrencia** controla la **interacción** entre las **transacciones concurrentes** para **asegurar** la **consistencia** de la base de datos.

**Arquitectura de bases de datos**

La arquitectura de una base de datos se ve muy influenciada por el **sistema informático** subyacente sobre el que se está ejecutando:

* Centralizado
* Cliente-servidor
* Paralelo (multi-procesador)
* Distribuido

### Usuarios de bases de datos:
Los usuarios se diferencian por la forma en que esperan interactuar con el sistema:
- **Programadores**: usan DML
- **Usuarios sofisticados**: Realizan querys a las DB
- **Usuarios especializados**: escriben aplicaciones de bases de datos especializadas que no cuadran con el marco de procesamiento de datos tradicional (?)
- **Usuarios normales**: Usan aplicaciones o interfaces.

**Administrador de la base de datos**
Coordina todas las actividades del sistema de la base de datos; posee buenos conocimientos de los recursos y necesidades de información de la empresa. Su funcion es:
- Definición del esquema
- Estructura de almacenamiento y definición del método de acceso
- Modificación del esquema y organización física
- Concesión de autorización para el acceso a los datos
- Especificación de las restricciones de consistencia
- Actuar como enlace con los usuarios
- Supervisión de rendimiento y respuesta a cambios de los requisitos

### Estructura general del sistema

![estructura db](./img/estructura_db.png "estructura db")