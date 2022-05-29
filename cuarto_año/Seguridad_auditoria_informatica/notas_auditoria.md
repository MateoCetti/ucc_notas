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
- [[05-04-22] Auditoria de seguridad y redes](#05-04-22-auditoria-de-seguridad-y-redes)
  - [Auditoria de seguridad](#auditoria-de-seguridad)
    - [Evaluación de riesgos](#evaluación-de-riesgos-1)
    - [Fases de la auditoria de seguridad](#fases-de-la-auditoria-de-seguridad)
    - [Auditoria de seguridad fisica](#auditoria-de-seguridad-fisica)
    - [Auditoria de seguridad logica](#auditoria-de-seguridad-logica)
    - [Tecnicas, metodos y herramientas](#tecnicas-metodos-y-herramientas)
    - [Informe final](#informe-final)
    - [Contratación de auditoria externa](#contratación-de-auditoria-externa)
  - [Auditoria de redes](#auditoria-de-redes)
    - [Vulnerabilidad en redes](#vulnerabilidad-en-redes)
    - [Auditando la red fisica](#auditando-la-red-fisica)
    - [Auditando la red logica](#auditando-la-red-logica)
- [[12-04-22] Informe de auditoria y auditoria de Windows](#12-04-22-informe-de-auditoria-y-auditoria-de-windows)
  - [Informe de auditoria](#informe-de-auditoria)
    - [La evidencia](#la-evidencia)
    - [Irregularidades](#irregularidades)
    - [La documentación](#la-documentación)
    - [El informe de auditoria informatica](#el-informe-de-auditoria-informatica)
  - [Organización del departamento de auditoria informatica](#organización-del-departamento-de-auditoria-informatica)
    - [Perfiles profesionales de la función de Auditoría Informática](#perfiles-profesionales-de-la-función-de-auditoría-informática)
    - [Funciones a Desarrollar por Auditoría Informática](#funciones-a-desarrollar-por-auditoría-informática)
    - [Organización de la Función de Auditoría Informática](#organización-de-la-función-de-auditoría-informática)
  - [Deontología del Auditor](#deontología-del-auditor)
- [[26-04-22] Auditoría de la Dirección de Informática y Área de Desarrollo](#26-04-22-auditoría-de-la-dirección-de-informática-y-área-de-desarrollo)
  - [Auditoría de la Dirección de Informática](#auditoría-de-la-dirección-de-informática)
    - [Proceso de Dirección Informática](#proceso-de-dirección-informática)
      - [Planificar](#planificar)
      - [Organizar y Dirigir](#organizar-y-dirigir)
      - [Controlar](#controlar)
  - [Auditoría del Área de Desarrollo](#auditoría-del-área-de-desarrollo)
    - [Funciones del Área de Desarrollo](#funciones-del-área-de-desarrollo)
    - [Auditoría de la Organización y Gestión del Área de Desarrollo](#auditoría-de-la-organización-y-gestión-del-área-de-desarrollo)
    - [Auditoría de Proyectos de Desarrollo de S.I.](#auditoría-de-proyectos-de-desarrollo-de-si)
      - [Aprobación, Planificación y Gestión del Proyecto](#aprobación-planificación-y-gestión-del-proyecto)
      - [Auditoría de la Fase de Análisis](#auditoría-de-la-fase-de-análisis)
      - [Auditoría de la Fase de Diseño](#auditoría-de-la-fase-de-diseño)
      - [Auditoría de la Fase de Construcción](#auditoría-de-la-fase-de-construcción)
      - [Auditoría de la Fase de Implementación](#auditoría-de-la-fase-de-implementación)
- [[03-05-22] Auditando Windows](#03-05-22-auditando-windows)
  - [Auditoria de Windows - Objetivos](#auditoria-de-windows---objetivos)
- [[10-05-22] Auditoria de aplicaciones web](#10-05-22-auditoria-de-aplicaciones-web)
  - [Buenas practicas](#buenas-practicas)
    - [1 Validación y desinfección de entrada](#1-validación-y-desinfección-de-entrada)
    - [2 Control de Errores](#2-control-de-errores)
    - [3 Administración Robusta de Sesiones](#3-administración-robusta-de-sesiones)
    - [4 Mediación Completa](#4-mediación-completa)
    - [5 Solución de Múltiples Capas](#5-solución-de-múltiples-capas)
  - [Conceptos basicos de aplicaciones web](#conceptos-basicos-de-aplicaciones-web)
  - [Seguridad de servidores](#seguridad-de-servidores)
  - [Pruebas de configuración](#pruebas-de-configuración)
  - [Metodos de autenticación](#metodos-de-autenticación)

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


# [05-04-22] Auditoria de seguridad y redes

## Auditoria de seguridad

Debe evaluarse en la auditoría si los **modelos** de **seguridad** están en **consonancia** con las nuevas **arquitecturas**, las distintas **plataformas** y las **posibilidades** de las **comunicaciones**.

Los grandes grupos de **controles**, que además de poderlos dividir en manuales y automáticos, o en generales y de aplicación, son los siguientes:
* Controles **directivos**
* Controles **preventivos**
* Controles **detectivos**
* Controles **correctivos**
* Controles de **recuperación**

El sistema de **control interno** debe basarse en **políticas**, y se implementa con apoyo de **herramientas**. Cuando existe un sistema de control interno **adecuado**, los procesos de auditoría, especialmente si son periódicos, son revisiones **necesarias** pero más **rápidas**, con informes más breves.

### Evaluación de riesgos

Se trata de **identificar** y **cuantificar** la **probabilidad** e **impacto** de los **riesgos** y analizar **medidas** que **disminuyan** la **probabilidad** de que **ocurran** los hechos o **mitiguen** el **impacto**.

Para **evaluarlos** hay que considerar:
* El **tipo** de **información** almacenada, procesada y transmitida.
* La **criticidad** de las **aplicaciones**.
* La **tecnología usada**, el **marco legal** aplicable, el **sector** de la **entidad**, la entidad misma y el momento.

Es necesario **revisar** si se han **considerado** las **amenazas** y, además, **errores** y **negligencias** en general que pueden traducirse en daños, en algunos casos irreversibles.

Es necesario evaluar las **vulnerabilidades** que existen

El **factor humano** es el principal a considerar.

En la auditoría externa se trata de saber si la entidad ha **evaluado** de forma adecuada los **riesgos**, si los **informes** han **llegado** a los **destinatarios** correspondientes y si se están **tomando** las **medidas pertinentes**, así como si el proceso se realiza con la **frecuencia necesaria** y no ha constituido un hecho aislado.

Al hablar de seguridad siempre se habla de sus tres **dimensiones** clásicas y los controles buscan **garantizar** alguna de estas **características**:
* **Confidencialidad**
* **Integridad**
* **Disponibilidad**
* **Autenticidad**

### Fases de la auditoria de seguridad

1. **Definición** de los **objetivos**, **alcance** y **profundidad** de la auditoría.
2. **Análisis** de posibles **fuentes** y **recopilación** de **información**.
3. **Determinación** del **plan** de **trabajo** y comunicación a la entidad.
4. Adaptación de **cuestionarios** y consideración de **herramientas** o perfiles de especialistas necesarios, sobre todo en la auditoría externa.
5. **Realización** de **entrevistas** y **pruebas**.
6. **Análisis** de **resultados** y valoración de riesgos.
7. **Presentación** y **discusión** del **informe provisional**.
8. **Informe definitivo**.

### Auditoria de seguridad fisica

Se evaluarán las **protecciones físicas** de datos, programas, instalaciones, equipos, redes y soportes, y personas.

Las **amenazas** pueden ser muy **diversas**: sabotaje, vandalismo, terrorismo, accidentes de distinto tipo, incendios, inundaciones, averías importantes, derrumbamientos, explosiones, etc.

Desde la perspectiva de las protecciones físicas algunos aspectos a considerar son:
* **Ubicación** del centro de datos, servidores locales y cualquier **elemento a proteger**.
* **Protección** de **computadoras portátiles**, incluso fuera de las oficinas: aeropuertos, automóviles, restaurantes, etc.
* Estructura, diseño, construcción y **distribución** de los **edificios** y de sus **plantas**.
* **Riesgos** a los que están **expuestos** por **agentes externos** como por accesos físicos no controlados. * Amenazas de **fuego**; riesgos por **agua**; por **accidentes atmosféricos** o por **averías** en las **conducciones**; problemas en el suministro eléctrico, tanto por caídas como por perturbaciones.
* **Controles** tanto **preventivos** como de **detección** relacionados con los puntos anteriores.
* Además debe **controlarse** el **contenido** de carteras, **paquetes**, bolsos o cajas, ya que podrían contener explosivos, así como lo que se quiere sacar del edificio, para evitar sustituciones o sustracción de equipos, componentes, soportes magnéticos, documentación u otros activos.
* **Protección** de **soportes magnéticos** (acceso, almacenamiento y posible transporte).
* **Protección** de **documentos** impresos y de cualquier tipo de documentación clasificada.
* Todos los puntos anteriores pueden estar además cubiertos por seguros.

### Auditoria de seguridad logica

Es necesario verificar que **cada usuario** sólo pueda **acceder** a los **recursos** a los que le **autorice** el propietario según su función, y con las posibilidades que el propietario haya fijado: lectura, modificación, borrado, ejecución, etc. lo que representaríamos en una **matriz de accesos** en la que figurarían los **sujetos**, los **objetos** que puedan ser **accedidos** con mayor o menor granularidad y las **posibilidades** que se le otorgan. 

Desde el punto de vista de la auditoría es necesario revisar **cómo se identifican** y sobre todo **autentican** los **usuarios**, **cómo** han sido **autorizados** y **por quién**, y qué ocurre cuando se producen transgresiones o **intentos**: **quién se entera**, **cuándo** y **qué se hace**.

En cuanto a autenticación el método más usado es la **contraseña**, cuyas
características serán **acordes** con las **normas** y **estándares** de la **entidad**.

Algunos de los aspectos a evaluar respecto a las contraseñas pueden ser:
* **Quién asigna** la contraseña.
* **Longitud mínima** y composición de caracteres.
* **Vigencia**.
* Control para **no asignar** las “x” **últimas** (Historial).
* **Número** de **intentos fallidos** que se permiten al usuario.
* Si las contraseñas están **cifradas**, y bajo qué sistema.
* Protección o cambio de contraseñas iniciales que llegan en los sistemas, y que a menudo aparecen en los propios manuales.
* **Controles existentes** para evitar y detectar Troyanos.
* La no-cesión, y el uso individual y responsable de cada usuario, a partir de la normativa.
* Promover el uso de **diferentes contraseñas** para diferentes sistemas.
* La solución más adecuada por ahora puede consistir en utilizar sistemas de identificación únicos (single sign-on).
* Verificar que el **proceso** de **altas**, **variaciones** y **bajas** de usuarios se realiza **según** la **normativa** en vigor. 
* Debería estar previsto **bloquear** a un **usuario** que **no accediera** por un **período determinado**.
* Examinar situaciones de bloqueo por la existencia de un sólo administrador.

### Tecnicas, metodos y herramientas

Como métodos y técnicas podemos considerar los **cuestionarios**, las **entrevistas**, la **observación**, los **muestreos**, las **CAAT** (Técnicas de Auditoría Asistidas por Computadora), las utilidades y **programas**, los paquetes específicos, las **pruebas** y la simulación en paralelo con datos reales.

### Informe final

Se harán **constar** los **antecedentes** y los **objetivos**, qué **metodología** de evaluación de riesgos y **estándares** se ha utilizado, y una breve descripción de los **entornos revisados**.

Debe incluirse un **resumen** para la **Dirección** en términos no técnicos.

En cada punto que se incluya debe **explicarse por qué** es un **incumplimiento** o una **debilidad**, así como alguna **recomendación**.

El informe debe ser necesariamente **revisado** por los **auditados**, así como **discutido** si es necesario antes de emitir el definitivo.

En muchos casos se **recogen** las **respuestas** de los auditados, sobre todo cuando la auditoría es interna.

La entidad decide qué acciones tomar a partir del informe, y en el caso de los auditores internos éstos suelen hacer también un **seguimiento** de las **implementaciones**.

Es necesario diferenciar puntos muy graves, graves, de mediana criticidad, u otra clasificación, en definitiva **establecer** algunas **métricas de seguridad** y **clasificar** los puntos **según** su **importancia** y **prioridad**.

Es **importante** que se **delimiten** las **responsabilidades** y los **entregables** que son **objeto** de **auditoría externa** en el **contrato** o propuesta.

### Contratación de auditoria externa

Algunas consideraciones pueden ser:
* La **entidad auditora** debe ser **independiente** de la **auditada** en el caso de una auditoría externa.
* Las **personas** que vayan a realizar el trabajo deben ser **independientes** y **competentes**, según el objetivo.
* La auditoría debe encargarse a un nivel suficiente alto, normalmente **Dirección General** o Consejero Delegado.
* Puede ser necesario dar o **mostrar** a los **auditores** todo lo que **necesiten** para **realizar** su **trabajo**, pero **nada más**, e incluso lo que se les muestre o a lo que se les permita acceder puede ser con restricciones.

## Auditoria de redes

### Vulnerabilidad en redes

En las redes de comunicaciones, por **causas propias** de la **tecnología**, pueden producirse básicamente **tres tipos** de **incidencias**:

* **Alteración de bits**. Una trama puede sufrir variación en parte de su contenido. Se agrega un sufijo a la trama con un Código de Redundancia Cíclico (CRC) que detecte cualquier error y permita corregir errores que afecten hasta unos pocos bits.
* **Ausencia de tramas**. Alguna trama puede desaparecer en el camino del emisor al receptor. Se suele atajar este riesgo dando un número de secuencia a las tramas.
* **Alteración de secuencia**. El orden en el que se envían y se reciben las tramas o coincide. Unas tramas han adelantado a otras. En el receptor, mediante el número de secuencia, se reconstruye el orden original.

Teniendo en cuenta que es físicamente posible **interceptar** la **información**, los tres mayores **riesgos** a atacar son:
● **Indagación**: Un mensaje puede ser leído por un tercero, obteniendo la información que contenga.
● **Suplantación**: Un tercero puede introducir un mensaje adulterado que el receptor cree proveniente del emisor legítimo.
● **Modificación**: Un tercero puede alterar el contenido de un mensaje. 

Para este tipo de actuaciones, la única medida prácticamente efectiva en redes MAN y WAN (cuando la información sale del edificio) es la **criptografía**.

El cableado que va desde el **armario distribuidor** a cada uno de los potenciales puestos, suele llamarse de **“planta**” suele ser de **cobre** y es propenso a escuchas (**“pinchazos**”) que pueden no dejar rastro.

El **cableado troncal** (conexión entre armarios y salas de equipos) y el **de ruta** (conexión desde sala de equipos hacia los transportistas de datos) se tienden frecuentemente mediante **fibra óptica**, que son muy **difíciles de interceptar**, debido a que no provocan radiación electromagnética y a que la conexión física a una fibra óptica requiere una tecnología delicada y compleja.

En el propio **puesto de trabajo** puede haber **peligros**, como grabar/retransmitir la imagen que se ve en la pantalla, teclados que memorizan el orden en que se han pulsado las teclas, o directamente que las contraseñas estén escritas en papeles a la vista.

Dentro de las **redes locales**, el mayor peligro es que alguien instale una “**escucha**” no autorizada. Al viajar en **texto plano** la información dentro de la **red local**, es imprescindible tener una organización que **controle** estrictamente los equipos de escucha, bien sean estos físicos (“**sniffers**”) o lógicos (**“traceadores”**). 

### Auditando la red fisica

Deben comprobarse que efectivamente los **accesos físicos** provenientes del **exterior** han sido debidamente **registrados** y que desde el **interior** del edificio **no se intercepta** **físicamente** el **cableado** (“pinchazo”).

En caso de desastre, debe comprobarse cuál es la parte del cableado que queda en condiciones de funcionar y qué operatividad puede soportar.

Como objetivos de control, se debe marcar la existencia de:
* **Áreas controladas** para los equipos de comunicaciones.
* **Protección** y **tendido adecuado** de cables y líneas de comunicaciones.
* **Controles** de **utilización** de los **equipos** de pruebas de comunicaciones, usados para monitorear la red y su tráfico.
* **Atención** específica a la **recuperación** de los **sistemas** de **comunicación** de datos en el plan de recuperación de desastres en sistemas de información.
* Controles específicos en caso de que se utilicen líneas telefónicas normales con acceso a la red de datos para prevenir accesos no autorizados al sistema o a la red.

### Auditando la red logica

Se debe controlar que un equipo **no pueda** **enviar indiscriminadamente** **mensajes** ya que puede **bloquear** la **red** completa.

Es necesario **monitorear la red**, **revisar** los **errores** o **situaciones anómalas** que se producen y tener establecidos los **procedimientos** para **detectar** y **aislar equipos** en situación **anómala**. 

Una solución totalmente efectiva es el **cifrado** de las comunicaciones.

Como **objetivos de control**, se debe marcar la existencia de:

* **Contraseñas** y otros procedimientos para limitar y detectar cualquier intento de acceso no autorizado a la red de comunicaciones.
* Facilidades para detectar errores de transmisión y establecer las retransmisiones apropiadas.
* **Controles** para asegurar que las **transmisiones** van solamente a **usuarios autorizados**.
* **Registro** de la **actividad** de la **red**.
* **Técnicas** de **cifrado** de datos donde haya riesgos de accesos impropios a transmisiones sensibles.
* Controles adecuados que cubran la importación o exportación de datos a otros sistemas informáticos.

# [12-04-22] Informe de auditoria y auditoria de Windows

## Informe de auditoria

### La evidencia

La evidencia es la **base razonable** de la **opinión** del auditor y tiene una serie de calificativos:

* La evidencia **relevante**, que tiene una relación lógica con los objetivos de la auditoría.
* La evidencia **fiable**, que es válida y objetiva.
* La evidencia **suficiente**, que es de tipo cuantitativo para soportar la opinión profesional del auditor.
* La evidencia **adecuada**, que es de tipo cualitativo para afectar a las conclusiones del auditor.

### Irregularidades

En los organismos y las empresas, la **Dirección** tiene la **responsabilidad principal** y **primaria** de la **detección** de **irregularidades**, **fraudes** y **errores**.

Es necesario diseñar **pruebas antifraude**, que lógicamente incrementarán el costo de la auditoría, previo análisis de riesgos (amenazas, importancia relativa, etc.).

En el caso de **detectar fraude** durante el proceso de auditoría procede actuar en consecuencia, con la debida prudencia, sobre todo si afecta a los administradores
de la organización objeto de auditoría.

### La documentación

**Papeles de trabajo**: los **documentos** preparados o **recibidos** por el **auditor** que **reúnen** la **información utilizada** y **resultados** de las **pruebas** efectuadas en la ejecución de su trabajo, junto con las **decisiones tomadas** para llegar a su **opinión**. El **Informe de Auditoría** tiene que estar **basado** en la documentación o **papeles de trabajo**.


**Característica registral del Informe**: tanto en su parte cronológica como en la organizativa, con procedimientos de archivo, búsqueda, custodia y conservación de su documentación, cumpliendo toda la normativa vigente, legal y profesional. 

Además, se **incluirán**: el **contrato** cliente/auditor informático, **declaraciones** de la **Dirección**, **contratos** que afecten al **sistema** de información, **informes** de **asesorías** jurídicas del cliente, **informes** sobre **terceros** vinculados y **conocimiento** de la **actividad** del cliente.

### El informe de auditoria informatica

Es la **comunicación** del **Auditor** Informático al **cliente** tanto del **alcance** de la **auditoría** (objetivos, período de cobertura, naturaleza y extensión del trabajo realizado) como de los **resultados** y las **conclusiones**.

No existe un **formato predeterminado**, pero sí algunas **recomendaciones** sobre estructura y contenido.

El Informe deberá ser **claro**, **adecuado**, **suficiente** y **comprensible**, con la utilización conveniente del lenguaje informático. 

Los puntos esenciales, genéricos y mínimos del Informe de Auditoría Informática son:
* Identificación del **Informe**
* Identificación del **Cliente**
* Identificación de la **Entidad Auditada**
* **Objetivos** de la Auditoría Informática
* **Normativa aplicada** y excepciones
* **Alcance** de la Auditoría
* **Conclusiones**: 
  * Opinión **favorable** 
  * Opinión **con salvedades** (limitaciones del alcance o restricciones / incertidumbres)
  * Opinión **desfavorable** (Irregularidades / incumplimiento de norma legal)
  * Opinión **denegada** (Limitaciones del alcance / irregularidades / incertidumbres / incumplimiento de normativa legal)
* **Resultados**
* **Informes previos**
* **Fecha** del Informe
* Identificación y **firma** del Auditor
* **Distribución** del Informe

## Organización del departamento de auditoria informatica

### Perfiles profesionales de la función de Auditoría Informática

El auditor informático debe ser una persona con **alto grado** de **calificación técnica** y al mismo tiempo estar **integrado** en las **corrientes organizativas empresariales**. Dentro de la función de auditoría informática, se deben contemplar las siguientes **características** para mantener un perfil profesional adecuado y actualizado:

* Las personas que integren esta función deben contemplar en su formación básica una mezcla de **conocimientos** de **auditoría** y de **informática** general: **Desarrollo informático**, **Gestión** del **Departamento** de **Sistemas**, **Análisis** de **Riesgos** en un **Entorno Informático**, **Sistemas Operativos**, **Telecomunicaciones**, Gestión de **Bases de Datos**, **Redes Locales**, **Seguridad Física**, etc.
* A estos conocimientos básicos se deben añadir **especializaciones** en función de la **importancia** de los **distintos componentes** en el **entorno empresarial**.
* En la realidad actual, los sistemas de información requieren cada vez mayor control, se hace necesario para el auditor informático conocer **técnicas de gestión empresarial**, y sobre todo **gestión del cambio**. 
* El auditor informático debe tener siempre el concepto de **Calidad Total**.

### Funciones a Desarrollar por Auditoría Informática

El auditor informático debe **revisar** la **seguridad**, el **control interno**, la **efectividad**, la **gestión** del **cambio** y la **integridad** de la **información**.

La **función** de Auditoría Informática debe realizar, entre otras actividades:

* **Verificación** del **control interno**, tanto de las aplicaciones como de los sistemas informáticos, centrales y periféricos.
* **Análisis** de la **gestión** de los **sistemas** de información desde un punto de vista de **riesgo** de **seguridad**, de **gestión** y de **efectividad**.
* **Análisis** de la **integridad**, **fiabilidad** y **certeza** de la **información** a través del análisis de las aplicaciones.
* **Auditoría** del **riesgo operativo** de los **circuitos** de **información**.
* **Análisis** de la **gestión** de los **riesgos** de la información y de la seguridad implícita.
* **Verificación** del nivel de **continuidad** de las **operaciones**.
* Análisis del Estado del **Arte tecnológico** de la instalación revisada y de las consecuencias empresariales que un desfase tecnológico pueda acarrear.
* Diagnóstico sobre el **grado** de **cobertura** que dan las aplicaciones a las necesidades estratégicas y operativas de información de la organización.

### Organización de la Función de Auditoría Informática

La organización típica de auditoría informática, debe contemplar los siguientes principios:
* Su localización puede estar ligada a la localización de la auditoría interna operativa, pero con independencia de objetivos, de planes de formación y de presupuestos.
* La organización operativa típica debe ser la de un grupo independiente del de auditoría interna, con **accesibilidad total** a los **sistemas informáticos** y de información, e idealmente dependiendo de la misma persona en la empresa que el de auditoría interna, que debería ser el director general o consejero delegado.
* Los recursos humanos con los que debe contar el departamento deben contener una mezcla entre personas con formación en auditoría y organización, y personas con perfil informático.
* Este personal debe contemplar entre su titulación la de CISA (Certified Information Systems Auditor) como un elemento básico para comenzar su carrera como auditor informático.
* La organización interna de la función podría ser: Jefe del Departamento, Gerente o Supervisor de Auditoría Informática y Auditor Informático.
* El tamaño del área sólo se puede precisar en función de los objetivos de la organización, pero se debería cubrir con Especialistas en el entorno informático a auditar, gestión de bases de datos, comunicaciones y/o redes, riesgos y aplicaciones, y auditoría de sistemas de información.

## Deontología del Auditor

* Principio de Beneficio del Auditado
  * El auditor deberá conseguir la máxima eficacia y rentabilidad de los medios informáticos de la empresa auditada.
  * El auditor deberá conseguir la máxima eficacia y rentabilidad de los medios informáticos de la empresa auditada.
* Principio de Calidad:
  * El auditor deberá prestar sus servicios conforme a las posibilidades de la ciencia y medios a su alcance en condiciones técnicas adecuadas para el idóneo cumplimiento de su labor.
* Principio de Capacidad
  * El auditor debe estar plenamente capacitado para la realización de la auditoría encomendada, teniendo en cuenta que, dada su especialización, a los auditados en algunos casos les puede ser extremadamente difícil verificar sus recomendaciones y evaluar correctamente la precisión de las mismas.
* Principio de Cautela
  * El auditor debe en todo momento ser consciente de que sus recomendaciones deben estar basadas en la experiencia que tiene adquirida, evitando que el auditado se embarque en proyectos de futuro fundamentados en simples intuiciones sobre la posible evolución de las nuevas tecnologías de la información.
* Principio de Comportamiento Profesional
  * El auditor deberá actuar conforme a las normas, implícitas o explícitas, de dignidad de la profesión y de corrección en el trato personal.
* Principio de Concentración en el Trabajo
  * El auditor deberá evitar que un exceso de trabajo supere sus posibilidades de concentración y precisión en cada una de las tareas encomendadas, ya que la saturación y dispersión de trabajos suele a menudo provocar la conclusión de los mismos sin las debidas medidas de seguridad.
* Principio de Confianza
  * El auditor deberá facilitar e incrementar la confianza del auditado en base a una actuación de transparencia en su actividad profesional sin alardes científico-técnicos que puedan restar credibilidad a los resultados obtenidos y a las directrices aconsejadas de actuación.
* Principio de Criterio Propio
  * El auditor durante la ejecución de la auditoría deberá actuar con criterio propio y no permitir que este esté subordinado al de otros profesionales, aún de reconocido prestigio, que no coincidan con el mismo.
* Principio de Discreción
  * El auditor deberá en todo momento mantener cierta discreción en la divulgación de datos, aparentemente inofensivos, que se le hayan puesto de manifiesto durante la ejecución de la auditoría.
* Principio de Formación Continua
  * Este principio impone a los auditores el deber y la responsabilidad de mantener una permanente actualización de sus conocimientos y métodos a fin de adecuarlos a las necesidades de la demanda y a las exigencias de la competencia de la oferta.
* Principio de Fortalecimiento y Respeto a la Profesión
  * La defensa de los auditados pasa por el fortalecimiento de la profesión de los auditores informáticos, lo que exige un respeto por el ejercicio de la actividad desarrollada por los mismos y un comportamiento acorde con los requisitos exigibles para el idóneo cumplimiento de la finalidad de las auditorías.
* Principio de No Injerencia
  * El auditor deberá evitar injerencias en los trabajos de otros profesionales, respetar su labor y eludir hacer comentarios que pudieran interpretarse como despreciativos de la misma o provocar un cierto desprestigio de su calificación profesional, a no ser que, por necesidades de la auditoría, tuviera que explicitar determinadas inidoneidades que pudieran afectar a las conclusiones o el resultado de su dictamen. 
* Principio de Responsabilidad
  * El auditor deberá responsabilizarse de lo que haga, diga o aconseje, sirviendo esta forma de actuar como limitación de injerencias extraprofesionales.
* Principio de Secreto Profesional
  * El auditor tiene la obligación de guardar en secreto los hechos e informaciones que conozca en el ejercicio de su actividad profesional. Solamente por imperativo legal podrá decaer esta obligación.

# [26-04-22] Auditoría de la Dirección de Informática y Área de Desarrollo

## Auditoría de la Dirección de Informática

### Proceso de Dirección Informática

Es necesaria la **evaluación** independiente de la **función** que **gestiona** las **tecnologías** de la **información**. Las actividades básicas del **proceso** de **dirección** son:
* **Planificar**
* **Organizar**
* **Dirigir**
* **Controlar**

#### Planificar

Tiene como objetivo **prever** la **utilización** de **tecnologías** de **información**.

El plan principal se denomina **Plan Estratégico** de **Sistemas** de **Información**.

* Debe estar **alineado** con los **objetivos** de la **empresa**.
* No es responsabilidad exclusiva de la Dirección de Informática, aunque ésta debe impulsar una planificación adecuada y a tiempo.
* El entorno de la empresa define el plazo del plan. Por lo general, es de 3 a 5 años.

#### Organizar y Dirigir

Se organiza para **estructurar** los **recursos**, **flujos** de **información** y **controles** para **alcanzar** los **objetivos** propuestos en la planificación.

Se establece el **Comité de Informática**, impulsado por la Dirección de Informática, como **lugar** de **encuentro** entre los **informáticos** y los **usuarios**.
* Presidido por el **director** con **mayor experiencia** dentro de la empresa
* Las grandes áreas usuarias deberían estar **representadas** al nivel de sus **directores**
* El **director** de **Auditoría Interna** debería ser **miembro** del Comité

**Funciones** del **comite**:
* **Aprobación** del **Plan Estratégico** de **Sistemas** de **Información**
* **Aprobación** de las grandes **inversiones** en **tecnología** de la información
* Fijación de **prioridades** entre los grandes **proyectos** informáticos
* Vehículo de **discusión** entre el área **informática** y sus **usuarios**
* Vigila y realiza el **seguimiento** de la **actividad** del **Departamento** de **Informática**

**Departamento de Informática**

su posición dentro de la empresa debe ser lo suficientemente **alto** en la jerarquía y contar con masa crítica suficiente.

Suele **depender** de la **Dirección General**. En grandes organizaciones, el Director de Informática es miembro del Comité de Dirección.

Las funciones de este departamento son

* **Segregación de Funciones**: funciones descritas y sus responsabilidades claramente delimitadas y documentadas. Evita que un individuo pueda trastornar un proceso crítico.
* **Aseguramiento de la Calidad**: función organizativa de Aseguramiento de la Calidad independiente. Responde directamente a la Dirección de Informática.


Deben existir **estándares** de **funcionamiento** y **procedimientos** que gobiernen la **actividad** del **Departamento** de **Informática** y sus relaciones con los departamentos usuarios.
Deben estar **documentados**, **actualizados** y ser **comunicados adecuadamente** a todos los departamentos afectados.

Deben existir **descripciones documentadas** de los **puestos de trabajo** dentro de Informática.

En cuanto a la organización y gestion economica, se deben tener en cuenta los siguientes 3 puntos:

* **Presupuestación**: El Departamento de Informática debe tener un **presupuesto económico**, normalmente en base anual.
* **Adquisición** de **bienes** y **servicios**: Los procedimientos que el Departamento de Informática siga para adquirir los bienes y servicios deben estar **documentados** y **alineados** con los **procedimientos** de **compras** del resto de la **empresa**.
* **Medida** y **reparto** de **costos**: La Dirección de Informática debe en todo momento **gestionar** los **costos** asociados con la **utilización** de los **recursos** informáticos: **humanos** y **tecnológicos**.

#### Controlar

**Control** y **Seguimiento**: La Dirección tiene la obligación de **controlar** y efectuar un **seguimiento** permanente de las distintas **actividades** del **Departamento**.
**Cumplimiento** de la **normativa legal**: La Dirección de Informática debe **controlar** que la realización de sus actividades se lleva a cabo **dentro** del **respeto** a la **normativa legal aplicable**. 

## Auditoría del Área de Desarrollo

### Funciones del Área de Desarrollo

* **Planificación** del **área** y **participación** en la **elaboración** del **plan estratégico** de **informática**.
* **Desarrollo** de **nuevos sistemas**.
* **Estudio** de **nuevos lenguajes**, **técnicas**, **metodologías**, **estándares**, herramientas, etc. **relacionados** con el **desarrollo** y adopción de los mismos.
* **Establecimiento** de un **plan** de **formación** para el **personal** asignado al área.
* **Establecimiento** de **normas** y **controles** para todas las **actividades** que se realizan en el **área** y **comprobación** de su **cumplimiento**.

Se abordará la **auditoría** del área en **dos** grandes **apartados**:

* **Auditoría** de la **organización** y gestión del área de desarrollo.
* **Auditoría** de **proyectos** de desarrollo de sistemas de información.

Se aplicará la **metodología** propuesta por **ISACA** basada en la **evaluación** de **riesgos**.

### Auditoría de la Organización y Gestión del Área de Desarrollo

Objetivos de Control:

1. El **área** de **desarrollo** debe tener **funciones asignadas** dentro del departamento y una **organización** que le **permita** el **cumplimiento** de las **mismas**.
2. El **personal** del área de desarrollo debe contar con la **formación adecuada** y estar **motivado** para la **realización** de su **trabajo**.
3. Si existe un **plan** de **sistemas**, los **proyectos** que se lleven a cabo se **basarán** en **dicho plan** y lo mantendrán actualizado.
4. La **propuesta** y **aprobación** de **nuevos proyectos** debe realizarse siguiendo **reglas** preestablecidas
5. La **asignación** de **recursos** a los **proyectos** debe basarse en **reglas** preestablecidas.
6. El **desarrollo** de **sistemas** de información debe hacerse aplicando **principios** de **ingeniería** del software ampliamente **aceptados**.
7. Las relaciones con el exterior del departamento tienen que producirse de acuerdo a un procedimiento.
8. La organización del área debe estar siempre adaptada a las necesidades de cada momento.


### Auditoría de Proyectos de Desarrollo de S.I.

La auditoría de un proyecto de desarrollo se puede hacer en dos momentos distintos: a medida que avanza el proyecto y una vez concluido.

Las fases a auditar serán:
* **Aprobación**, **Planificación** y **Gestión del Proyecto**
* Auditoría de la Fase de **Análisis**
* Auditoría de la Fase de **Diseño**
* Auditoría de la Fase de **Construcción**
* Auditoría de la Fase de **Implementación**

#### Aprobación, Planificación y Gestión del Proyecto

**Objetivos** de **Control**:
1. El **proyecto** de **desarrollo** deberá estar **aprobado**, **definido** y **planificado** formalmente.
2. El **proyecto** se debe **gestionar** de forma que se consigan los **mejores resultados** posibles teniendo en cuenta las restricciones de tiempo y recursos.

#### Auditoría de la Fase de Análisis

La fase de análisis pretende **obtener** un conjunto de **especificaciones** formales que **describan** las **necesidades** de información que deben ser **cubiertas** por el **nuevo sistema** de forma independiente del entorno técnico. Esta fase se divide en dos módulos.

* **Análisis de Requisitos del Sistema** (ARS): En este módulo se **identificarán** los **requisitos** del nuevo sistema, tanto los **funcionales** como los **no funcionales**, se determinarán las posibles soluciones y se elegirá la más adecuada.
  1. Los **usuarios** y responsables de las unidades a las que afecta el nuevo sistema **establecerán** de forma clara los **requisitos** del mismo.
  2. En el **proyecto** de desarrollo se utilizará la **alternativa** más **favorable** para conseguir que el sistema cumpla los requisitos establecidos.
* **Especificación Funcional del Sistema** (EFS): Se elaborará una **especificación funcional detallada** del sistema que sea coherente con lo que se espera de él
  1. El nuevo sistema debe especificarse de forma completa desde el punto de vista funcional, contando esta **especificación** con la **aprobación** de los **usuarios**.

#### Auditoría de la Fase de Diseño

En la fase de diseño se **elaborará** el conjunto de **especificaciones físicas** del nuevo sistema que servirán de **base** para la **construcción** del mismo. Hay un único módulo.
* **Diseño Técnico del Sistema** (DTS)
  1. Se debe definir una **arquitectura física** para el sistema **coherente** con la **especificación funcional** que se tenga y con el entorno tecnológico elegido.

#### Auditoría de la Fase de Construcción

En esta fase se **desarrollarán** y probarán los distintos **componentes** y se pondrán en marcha todos los procedimientos necesarios para que los usuarios puedan trabajar con el nuevo sistema. Estará **basado** en las especificaciones** físicas obtenidas** en la fase de **diseño**. Tiene **dos módulos**:
* **Desarrollo** de **Componentes** del **Sistema** (DCS)
  1. Los componentes o módulos deben desarrollarse usando técnicas de programación correctas.
* **Desarrollo** de **Procedimientos** de **Usuario** (DPU)
  1. Al término del proyecto, los futuros usuarios deben estar capacitados y disponer de todos los medios para hacer uso del sistema.

#### Auditoría de la Fase de Implementación

En esta fase se realizará la **aceptación** del **sistema** por parte de los **usuarios**, además de las actividades necesarias para la puesta en marcha. Hay un único módulo.
* **Pruebas, Implementación y Aceptación del Sistema** (PIA)
  1. El sistema debe ser **aceptado formalmente** por los **usuarios** antes de ser puesto en funcionamiento.
  2. El sistema se pondrá en **funcionamiento** formalmente y pasará a estar en mantenimiento sólo cuando **haya sido aceptado** y esté preparado todo el entorno en el que se ejecutará.


# [03-05-22] Auditando Windows

Muchas organizaciones tienen entornos de dominios de distintos tamaños. Por suerte, hay numerosas herramientas que nos permiten auditar tanto dominios "standalone" como dominios de 10.000 equipos. Sin embargo, auditar un dominio muy grande puede ser desalentador

Equipos "Standalone":
* Toda la **información** está en el **propio equipo**
* Es más **simple** para obtener la **información** sobre el **sistema individual**
* Es más **difícil** **obtener información** sobre un **gran número** de **sistemas individuales**

En un "entorno de dominio":
* La **seguridad** de **un equipo** está **integrada** con la seguridad del **dominio**.
* Mucha **información** está ahora **centralizada** a nivel de **dominio**.
* **Seguridad** aplicada en "**capas**" pueden **complicar** la **auditoría** (y la solución de problemas)

**WMIC** (Windows Management Instrumentation Command-Line): Herramienta desde la CLI que nos permite exponer casi cualquier configuración con el fin de solucionar problemas y automatizar

Algunas configuraciones que nos muestra son:

* Configuración de Red (NIC)
* Configuraciones de Escritorio
* Usuarios y Grupos
* Estado de bloqueo de Contraseñas
* Información de Configuración del Sistema
* Logs de Eventos

## Auditoria de Windows - Objetivos

1. Identificar el sistema (SO, tipo, version, HW, particiones)
   1. systeminfo (CLI)
   2. winver (UI) 
2. Parches/Actualizaciones del Sistema Operativo
   1. Microsoft Baseline Security Analyzer (MBSA, UI) 
3. Componentes/Servicios Innecesarios
   1.  nmap
   2.  openports
4. Problemas con Usuarios y Grupos
   1. Net user
   2. Addusers
5. Grupos Apropiados
   1. dsquery
   2. DumpSec (Somarsoft)
6. Contraseñas Fuertes
   1. net accounts
   2. DumpSec

# [10-05-22] Auditoria de aplicaciones web

Actualmente, las aplicaciones web son muy vulnerables, uno de los principales motivos son que los servidores vienen con codigos de ejemplo predeterminados muy poco seguros que los desarrolladores suelen utilizar para basar sus servicios.

Google Hacking Database muestra muchas vulnerabilidades que afectan a estos sistemas.

Algunas de las buenas practicas que se deben de tomar para mejorar la seguridad de nuestras aplicaciones son:

## Buenas practicas

### 1 Validación y desinfección de entrada

**Validación**: **Verificar** todo lo que **ingresa** a la aplicación para comprobar que eso conforma lo que la aplicación está esperando.

**Desinfección**: **descartar** todo lo **no identificado**.

### 2 Control de Errores

Manejar todas las condiciones de error (DB, red, input, etc.)

### 3 Administración Robusta de Sesiones

Generar **IDs de Sesión Fuertes**, **aleatorios**, con una **fuerte asociación** con el **cliente** y considerar que sean **a prueba** de **falsificaciones**.

### 4 Mediación Completa

El principio de mediación completa es que hay **solamente una manera** de **ingresar** y **salir** de una **aplicación**.

### 5 Solución de Múltiples Capas

Para tener seguridad robusta, se recomienda usar tres capas:
* Presentación 
* Aplicación (o Negocio) 
* Persistencia

## Conceptos basicos de aplicaciones web

* HTTP (HyperText Transfer Protocol, solamente texto)
* Formularios Web
* GET/POST (get --> URL, post --> body)
* Métodos HTTP y REST
* Cookies
  * Las Cookies son simplemente texto:
  * El servidor envía un nombre de cookie con un valor arbitrario.
  * El cliente lo almacena y luego envía la cookie con cada petición.
  * Es posible enviar más de una cookie.
* SSL/TLS (ssl --> sifrado, no seguridad)
* AJAX
* CSS (Cascading Style Sheets)
* OWASP (Open Web Application Security Project)

## Seguridad de servidores

* Indexación en directorios
* Encabezados
* Robots.txt

## Pruebas de configuración

Analizadores: Nessus

**Fuzzing** es una **táctica antigua** con nuevas herramientas:
* **Encuentra** todos los **orificios** de entrada que tiene una aplicación.
* Automáticamente **pega** todo tipo de **basura** en todos ellos al mismo tiempo

## Metodos de autenticación

* Basic HTTP
  * Es facil de implementar
  * No tiene cifrado.
  * Fácil para fuerza bruta.
* Autenticación Basada en Formularios
  * Fácil de Implementar.
  * Balance razonable entre seguridad y conveniencia para los usuarios
  * Potencial de fuerza bruta
  * No cifrado por defecto.
* Certificados del lado del Cliente
  * Altamente seguro.
  * Permite el “no repudio”.
  * Confidencialidad.
  * Autenticación mutua.
  * Movilidad e interoperabilidad limitada.
* Autenticación NTLM
  * Solamente útil para aplicaciones de Intranet.