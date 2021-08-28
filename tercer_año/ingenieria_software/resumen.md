# Ingenieria de software

## Notas

* Estudiar los metodos de desarrollo de software en forma disciplinada y precisa.
* Se analiza todo lo relacionado a la gestion de proyectos de software.
* Se enfocan los estandares de calidad.

## Introduccion

La ingenieria de software es una **rama** de la **ingenieria** que aplica teorias, metodos y herramientas para el **desarrollo** de **sofware profesional**.

**¿Porque?**

* Economia suele depender de algun tipo de sofware.
* Cada vez mas sistemas incluyen sofware.
* Gasto en sofware representa una fraccion significativa en el PBI.
* Los errores de sofware suelen ser muy **caros** de **arreglar**.

La ingenieria de sofware tiene que ver con el desarrollo de software rentable. El mantenimiento del mismo es mucho mas costoso que su desarrollo.

`Nota: En un ciclo de vida de un sofware, el software empieza con la idea.`

`Nota: Un sofware para ser tal debe de estar documentado.`

Productos de sofware:
* **Productos Genericos** (El dueño de dicho sofware es el desarrollador del mismo)
* **Productos personalizados** (El dueño de dicho sofware es el cliente del mismo)

El buen software deben entregar al usuario la funcionalidad y desempeño requeridos y deben ser sustentables, confiables y utilizables.

Las actividades fundamentales de la ingenieria de software son la especificacion, desarrollo, validacion y evolucion del sofware.

![](./img/attr_buen_software.png)

La **ingenieria de software** es una disciplina de la ingenieria que se ocupa de todos los aspectos de la produccion de software desde las etapas mas iniciales de la especificacion del sistema hasta el mantenimiento del mismo despues de haber sido desplegado.

* **Disciplina**: Uso de teorias y metodos adecuados teniendo en cuenta las limitaciones financieras y de organizacion
* **Aspectos** de la **produccion** de **software**: No solo el desarrollo tecnico, sino todo el proceso en el ciclo de vida del software.

Actividades en el proceso de software:

* **Especificacion** del software: El cliente nos dice lo que hace falta.
* **Desarrollo** del software: (Autoexplicativo)
* **Validacion** del software: Se verifica la integridad del software
* **Evolucion** del software: Ya estando en operacion, mejoramos, agrandamos, arreglamos, o lo que sea necesario.

**Detalles** que afectan a la mayoria del software:
* **Heterogeneidad**: Los sistemas son cada vez mas grandes, con mas requerimientos, y abarcan mas ambitos.
* **Cambio empresarial** y **social**: A medida que avanza el tiempo, las necesidades de las empresas y las personas cambian, por lo que el software tambien deberia de cambiar para satisfacer dichas necesidades.
* **Sistemas embebidos** y de **control**.

## Procesos de software

Conjunto estructurado de actividades necesarias para desarrollar un sistema de software.
Todos los procesos implican:
* **Especificacion**
* **Diseño** e **implementacion**
* **Validacion** y **verificacion**
* **Evolucion**

Un **modelo** de **proceso** de **sofware** es una representacion abstracta de un proceso. Se presenta una descripcion de un proceso a partir de una perspectiva en particular.

Cuando describimos los procesos, hay que describir...

Procesos dirigidos por **plan** y por **procesos agiles**.

* Desarrollo dirigido por **plan**: Las planificaciones del proceso se planifican con antelacion y el progreso se mide en contra de este plan.
* **Procesos agiles**: La planificacion es **gradual** y es mas facil cambiar el proceso para reflejar los requisitos cambiantes de los clientes.

**No hay** procesos **correctos** o **incorrectos**. Es mas, en la mayoria de los procesos se suelen mezclar ambos procesos en distintas etapas. Pero si hay procesos mal o bien aplicados

**Modelos** de procesos de software:
* **Modelo de cascada**: Modelo sumamente estructurado y rigido (dirigido por plan) etapas y cronologia estrictamente definidas.
* **Desarrollo incremental**: las distintas etapas de desarrollo se intercalan. (puede ser plan o agil)
* **Ingenieria de sofware orientada a reutilizacion**: El sistema se ensambla a partir de componentes existentes.(?)

### Modelo de cascada

![](./img/cascada.png)

**Fases**:
* **Analisis de requerimientos**
* **Diseño y sistema de software**
* **Implementacion y pureba unitaria**
* **Integracion** y **prueba** del **sistema en general**
* **Operacion y mantenimiento**.

El principal inconveniente es acomodar el **cambio** luego de que el modelo se puso en marcha, sin mencionar que es **inflexible** (las necesidades de los clientes cambian con el tiempo). **Pocos sistemas** tienen **requisitos estables**

