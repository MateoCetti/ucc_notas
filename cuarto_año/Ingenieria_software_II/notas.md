# Ingenieria de Software 2

- [Ingenieria de Software 2](#ingenieria-de-software-2)
- [[07-03-22] - Modelado y Diagrama de casos de uso](#07-03-22---modelado-y-diagrama-de-casos-de-uso)
  - [Modelo](#modelo)
    - [Herramientas de modelado](#herramientas-de-modelado)
    - [Diagramas de casos de uso](#diagramas-de-casos-de-uso)
- [[08-03-22] Repaso Ing. Soft. 1](#08-03-22-repaso-ing-soft-1)
  - [Calidad](#calidad)

**Profe practico**: Pablo Córdoba

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