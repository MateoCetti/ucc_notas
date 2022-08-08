# Sistemas operativos

- [Sistemas operativos](#sistemas-operativos)
- [Introducción](#introducción)
  - [Clasificación de SO's](#clasificación-de-sos)
- [Capitulo 1 - Introducción a los sistemas informaticos](#capitulo-1---introducción-a-los-sistemas-informaticos)
  - [Elementos basicos](#elementos-basicos)
  - [Registros del procesador](#registros-del-procesador)
  - [Ejecución de instrucciones](#ejecución-de-instrucciones)
  - [Interrupciones](#interrupciones)
  - [Jerarquia de memoria](#jerarquia-de-memoria)
  - [Memoria cache](#memoria-cache)
  - [Tecnicas de comunicación de E/S](#tecnicas-de-comunicación-de-es)
- [Capitulo 2 - Introducción a los SO](#capitulo-2---introducción-a-los-so)
  - [Objetivos y funciones de los SO](#objetivos-y-funciones-de-los-so)
  - [Evolución de un SO __TODO__](#evolución-de-un-so-todo)
    - [Procesamiento serie](#procesamiento-serie)
    - [Sistemas en lotes sencillos](#sistemas-en-lotes-sencillos)
      - [Monoprogramación](#monoprogramación)
      - [Multiprogramación](#multiprogramación)
    - [Entornos compartidos](#entornos-compartidos)

# Introducción

## Clasificación de SO's

La construcción de un SO se asienta sobre 2 requisitos: el usuario y el software

* **Estructura**:
  * Monolitica
  * Jerarquica
* **N° usuarios**:
  * monouser
  * multiuser
* **N° tareas**:
  * Monotask
  * Multitask
* **Nro de procesadores**:
  * Monoprocesador
  * Multiprocesador
  * Simetrico
  * Asimetrico
* **Como ofrece servicios**
  * de red
  * distribuidos

# Capitulo 1 - Introducción a los sistemas informaticos

Un sistema operativo:
* explota los recursos hardware de uno o más procesadores para proporcionar un conjunto de servicios a los usuarios del sistema. 
* El sistema operativo también gestiona la memoria secundaria y los dispositivos de E/S (entrada/salida) para sus usuarios.

## Elementos basicos

Los elementos de los sistemas computacionales son:
* **Procesador**: Controla el funcionamiento del computador y realiza sus funciones de procesamiento de datos. Cuando sólo hay un procesador, se denomina usualmente unidad central de proceso (Central Processing Unit, CPU).
* **Memoria principal**: Almacena datos y programas. Esta memoria es habitualmente volátil; es decir, cuando se apaga el computador, se pierde su contenido. En contraste, el contenido de la memoria del disco se mantiene incluso cuando se apaga el computador. A la memoria principal se le denomina también memoria real o memoria primaria.
* **Modulos de E/S**: Transfieren los datos entre el computador y su entorno externo. El entorno externo está formado por diversos dispositivos, incluyendo dispositivos de memoria secundaria (por ejemplo, discos), equipos de comunicaciones y terminales.
* **Bus del sistema**: Proporciona comunicación entre los procesadores, la memoria principal y los módulos de E/S.

![](img/componentes_pc.png)

Una de las funciones del procesador es el intercambio de **datos** con la **memoria**. Para este fin, se utilizan normalmente dos registros internos (al procesador): 
* un registro de dirección de memoria (**RDIM**), que especifica la **dirección** de memoria de la siguiente lectura o escritura; 
* y un registro de **datos** de memoria (**RDAM**), que contiene los datos que se van a escribir en la memoria o que recibe los datos leídos de la memoria. 

De manera similar, un registro de **dirección** de **E/S** (**RDIE/S**) especifica un determinado dispositivo de E/S, y un registro de **datos** de **E/S** (**RDAE/S**) permite el intercambio de datos entre un módulo de E/S y el procesador.

Un **módulo** de **memoria** consta de un conjunto de **posiciones definidas** mediante **direcciones** numeradas secuencialmente. Cada posición contiene un **patrón de bits** que se puede interpretar como una instrucción o como datos. 

Un **módulo** de **E/S** transfiere datos desde los **dispositivos externos** hacia el procesador y la memoria, y viceversa. Contiene **buffers** (es decir, zonas de almacenamiento internas) que mantienen temporalmente los datos hasta que se puedan enviar.

## Registros del procesador

Los registros del procesador sirven para dos funciones:
* **Registros visibles para el usuario**: Permiten al programador en lenguaje máquina o en ensamblador **minimizar** las **referencias** a **memoria principal** optimizando el uso de registros. Para lenguajes de alto nivel, un compilador que realice **optimización** intentará tomar decisiones inteligentes sobre qué variables se asignan a registros y cuáles a posiciones de memoria principal.
* **Registros de control** y **estado**. Usados por el procesador para **controlar** su **operación** y por rutinas privilegiadas del sistema operativo para **controlar** la **ejecución** de **programas**.

Tipos de registros **visibles**:
* Registros de **datos**: De proposito general, utilizados para operaciónes sobre datos
* Registros de **dirección**: De proposito general o dedicados, utilizados para operaciónes sobre direcciones de memoria o partes de direcciones de memoria (Ej: registro indice, puntero de pila)

En algunas máquinas, una llamada a una subrutina o a un procedimiento implica **salvar** automáticamente todos los **registros visibles** para el usuario, que se **restaurarán** al retornar. El procesador realiza estas operaciones de salvar y restaurar como parte de la ejecución de las instrucciones de **llamada** y de **retorno**. En otras máquinas, el programador es el responsable de guardar el contenido de los registros visibles para el usuario antes de una llamada a un procedimiento, incluyendo instrucciones para ello en el programa

En cuanto a los **registros** de **control** y **estado**, en las maquinas se emplean varios registros del procesador para controlar el funcionamiento del mismo. Algunos registros de control son por ejemplo:
* Contador de programa (**Program Counter**, PC): Contiene la **dirección** de la **próxima instrucción** que se leerá de la memoria.
* Registro de instrucción (**Instruction Register**, IR). Contiene la **última instrucción leída**.

Todos los diseños de procesador incluyen también un **registro**, o conjunto de registros, conocido usualmente como la **palabra** de **estado** del **programa** (Program Status Word, PSW), que contiene información de **estado**. La PSW contiene normalmente **códigos** de **condición**, además de otra información de estado, tales como un bit para habilitar/inhabilitar las interrupciones y un bit de modo usuario/supervisor.

Los **códigos** de **condición** (también llamados indicadores) son **bits** cuyo valor lo asigna normalmente el **hardware** de procesador teniendo en cuenta el **resultado** de las **operaciones**. Por ejemplo, una operación aritmética puede producir un resultado **positivo**, **negativo**, **cero** o **desbordamiento**. Posteriormente, se puede **comprobar** el código de condición como parte de una operación de **salto condicional**. Los bits de código de condición no pueden ser **alterados** por una referencia **explícita** debido a que están destinados a la realimentación del resultado de la ejecución de una instrucción

## Ejecución de instrucciones

En su forma más simple, el **procesamiento** de **una instrucción** consta de **dos pasos**: 

* el procesador lee (busca) instrucciones de la memoria, una cada vez, 
* y ejecuta cada una de ellas. 

La ejecución del programa consiste en **repetir** el proceso de búsqueda y ejecución de instrucciones.

Se denomina **ciclo** de instrucción al procesamiento requerido por una única instrucción

![](img/ciclo.png)

Al principio de cada ciclo de instrucción, el procesador lee una **instrucción** de la **memoria**. En un procesador típico, el contador del programa (PC) almacena la dirección de la **siguiente instrucción** que se va a leer. A menos que se le indique otra cosa, el procesador siempre **incrementa** el PC después de cada instrucción ejecutada, de manera que se leerá la **siguiente** instrucción en orden **secuencial**.

La instrucción leída se **carga** dentro de un registro del procesador conocido como **registro de instrucción** (IR). La instrucción contiene **bits** que especifican la **acción** que debe realizar el procesador. El procesador **interpreta** la instrucción y **lleva a cabo** la acción requerida.

En general, estas acciones se dividen en cuatro categorías:
* Procesador-**memoria**
* Procesador-**E/S**
* Procesamiento de **datos**
* **Control** (Saltos, branches)

`Nota: Se pueden intercambiar datos directamente entre un módulo de E/S. sin embargo, en algunos casos, es deseable permitir que los intercambios de E/S se produzcan directamente con la memoria para liberar al procesador de la tarea de E/S. En tales casos, el procesador concede a un módulo de E/S la autorización para leer o escribir de la memoria, de manera que la transferencia entre memoria y E/S puede llevarse a cabo sin implicar al procesador. Durante dicha transferencia, el módulo de E/S emite mandatos de lectura y escritura a la memoria, liberando al procesador de la responsabilidad del intercambio. Esta operación, conocida como acceso directo a memoria (Direct Memory Access, DMA)`

## Interrupciones

Las interrupciones constituyen una manera de mejorar la utilización del procesador.  La mayoría de los dispositivos de E/S son mucho más **lentos** que el procesador. Supóngase que el procesador está transfiriendo datos a una impresora utilizando el esquema de **ciclo** de instrucción. Después de cada instrucción de escritura, el procesador debe **parar** y permanecer **inactivo** hasta que la impresora la lleve a cabo. La longitud de esta pausa puede ser del orden de muchos miles o incluso **millones** de **ciclos** de instrucción. Claramente, es un enorme desperdicio de la capacidad del procesador.

Gracias a las interrupciones, el procesador puede dedicarse a ejecutar otras instrucciones mientras que la operación de E/S se está llevando a cabo. 

**Proceso de interrupción**: 
* El programa de usuario alcanza un punto en el que hace una llamada al sistema que consiste en una llamada de **escritura** de **E/S**. El programa de E/S que se invoca en este caso consta sólo del código de preparación y el mandato real de E/S (y no la espera de confirmación de escritura). 
* Después de que se ejecuten estas pocas instrucciones, se **devuelve** el **control** al **programa** de **usuario**. Mientras tanto, el dispositivo externo está ocupado **aceptando** **datos** de la memoria del computador e **imprimiéndolos**. La operación de E/S se lleva a cabo de forma concurrente con la ejecución de instrucciones en el programa de usuario. 
* Cuando el dispositivo externo está listo para ser atendido, es decir, cuando está preparado para aceptar más datos del procesador, el módulo de E/S de este dispositivo externo manda una **señal** de petición de **interrupción** al **procesador**. 
* El procesador responde **suspendiendo** la **ejecución** del programa actual, saltando a la rutina de servicio específica de este dispositivo de E/S, conocida como **manejador** de **interrupción**, y **reanudando** la **ejecución** original después de haber atendido al dispositivo.

Para tratar las interrupciones, se añade una **fase de interrupción** al ciclo de instrucción. En la fase de interrupción, el procesador **comprueba** si se ha producido cualquier **interrupción**, hecho indicado por la presencia de una **señal** de **interrupción**. Si no hay interrupciones pendientes, el procesador **continúa** con la fase de búsqueda y lee la siguiente instrucción del **programa** actual. Si está pendiente una interrupción, el procesador **suspende** la **ejecución** del programa actual y ejecuta la rutina del **manejador** de **interrupción**.

![](img/ciclo_i.png)

![](img/int.png)

Se pueden considerar dos alternativas a la hora de tratar con múltiples interrupciones. La primera es **inhabilitar** las **interrupciones** mientras que se está **procesando** una **interrupción**.

Una segunda estrategia es **definir prioridades** para las **interrupciones** y permitir que una interrupción de más prioridad cause que se interrumpa la ejecución de un manejador de una interrupción de menor prioridad

## Jerarquia de memoria

Como se podría esperar, hay un compromiso entre las tres características fundamentales de la memoria: a saber, **coste**, **capacidad** y **tiempo** de **acceso**. En cualquier momento dado, se utilizan diversas tecnologías para implementar los sistemas de memoria. En todo este espectro de tecnologías, se cumplen las siguientes relaciones:

* Cuanto **menor tiempo de acceso**, **mayor coste** por bit.
* Cuanto **mayor capacidad**, **menor coste** por bit.
* Cuanto **mayor capacidad**, **menor velocidad** de acceso

Queda claro el dilema al que se enfrenta el diseñador. A él le gustaría utilizar tecnologías que proporcionen una memoria de gran capacidad, tanto porque se necesita esa capacidad como porque su coste por bit es bajo. Sin embargo, para cumplir con los requisitos de rendimiento, el diseñador necesita utilizar memorias de capacidad relativamente baja con tiempos de acceso rápidos.

La solución a este dilema consiste en no basarse en un único componente de memoria o en una sola tecnología, sino emplear una **jerarquía de memoria**. Según se desciende en la jerarquía, ocurre lo siguiente:
1. Disminución del coste por bit.
2. Aumento de la capacidad.
3. Aumento del tiempo de acceso.
4. Disminución de la frecuencia de acceso a la memoria por parte del procesador

![](img/jerarquia_memoria.png)


* Memoria principal -> **volatil**
* Memoria secundaria -> **no volatil**

## Memoria cache

En todos los ciclos de instrucción, el procesador accede a memoria al menos una vez, para leer la instrucción y, con frecuencia, una o más veces adicionales, para leer y/o almacenar los resultados. La velocidad a la que el procesador puede ejecutar instrucciones está claramente limitada por el tiempo de ciclo de memoria. La solución a esta limitación consiste en aprovecharse del **principio** de la **proximidad** utilizando una memoria pequeña y rápida entre el procesador y la memoria principal, denominada **cache**.

Hay una memoria principal relativamente grande y lenta junto con una memoria cache más pequeña y rápida. La cache contiene una **copia** de una **parte** de la memoria principal. Cuando el procesador intenta leer un byte de la memoria, se hace una **comprobación** para determinar si el **byte** **está** en la **cache**. Si es así, se le **entrega** el byte al **procesador**. 

En caso contrario, se lee e **introduce** dentro de la cache un **bloque** de **memoria** principal, que consta de un **cierto número** fijo de **bytes**, y, a continuación, se le **entrega** el byte pedido al **procesador**. 

Debido al fenómeno de la **proximidad** de referencias, cuando se lee e introduce dentro de la cache un bloque de datos para satisfacer una única referencia de memoria, es probable que muchas de las referencias a memoria en el futuro próximo correspondan con otros bytes del bloque (Ej: bucles).

## Tecnicas de comunicación de E/S

Hay tres técnicas para llevar a cabo las operaciones de E/S:
• **E/S programada**: el procesador **comprueba periódicamente** el estado del módulo de E/S hasta que encuentra que se ha completado la operación.
• **E/S dirigida de interrupciones**: el procesador genere un mandato de E/S para un módulo y, acto seguido, continúe realizando algún otro trabajo útil. El módulo de E/S **interrumpirá** más tarde al procesador para solicitar su servicio cuando esté listo para intercambiar datos con el mismo. El procesador ejecutará la transferencia de datos, como antes, y después reanudará el procesamiento previo.
• **Acceso directo a memoria** (DMA). Cuando el procesador desea leer o escribir un bloque de datos, genera un mandato al módulo de **DMA**. A continuación, el procesador continúa con otro trabajo. Ha delegado esta operación de E/S al módulo de DMA, que se ocupará de la misma. El módulo de DMA **transferirá** el bloque completo de datos, palabra a palabra, hacia la **memoria** o desde ella **sin pasar** a través del **procesador**. Por tanto, el procesador solamente está involucrado al **principio** y al **final** de la transferencia

![](img/tecnicas_es.png)

# Capitulo 2 - Introducción a los SO 

## Objetivos y funciones de los SO

Un **sistema operativo** es un **programa** que:
* **Controla** la **ejecución** de **aplicaciones** y **programas** 
* Actua como **interfaz** entre las **aplicaciones** y el **hardware** del computador.
* "Lo primero que arranca cuando arranca la PC (BIOS)"

Se puede considerar que un sistema operativo tiene los siguientes tres objetivos:

*  **Facilidad de uso**: Un sistema operativo **facilita** el **uso** de un computador.
* **Eficiencia**: Un sistema operativo permite que los **recursos** de un sistema de computación se puedan **utilizar** de una manera **eficiente**.
* Capacidad para **evolucionar**: Un sistema operativo se debe construir de tal forma que se puedan desarrollar, probar e **introducir nuevas funciones** en el sistema sin interferir con su servicio.

![](img/niveles_SI.png)

Algunos de los servicios que ofrece el SO son:

* **Desarrollo** de programas
* **Ejecución** de programas
* Acceso a dispositivos de **E/S**.
* Acceso controlado a los **ficheros**.
* Acceso al **sistema**.
* **Detección** y **respuesta** a **errores**
  * Errores de HW
    * Internos
    * Externos
  * Errores de SW
    * Division por cero
    * Acceso prohibido a memoria
* **Contabilidad** (estadistica)
  * Recoger estadisticas
  * Supervisar su rendimiento
  * Utilizado para anticiparse a las mejoras futuras
  * Utilizando a los usuarios de cuotas

¿Se puede decir que es el sistema operativo quien controla el transporte, almacenamiento y procesamiento de los datos? Desde un punto de vista, la respuesta es afirmativa. **Gestionando** los **recursos** del **computador**, el sistema operativo tiene el control de las **funciones básicas** del mismo.
 
El sistema operativo deja el control para que el procesador pueda realizar trabajo «útil» y de nuevo retoma el control para permitir al procesador que realice la siguiente pieza de trabajo.

![](img/so_recursos.png)

**Nucleo** / **kernel**: Una porción del sistema operativo se encuentra en la **memoria principal**. Contiene las funciones del sistema operativo más frecuentemente utilizadas y, en cierto momento, otras porciones del sistema operativo actualmente en uso. El resto de la memoria principal contiene programas y datos de usuario.

Un sistema operativo importante debe evolucionar en el tiempo por las siguientes razones:
* Actualizaciones de hardware más nuevos tipos de hardware.
* Nuevos servicios
* Resolución de fallos

## Evolución de un SO __TODO__

### Procesamiento serie

### Sistemas en lotes sencillos

#### Monoprogramación

#### Multiprogramación

### Entornos compartidos