Este modelo se suele usar en **proyectos grandes** y desarrollados en **varios lugares a la vez**, ya que permite coordinar mejor el trabajo.

### Desarrollo incremental

![](./img/d_incremental.png)

**Beneficios**:
* Costo de atender las necesidades cambiantes del cliente es menor.
* Es mas facil obtener retroalimentacion de los clientes en mitad del desarrollo.
* Entrega y despliegue de software en menor tiempo.

**Contras**

El proceso no es facilmente visible.

La estructura del sistema tiende a degradarse a medida que se añaden nuevos documentos.

A medida que se añaden funcionalidades, se hace mas dificil terminar el proyecto en el tiempo acordado.

### Ingenieria de software orientado a la reutilizacion

Se basa en la reutilizacion sistematica de codigo.

**Etapas**
* Analisis de requerimientos
* Analisis de componentes ya desarrollados
* Modificacion de requerimientos (Ver si podemos utilizar los componentes ya desarrollados para satisfacer los requerimientos de este proyect)
* Configuracion del sistema con la reutilizacion
* Desarrollo e integracion

Ahora se suele reutilizar mucho en la construccion de muchos tipos de sistemas.

## Especificaciones de software

Poder determinar para que va a servir, cuales son las necesidades que este producto de software va a requerir.

Es importante determinar no solamente las **funcionalidades** que debe **brindar** el sistema sino tambien sus **limites**.

Esta etapa se llama **ingenieria** de **requisitos** o **requerimientos**. y tiene **subetapas**:

* **Estudio de factibilidad**: Es factible construir el sistema? Tecnologica y financieramente es posible llevar a cabo el producto? es rentable?
* **Requerimientos, obtención y análisis**: Especificar los servicios que el sistema debe proveer. ¿Que requieren los actores del sistema? (**OJO!** Preguntar a **TODOS** los actores involucrados en el sistema a desarrollar)
* **Especificacion de requerimientos**
* **Validacion de los requerimientos**

## Diseño de software e implementacion

En esta etapa se analizan cosas para llegar a producir el producto. En esta etapa no se genera el producto, pero se va yendo a cosas concretas, se van pensando mas cosas tecnicas.

![](./img/diseño.png)

## Validacion y verificacion

Se ve si el sistema cumple con los requerimientos que el cliente pidio en un principio.

**Revision**

Se revisa cualquier cosa del proyecto.

**Pruebas**

* Pruebas de componentes
* Pruebas del sistema
* Pruebas de aceptacion

## Evolucion del software

Estar atento ante cualquier cambio en el ambiente en el que el producto de desarrolla. Un producto de software no termina al finalizar su desarrollo.

## Problema de cambio

El cambio es inevitable en todos los grandes proyecos de software. Esto conduce a requisitos nuevos y modificaciones. Las especificaciones del producto va cambiando.

Para reducir los costos de estos cambios, se pueden tomar las siguientes alternativas:

* **Evitar el cambio**: Anticiparse a posibles cambios para evitar el trabajo.
* **Tolerancia al cambio**: Diseñar el software de tal manera de poder enfrentar posibles cambios con el menor costo posible

## Software prototipado

Version inicial de un sistema que se utiliza para demonstrar conceptos y probar opciones de diseño (Mockup). Esto acerca al cliente al producto a desarrollar y podemos obtener requisitos de manera mucho mas precisa.

# Desarrollo Agil de software

`Nota: Manifiesto agil, documento con el que se empezo a pensar procedimiento de desarrollo agiles`

Este tipo de desarrollo tiene ciertos principios:

* **Participacion del cliente**: el cliente debe ser parte del edsarrollo interviniendo estrechamente durante el proceso de desarrollo.
* **Entrega incremental**: Se separa el proyecto en funcionalidades y se va entregando dichas funcionalidades periodicamente, agregando en cada iteracion nuevas funcionalidades.
* **Personas no procesos**: Las personas cooperan y trabajan en conjunto para concretar un desarrollo. son un EQUIPO no un GRUPO. Cada persona tiene sus intereses y talentos, y hay que saber aprovechar estos al maximo.
* **Adoptar el cambio**: Diseñar el sistema para adoptar los cambios. Ademas, dicho cambio sera tomado en cuenta como incremento del proyecto.
* **Mantener la simplicidad**: Escribir codigo simple y refactorizado.

Siguiendo estos principios y aplicando metodologias agiles, podriamos obtener proyectos de alta calidad en tiempos mucho mas cortos y con precios mas bajos.

