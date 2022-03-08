**Profe practico**: Pablo Córdoba
**Profe teorico**: 

# [07/03/22] - Modelado y Diagrama de casos de uso

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