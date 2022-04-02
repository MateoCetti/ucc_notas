# Auditoria informatica

- [Auditoria informatica](#auditoria-informatica)
- [[08-03-22]](#08-03-22)
  - [Auditoria](#auditoria)
  - [Procedimientos](#procedimientos)
  - [Consultoria](#consultoria)
  - [Control interno](#control-interno)
  - [Herramientas de la Auditoría Informática](#herramientas-de-la-auditoría-informática)
  - [Etapas de la Auditoría de una Aplicación Informática](#etapas-de-la-auditoría-de-una-aplicación-informática)
- [[15-03-22]](#15-03-22)
  - [Terminos](#terminos)
  - [Politica -> procedimiento -> auditoria](#politica---procedimiento---auditoria)
  - [Amenazas](#amenazas)
  - [Evaluación de riesgos](#evaluación-de-riesgos)
- [Proceso de auditoria](#proceso-de-auditoria)
- [[22-03-22] Auditorias de DB's](#22-03-22-auditorias-de-dbs)
  - [Objetivos de control en el ciclo de vida de una DB:](#objetivos-de-control-en-el-ciclo-de-vida-de-una-db)
    - [Estudio Previo y plan de trabajo:](#estudio-previo-y-plan-de-trabajo)
    - [Concepcion de la base de datos y seleccion de motor](#concepcion-de-la-base-de-datos-y-seleccion-de-motor)
    - [Diseño y carga](#diseño-y-carga)
    - [Uso y mantenimiento](#uso-y-mantenimiento)
    - [Revision post-implementación](#revision-post-implementación)
    - [Hay otros procesos auxiliares](#hay-otros-procesos-auxiliares)
  - [Auditoria de DB's y sus entornos](#auditoria-de-dbs-y-sus-entornos)
  - [Tecnicas para control de DB's en entornos complejos](#tecnicas-para-control-de-dbs-en-entornos-complejos)
    - [Matrices de control](#matrices-de-control)
    - [analisis de los camimos de acceso](#analisis-de-los-camimos-de-acceso)
  - [consejos para la auditoria y evaluacion de DB's](#consejos-para-la-auditoria-y-evaluacion-de-dbs)
- [[29-03-22] Auditoria de sistemas UNIX](#29-03-22-auditoria-de-sistemas-unix)
  - [Scripting](#scripting)
  - [Auditando en unix](#auditando-en-unix)
    - [Objetivos y actividades de una auditoria UNIX](#objetivos-y-actividades-de-una-auditoria-unix)

# [08-03-22]

## Auditoria

una persona da una opinion de caracter profesional de un objeto en base a determinados procedimientos para determinar su fiabilidad. se audita a _posteriori_

Clases de auditoria:
* Financiera (cuantas anuales)
* Informatica (sistemas)
* Gestion (direccion)
* Cumplimiento (normas)

## Procedimientos

Permiten justificar la opinion profesional. 

Cada clase o tipo de auditoría tiene sus **propios procedimientos** y éstos definen el **alcance** de la **auditoría**.

Buscan garantizar que:
* El trabajo se planificará y se supervisará adecuadamente
* Se estudiará y evaluará el sistema de control interno
* Se obtendrá evidencia suficiente y adecuada

Procedimientos Automatizados VS manuales:
* Automatizados
  * Bajo Costo de Puesta en Marcha
  * Bajo Costo de Operación
  * Aumento del Rendimiento Continuo
  * Excelente Consistencia
* Manuales
  * Mejor capacidad de reacción ante lo inesperado
  * Incorporación del sentido común
  * Mejor lenguaje para comunicar

La **auditoria informatica** es el proceso de recoger, agrupar y evaluar evidencias para **determinar** si un **sistema informatizado** **protege** los **activos**, mantiene la **integridad** de los **datos**, lleva a cabo eficazmente los fines de la organización y utiliza eficientemente los recursos

La auditoría informática sustenta y confirma la consecución de los objetivos tradicionales de la auditoría

El auditor evalúa y comprueba en determinados momentos del tiempo los controles y procedimientos informáticos más complejos

El auditor es responsable de revisar e informar a la Dirección de la Organización sobre el diseño y el funcionamiento de los controles implementados y sobre la fiabilidad de la información suministrada

Se pueden establecer tres grupos de **funciones** a realizar por un **auditor informático**:
* Participar en las **revisiones** durante y después del diseño, realización, implementación y uso de aplicaciones informáticas, así como en las fases análogas de realización de cambios importantes
* **Revisar** y **juzgar** los **controles** implementados en los sistemas informáticos para **verificar** su **adecuación** a las órdenes e **instrucciones** de la **Dirección**, **requisitos legales**, protección de **confidencialidad** y cobertura ante **errores** y fraudes
* Revisar y **juzgar** el nivel de **eficacia**, **utilidad**, **fiabilidad** y **seguridad** de los equipos e información

Un **auditor** informatico Interno/externo debe **revisar** los diferentes **controles internos** definidos en cada una de las funciones informáticas y el **cumplimiento** de **normativa** interna y externa, de acuerdo al nivel de riesgo, conforme a los objetivos definidos por la Dirección del Negocio y la Dirección de Informática

Tambien **Informará** a la alta **dirección** de los **hechos observados** y al detectarse deficiencias o ausencias de controles **recomendará** **acciones** que minimicen los riesgos que pueden originarse

## Consultoria

Su objetivo es dar asesoramiento o consejo de caracter especializado en base a un analisis sobre una actividad o cuestion paa establecer como se debe realizar correctamente. _priori_

## Control interno

Para llevar a cabo un control interno exitoso, una empresa debe de realizar:

* Reingenieria de procesos
* Gestion de calidad total
* Redimensionamiento de tamaño
* Tercerarizacion
* Descentralizacion

El control interno informatico es cualquier actividad o acción realizada manual y/o automáticamente para prevenir, corregir errores o irregularidades que puedan afectar al funcionamiento de un sistema para conseguir sus objetivos

El Control Interno **Informático** se ocupa de:
* Que todas las **actividades** de sistemas de información sean **realizadas** cumpliendo los **procedimientos**, **estándares** y **normas** fijados por la **Dirección** de la Organización y/o la Dirección de Informática, así como los **requerimientos legales**
* Asesorar sobre el **conocimiento** de las **normas**
* **Colaborar** con los esfuerzos de **Auditoría** Informática y otras Auditorías Externas
* **Definir**, establecer y ejecutar **mecanismos** y **controles** para **comprobar** el logro de los **grados** adecuados del **servicio** informático
* Realiza en los diferentes sistemas (centrales, departamentales, redes locales, PC’s, etc.) y entornos informáticos (producción, desarrollo o pruebas) el **control** de las diferentes **actividades** operativas sobre:
  * El **cumplimiento** de procedimiento, **normas** y controles dictados, especialmente sobre el control de **cambios** y **versiones** del software
  * Controles sobre la **producción diaria**
  * Controles sobre la **calidad** y **eficiencia** del desarrollo y **mantenimiento** del software y del servicio informático
  * Controles en las **redes** de **comunicaciones**
  * Controles sobre el **software** de base
  * Controles en los sistemas microinformáticos.
  *  La **seguridad** informática
    * Usuarios, responsables y perfiles de uso de archivos y bases de datos
    * Normas de seguridad
    * Control de información clasificada
  * **Licencias** y relaciones contractuales con terceros
  * Asesorar y transmitir cultura sobre el **riesgo informático**

![](img/ci_vs_ai.png)

Los objetivos de los controles informáticos se han clasificado en las siguientes categorías:
* Controles preventivos
* Controles detectivos
* Controles correctivos

Un sistema de control interno informaitoico debe **definir** los diferentes **controles periódicos** a realizar en cada una de las funciones informáticas, conforme a los objetivos de negocio y dentro del marco legal aplicable

Realizará periódicamente la **revisión** de los **controles establecidos** informando de las **desviaciones** a la **Dirección** de Informática y sugiriendo cuantos **cambios** serán **convenientes** en los controles, así como transmitirá constantemente a toda la organización de informática la cultura y políticas del riesgo informático.

## Herramientas de la Auditoría Informática

Algunas de las herramientas de la auditoria informatica son:

* Entrevistas
* Encuestas
* Observación del trabajo
* Pruebas de conformidad
* Pruebas de validación
* Uso de Equipos Informáticos

## Etapas de la Auditoría de una Aplicación Informática

* Obtención de Información y Documentación sobre la Aplicación
* Determinación de los Objetivos y Alcance de la Auditoría
* Planificación de la Auditoría
* Trabajo de Campo, Informe e Implementación de Mejoras

# [15-03-22]

Al auditar la seguridad en una empresa siempre **Empezar por auditar algo pequeño**

La función del auditor es actuar como una **herramienta** de la **Dirección** para **medir** y **reportar** sobre **riesgos**

## Terminos

* **Auditoría**: Medir algo contra un estándar
* **Tipos** de Auditoría
  * Auditoría de Conformidad
  * Auditoría de Seguridad
  * Auditoría Financiera
* **Evaluación**: Medición/Estimación
* **Alcance**: Que estamos auditando?
* **Objetivo**: Meta o fin de la politica/procedimiento
* **Control**: Responde la pregunta "Cómo sabemos que..."
* **Excepción de Auditoría**: Elemento que falla el cumplimiento del criterio de auditoría
* **Remediación**: ¿Qué hacemos para corregirlo?
* **Mitigación**: Qué hacemos para reducir pérdidas/daños
* **Causa Raíz**: Lo que realmente salió mal... (causa de las excepciones)
* **Lineas de base**: **Medición** de un Sistema en un **Estado Bueno** Conocido
* Seguridad Basada en Tiempo (TBS): Auditar o Evaluar a través del tiempo como una dimensión primaria. Mide qué tan bien en cuánto tiempo.

```
Nota: COBIT (Objetivos de Control para Tecnologías de la Información) es un Estándar aceptado para Seguridad de Tecnologías de la Información.
```

**Estandares de control**: FIPS, FISMA, DIACAP, GLB, HIPAA, C&A, ISO-27001, SARBOX, etc.

**Listas de control**: (?)

## Politica -> procedimiento -> auditoria

**Politica**: La Política responde quién, qué y por qué

**Procedimiento**: dice quién hace qué, cuándo y cómo

**Auditoria**: mide el rendimiento de la organización con respecto a la
Política y el Procedimiento

## Amenazas

Estas pueden ser:
* Internas
* Externas
* Intencionales
* Accidentales

## Evaluación de riesgos

La evaluación de riesgos debe:
* ser usable y repetible
* identificar riesgos inaceptables
* identificar causas subyacentes de estos riesgos
* establecer puntos de control para el riesgo evidente

`Nota: SIEMPRE debemos evitar culpar a la gente`

Tipos de evaluaciónes (Ambos identifican fallas):
* Arbol de eventos (consecuencias de una falla)
* Arbol de fallas (causas de una falla)

`Nota: los auditores deben de recomendar una manera de reparar dichas fallas`

`Nota: No hace falta hacer una evaluación de riesgos para cada excepcion. Listas de “Top 10” funcionan bastante bien.`

# Proceso de auditoria

**Objetivo Principal del Auditor**: medir y reportar sobre riesgos e influir sobre los demás en reducir riesgos mediante la concientización.

**Pasos de una auditoria**:
1. Planificación de la Auditoría:
   * Investigación
   * Definición Inicial del Alcance
   * Definición de la Estrategia de Auditoría
2. Conferencia de Entrada (No ser prepotente)
3. Trabajo de Campo
4. Preparación del Reporte
5. Conferencia de Salida (No ser prepotente)
6. Informe a la Gerencia

# [22-03-22] Auditorias de DB's

**Metodologia tradicional**: En este tipo de metodología el auditor **revisa** el entorno con la ayuda de una lista de control (**checklist**), que consta de una serie de cuestiones a verificar.

Metodologia de **evaluacion** de **riesgos**: 

Esta metodología empieza fijando los **objetivos** de **control** que **minimizan** los **riesgos** potenciales a los que está sometido el entorno.
Una vez establecidos los objetivos de control, se especifican las **técnicas** específicas correspondientes a dichos objetivos. Estas técnicas pueden ser **preventivas**, **detectivas** y **correctivas**.
En caso de que los controles existan, se diseñan **pruebas** (denominadas pruebas de cumplimiento) que permiten **verificar** la **consistencia** de los mismos.

## Objetivos de control en el ciclo de vida de una DB:

### Estudio Previo y plan de trabajo:

* Analisis de viabilidad (si conviene seguir el proyecto o no, si combiene desarrollar o comprar)
* Direccion aprueba si seguir con el proyecto.
* Objetivos de control:
  * Responsabilidades para la planificación, organización, plantillas y control de los activos de datos de la organización -> Administrador de Datos
  * Responsabilidad de la administración del entorno de la base de datos Administrador de Base de Datos
  * Posicionamiento en el organigrama lo suficientemente alto para asegurar su independencia

### Concepcion de la base de datos y seleccion de motor

* Se diseña la base de datos
* Objetivos de control:
  * Modelo de arquitectura de información y su actualización
  * Datos y diccionario de datos corporativo
  * Esquema de clasificación de datos en cuanto a seguridad
  * Niveles de seguridad para cada anterior clasificación de datos
* La selección del motor deberá realizarse utilizando un procedimiento riguroso en el que se consideren:
  * Las necesidades de la empresa.
  * Las prestaciones que ofrecen los distintos SGBD candidatos.

### Diseño y carga

* Se lleva a cabo el diseño logico y fisico de la DB
* Diseño aprobado por direccion
* Carga de los datos
* Planificar migraciones
* Controles para la entrada manual de datos (asegurar su integridad)
* Tratamiento cuidadoso de ingreso de datos erroneos

### Uso y mantenimiento
* Poner el sistema en marcha siguiendo los procedimientos establecidos
* Comprobar que los datos se cargan de forma exacta
* Auditar el rendimento de la DB (disponibilidad y performance)

### Revision post-implementación
* Se evalua si los resultados son los esperados, satisfacen al usuario y estan dentro del coste estipulado.

### Hay otros procesos auxiliares

* Instruir a los usuarios poco formados
* Controlar el acceso a la informacion
* Controlar la documentacion
* Controlar la calidad de los diseños

## Auditoria de DB's y sus entornos

Cuando el auditor encuentra el sistema en uso, deberá estudiar el **SGBD** y su **entorno**. En el desarrollo y mantenimiento de sistemas informáticos en entornos de BD, deberían considerarse el control, la integridad y la seguridad de los datos compartidos por **múltiples usuarios**. Esto debe abarcar a todos los componentes del **entorno** de BD. El gran problema de las bases de datos es que su entorno es cada vez más **complejo** y no puede limitarse sólo al propio SGBD.

Para poder auditar las DB's se suelen utilizar softwares especificos para facilitar la labor del auditor, en cuanto a la extracción de datos de la base, el seguimiento de las transacciones, datos de prueba, etc

Tambien se utilizan sistemas de Tuning que ofrecen información para optimizar el sistema, llegando a ser en determinadas ocasiones verdaderos sistemas expertos que proporcionan la estructura óptima de la base de datos y de ciertos parámetros del SGBD y del SO.

`NOTA: El SO es una pieza clave del entorno, puesto que el SGBD se apoyará en los servicios que ofrezca el SO en cuanto a control de memoria, gestión de áreas de almacenamiento intermedio (buffers), manejo de errores, control de confidencialidad, mecanismos de interbloqueo, etc.`

* Cada vez más se está accediendo a las bases de datos a través de redes (sistemas distribuidos), con lo que el riesgo de violación de la confidencialidad e integridad se acentúa. También las bases de datos
distribuidas pueden presentar graves riesgos de seguridad, por lo que para estos casos se establecen mas objetivos de control a la hora de realizar auditorias.

(?) Existen en el mercado varios productos que permiten la implementación efectiva de una política de seguridad, puesto que centralizan el control de accesos, la definición de privilegios, perfiles de usuario, etc.

## Tecnicas para control de DB's en entornos complejos
Existen muchos elementos del entorno del SGBD que influyen en la
confidencialidad e integridad de los datos, algunos de ellos
interdependientes.

Se deben fijar claramente las responsabilidades sobre los diferentes
componentes de Seguridad, utilizar informes de excepción efectivos que
permitan monitorear los controles, establecer procedimientos adecuados,
implementar una gestión rigurosa de la configuración del sistema, etc.

Algunas tecnicas de control para DB's en entornos complejos son las siguientes:

### Matrices de control

Identifican datos con los controles implementados sobre los mismos

Controles detectivos, preventivos y correctivos

### analisis de los camimos de acceso

se documentan el flujo, almacenamiento y procesamiento de los datos, identificando los componentes del sistema que atraviesan y los controles asociados.

## consejos para la auditoria y evaluacion de DB's

* No alejarse del objetivo
* Planificar en consecuencia
* Suyomsyixst lo wur dr purfs
* Ir mas alla de la auditoria tradicional
* Informar metricas significativas

# [29-03-22] Auditoria de sistemas UNIX

Buenos **Controles** de Configuración significan
* Sistemas Seguros
* Facilidad para Auditar

Los sistemas basados en UNIX son "**copos de nieve**", es decir son unicos ya que generalmente son utilizados para implementar **servidores** y su **gestion** y **administración** suele estar **poco descentralizada** (su configuración es llevada a cabo por el administrador quien lo configura a su gusto).

## Scripting

El scripting de tipo "**Batch**" se puede realizar con lenguajes como bash y python y nos ayudan a **simplificar** las **tareas** de auditoria / **automatizar** los procesos.

`NOTA: Investigar test en bash scripting`

`NOTA: Investigar implementación de regexp en bash scripting`

## Auditando en unix

Cuando evaluamos un sistema unix estamos evaluando practicamente un sistema **desconocido** ya que su configuración depende del **administrador** que implemento dicho sistema. Las **herramientas** que proveen los sistemas y repositorios (y que procederiamos a usar en un proceso de auditoria) pueden llegar a haber sido **modificadas** de manera intencional o no por dicho administrador. A esto se lo suele llamar **Rootkit**.

Por este motivo ¿Como verificamos qe las herramientas de un sistema a auditar no estan alteradas? es decir ¿Como **examinamos** un sistema **no confiable**?

Una de las soluciones implementadas en las auditorias es crear un **USB** con herramientas y scripts **confiables** y utilizar dichas herramientas en los procesos de auditoria (ya sea en sistemas UNIX como en WINDOWS)

### Objetivos y actividades de una auditoria UNIX

1. Información del sistema
   * Identificar el tipo de sistema
   * Identificar nivel de actualización
   * Otra informacion general de importancia especifica
2. Perfil operativo
   * Identificar servicios de red
   * Identificar servicios locales
   * Identificar comportamiento de red
3. Acceso no autorizado
   * Examinar control de accesos a nivel de red para equipos
4. Administración / acceso de usuarios
   * Asegurar cuentas de usuario unicas
   * Identificar usuarios autorizados
   * Examinar configuraciones de contraseñas
5. Acceso no autorizado
   * Asegurar que los archivos tienen el acceso justo y necesario
   * Identificar archivos modificados recientemente
6. 