**Aplicabilidad del metodo agil**

* Desarrollo de productos pequeños o medianos.
* Desarrollo de sistemas a medida en donde hay u claro compromiso por parte del cliente para participar en el proceso de desarrollo.
* Enfoque en pequeños equipos (?)

**Problemas de las metodologias agiles**

* Dificil mantener el interes de los clientes
* Los miembros deben de estar comprometidos para participar de manera intensa
* Priorizar cambios puede ser dificil donde hay multiples partes interesadas.
* Mantener simplicidad requiere un trabajo extra
* Contratos pueden ser un problema

**Mantenimiento de software**

Los metodos agiles se pueden implementar en la etapa de mantenimiento. Sin embargo se presentan un problema:

Al hacer enfasis en la minimizacion de la documentacion puede resultar dificultoso el labor de mantenimiento

**Plan VS. Agil**

No son opuestos. Las empresas pueden implementar ambos en un proyecto. El uso de uno o el otro depende de muchos factores como el tamaño de los equipos, entre otras cosas.

**Extreme programming**

Ejemplo: **scrum**

![](./img/xp.png)

![](./img/p_xp.png)


**Historia de usuario**:

![](./img/hs.png)
![](./img/tareas.png)

**Proceso de scrum**

![](./img/scrum.png)

## Ingenieria de requerimientos

Proceso en el que se describen las funcionalidades y limitaciones del sistema en cuestion.

Un requerimiento es una declaracion abstractade un servicio o de una restriccion del sistema a una especifcacion funcional matematica detallada.

Los requisitos pueden ser ambiguos.
* Debe estar abierto a la interpretacion
* Debe estar definido con detalle
* Estas declaraciones pueden ser llamados requerimientos

**Tipos de requerimientos**

* **Requerimientos no funcionales**: Limitaciones de las funcionalidades que ofrece el sistema (restricciones de tiempo, proceso de desarrollo, normas, etc.)
* **Requerimientos funcionales**: define las funcionalidades que el sistema debe proveer
    * **Requerimientos del usuario**: Deben ser escritos en lenguaje natural, para que el cliente lo entienda.
    * **Requerimientos del sistema**: Documento estructurado que establece las descripciones detalladas de las funcionalidades del sisetma. Define todo lo que debe ser implementado asi que puede ser parte de un documento entre el cliente y el desarrollador.

**Ejemplo**:
![](./img/requerimientos.png)

Los requerimientos no funcionales  pueden tener distintas causas / clasificaciones

**Requerimientos del producto**
* Ejecucion / velocidad / fiabilidad, etc. Son requerimientos que especifican que el rpoducto entregado debe comportarse de una manera particular

**Requerimientos organizacionales**
*  Consecuencia de politicas y procedimientos organizacionales, ej: estandares de procesos, requisitos de implementacion (usar un SGBD en especifico), etc.

**Requerimientos externos**
* Por ejemplo, restricciones legales.

Si alguno de estos requerimientos no se cumplen, el sistema es inutil

![](./img/req_no_func.png)

Los requerimientos no funcionales pueden ser muy dificiles de explicar y requerimientos imprecisos o ambiguos pueden ser muy dificiles de verificar.

Para resolver la hipotetica ambiguedad en estos requerimientos, se suelen aplicar metricas a cada tipo de propiedad.

![](./img/metricas.png)

**Requerimientos del dominio**

Son los requerimientos del dominio sobre el cual se esta trabajando.

Estos requerimientos se expresan en el lenguaje del dominio en cuestion, por lo que puede ser dificil de entender por los programadores.

**Documento de requerimientos de software**

Declaracion oficial de lo que se requiere de los desarrolladores del sistema.

Se definen los requisitos edl usuario y del sistema.

No es un documento tecnico. dice **QUE** debe hacer, pero no **COMO**.

**Usuarios de un documento de requerimientos**

![](./img/req_usuarios.png)

![](./img/requ_doc_estructura.png)
![](./img/requ_doc_estructura_2.png)

**Especificacion de requerimientos**

Proceso de escribir los requerimientos del sistema del usuairo y en un documento de requisitos.

**Maneras de escibir una especificacion de requerimientos del sistema**:

![](./img/escribir_requerimientos.png)

El lenguaje natural es muy ambiguo y poco claro. Da pie a la confusion y fusion de requerimientos.

Para quitar esta ambiguedad, se suele pasar a un lenguaje tecnico casi pseudocodigo.

Procesos de ingenieria de requerimientos:

* Obtener requerimientos (entrevistas)
* Analisar requerimientos
* Validar requerimientos
* Gestionar requerimientos