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
    - [Facilidad de uso](#facilidad-de-uso)
    - [Eficiencia](#eficiencia)
    - [Capacidad de evolución](#capacidad-de-evolución)
  - [Evolución de un SO](#evolución-de-un-so)
    - [Procesamiento serie](#procesamiento-serie)
    - [Sistemas en lotes sencillos](#sistemas-en-lotes-sencillos)
    - [Sistemas en lotes multiprogramados](#sistemas-en-lotes-multiprogramados)
    - [Sistemas de tiempo compartido](#sistemas-de-tiempo-compartido)

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

### Facilidad de uso

Algunos de los **servicios** que ofrece el SO son:

* **Desarrollo de programas**: El sistema operativo proporciona una variedad de utilidades y servicios, tales como **editores** y **depuradores**, para asistir al programador en la creación de los programas
* **Ejecución** **de programas**: Se necesita realizar una serie de pasos para ejecutar un programa. Las instrucciones y los datos se deben cargar en memoria principal. Los dispositivos de E/S y los ficheros se deben inicializar, y otros recursos deben prepararse. Los sistemas operativos realizan estas labores de planificación en nombre del usuario
* **Acceso a dispositivos de** **E/S**: Cada dispositivo de E/S requiere su propio conjunto peculiar de instrucciones o señales de control para cada operación. El sistema operativo proporciona una interfaz uniforme que esconde esos detalles de forma que los programadores puedan acceder a dichos dispositivos utilizando lecturas y escrituras sencillas.
* **Acceso controlado a los** **ficheros**: Para el acceso a los ficheros, el sistema operativo debe reflejar una comprensión detallada no sólo de la naturaleza del dispositivo de E/S (disco, cinta), sino también de la estructura de los datos contenidos en los ficheros del sistema de almacenamiento. Adicionalmente, en el caso de un sistema con múltiples usuarios, el sistema operativo puede proporcionar mecanismos de protección para controlar el acceso a los ficheros.
* **Acceso al** **sistema**: Para sistemas compartidos o públicos, el sistema operativo controla el acceso al sistema completo y a recursos del sistema específicos.
* **Detección** y **respuesta** a **errores**: El sistema operativo debe proporcionar una respuesta que elimine la condición de error, suponiendo el menor impacto en las aplicaciones que están en ejecución.
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

### Eficiencia

¿Se puede decir que es el sistema operativo quien controla el transporte, almacenamiento y procesamiento de los datos? Desde un punto de vista, la respuesta es afirmativa. **Gestionando** los **recursos** del **computador**, el sistema operativo tiene el control de las **funciones básicas** del mismo.

El sistema operativo dirige al procesador en el uso de los otros recursos del sistema y en la temporización de la ejecución de otros programas. No obstante, para que el procesador pueda realizar esto, el sistema operativo debe dejar paso a la ejecución de otros programas. Por tanto, 
El sistema operativo deja el control para que el procesador pueda realizar trabajo «útil» y de nuevo retoma el control para permitir al procesador que realice la siguiente pieza de trabajo.

![](img/so_recursos.png)

**Nucleo** / **kernel**: Una porción del sistema operativo se encuentra en la **memoria principal**. Contiene las funciones del sistema operativo más frecuentemente utilizadas y, en cierto momento, otras porciones del sistema operativo actualmente en uso. El resto de la memoria principal contiene programas y datos de usuario.

El sistema operativo decide cuándo un programa en ejecución puede utilizar un dispositivo de E/S y controla el acceso y uso de los ficheros. El procesador es también un recurso, y el sistema operativo debe determinar cuánto tiempo de procesador debe asignarse a la ejecución de un programa de usuario particular.

### Capacidad de evolución

Un sistema operativo importante debe evolucionar en el tiempo por las siguientes razones:
* Actualizaciones de hardware más nuevos tipos de hardware.
* Nuevos servicios
* Resolución de fallos

## Evolución de un SO

Para comprender los requisitos claves de un sistema operativo y el significado de las principales características de un sistema operativo contemporáneo, es útil considerar la evolución de los sistemas operativos a lo largo de los años.

### Procesamiento serie

Con los primeros computadores, desde finales de los años 40 hasta mediados de los años 50, el programador interaccionaba **directamente** con el **hardware** del computador; no existía ningún sistema operativo.

Estas máquinas eran utilizadas desde una consola que contenía luces, interruptores, algún dispositivo de entrada y una impresora. 

Los programas en **código máquina** se cargaban a través del dispositivo de entrada (por ejemplo, un lector de **tarjetas**). Si un error provocaba la parada del programa, las **luces** indicaban la condición de **error**. 

El programador podía entonces **examinar** los **registros** del procesador y la memoria principal para determinar la causa de error. Si el programa terminaba de forma normal, la salida aparecía en la impresora.

Estos sistemas iniciales presentaban dos problemas principales:

* **Planificación**. La mayoría de las instalaciones utilizaban una **plantilla impresa** para **reservar tiempo de máquina**. Típicamente, un usuario podía solicitar un bloque de tiempo en múltiplos de **media hora** aproximadamente. Un usuario podía obtener una hora y terminar en 45 minutos; esto implicaba **malgastar tiempo** de procesamiento del computador.
* **Tiempo de configuración**. Un único programa, denominado trabajo, podía implicar la **carga en memoria** del **compilador** y del **programa** en lenguaje de alto nivel (programa en código fuente) y a continuación la carga y el enlace del programa objeto y las funciones comunes. Cada uno de estos pasos podían suponer **montar** y **desmontar** cintas o configurar **tarjetas**. Si ocurría un error, el desgraciado usuario normalmente tenía que **volver al comienzo** de la secuencia de configuración. Por tanto, se utilizaba una cantidad considerable de tiempo en configurar el programa que se iba a ejecutar.

Este modo de operación puede denominarse procesamiento serie, para reflejar el hecho de que los usuarios acceden al computador en serie.

### Sistemas en lotes sencillos

La idea central bajo el esquema de procesamiento en lotes sencillo es el uso de una pieza de **software** denomina **monitor**. Con este tipo de sistema operativo, el usuario no tiene que acceder directamente a la máquina. En su lugar, el usuario **envía** un **trabajo** a través de una **tarjeta** o cinta al operador del computador, que crea un **sistema por lotes** con todos los trabajos enviados y coloca la **secuencia de trabajos** en el dispositivo de **entrada**, para que lo utilice el **monitor**. Cuando un programa finaliza su procesamiento, devuelve el control al monitor, punto en el cual dicho monitor comienza la carga del siguiente programa.

El monitor realiza una función de **planificación**: en una **cola** se sitúa un **lote de trabajos**, y los trabajos se ejecutan lo más rápidamente posible, sin ninguna clase de tiempo ocioso entre medias. Además, el monitor mejora el **tiempo de configuración** de los trabajos. Con cada uno de los trabajos, se incluye un conjunto de **instrucciones** en algún formato primitivo de **lenguaje de control de trabajos** (Job Control Language, JCL).

El monitor, o sistema operativo en lotes, es simplemente un programa. Éste **confía** en la habilidad del procesador para **cargar instrucciones** de diferentes porciones de la memoria principal que de forma alternativa le permiten tomar y abandonar el control. Otras características hardware son también deseables:

* **Protección de memoria**. Durante la ejecución del programa de usuario, éste no debe alterar el área de memoria que contiene el monitor. Si esto ocurriera, el hardware del procesador debe detectar un error y transferir el control al monitor. El monitor entonces abortará el trabajo, imprimirá un mensaje de error y cargará el siguiente trabajo.
* **Temporizador**. Se utiliza un temporizador para evitar que un único trabajo monopolice el sistema. 
* **Instrucciones privilegiadas**. Ciertas instrucciones a nivel de máquina se denominan privilegiadas y sólo las puede ejecutar el monitor.
* **Interrupciones**. Los modelos de computadores iniciales no tenían esta capacidad. Esta característica proporciona al sistema operativo más flexibilidad para dejar y retomar el control desde los programas de usuario.

Ciertas consideraciones sobre la protección de memoria y las instrucciones privilegiadas llevan al concepto de **modos de operación**. Un programa de usuario ejecuta en **modo usuario**, en el cual los usuarios no pueden acceder a ciertas áreas de memoria y no puede ejecutar ciertas instrucciones. El monitor ejecuta en **modo sistema**, o lo que se denomina modo núcleo, en el cual se pueden ejecutar instrucciones privilegiadas y se puede acceder a áreas de memoria protegidas.

### Sistemas en lotes multiprogramados

El procesador se encuentra frecuentemente ocioso, incluso con el secuenciamiento de trabajos automático que proporciona un sistema operativo en lotes simple. El problema consiste en que los dispositivos de E/S son lentos comparados con el procesador. El procesador ejecuta instrucciones durante cierto tiempo hasta que alcanza una instrucción de E/S. Entonces debe esperar que la instrucción de E/S concluya antes de continuar (**Monoprogramación**).

![](img/monoprog.png)

Esta ineficiencia puede evitarse. Se sabe que existe suficiente memoria para contener al sistema operativo (monitor residente) y un programa de usuario. Supóngase que hay espacio para el sistema operativo y dos programas de usuario. Cuando un trabajo necesita **esperar** por la E/S, se puede **asignar** el procesador al **otro trabajo**, que probablemente no esté esperando por una operación de E/S. Más aún, se puede expandir la memoria para que albergue tres, cuatro o más programas y pueda haber **multiplexación** entre todos ellos. Este enfoque se conoce como **multiprogramación** o multitarea. Es el tema central de los sistemas operativos modernos.

![](img/multiprogramacion.png)

Del mismo modo que un sistema en lotes simple, un sistema en lotes multiprogramado también debe basarse en ciertas características hardware del computador. La característica adicional más notable que es útil para la multiprogramación es el hardware que soporta las **interrupciones** de E/S y **DMA** (Direct Memory Access: acceso directo a memoria). Con la E/S gestionada a través de interrupciones o DMA, el procesador puede solicitar un mandato de E/S para un trabajo y continuar con la ejecución de otro trabajo mientras el controlador del dispositivo gestiona dicha operación de E/S. Cuando esta última operación finaliza, el procesador **es interrumpido** y se pasa el control a un programa de tratamiento de interrupciones del sistema operativo. Entonces, el sistema operativo pasará el control a otro trabajo.

Los sistemas operativos multiprogramados son bastante **sofisticados**, comparados con los sistemas monoprogramados. Para tener varios trabajos listos para ejecutar, éstos deben guardarse en memoria principal, requiriendo alguna forma de **gestión de memoria**. Adicionalmente, si varios trabajos están listos para su ejecución, el procesador debe decidir **cuál** de ellos **ejecutar**; esta decisión requiere un **algoritmo** para **planificación**.

### Sistemas de tiempo compartido

la técnica se denomina **tiempo compartido** porque se **comparte** el **tiempo** de **procesador** entre **múltiples usuarios**. En un sistema de tiempo compartido, múltiples usuarios acceden **simultáneamente** al **sistema** a través de **terminales**, siendo el sistema operativo el encargado de entrelazar la ejecución de cada programa de usuario en pequeños intervalos de tiempo o cuantos de computación.

Ambos tipos de procesamiento, en lotes y tiempo compartido, utilizan **multiprogramación**.

![](img/tiempo_compartido.png)

La compartición de tiempo y la multiprogramación implican nuevos problemas para el sistema operativo. Si existen múltiples trabajos en memoria, éstos deben protegerse para evitar que interfieran entre sí, por ejemplo, a través de la modificación de los datos de los mismos. Con múltiples usuarios interactivos, el sistema de ficheros debe ser protegido, de forma que sólo usuarios autorizados tengan acceso a un fichero particular. También debe gestionarse los conflictos entre los recursos, tal como impresoras y dispositivos de almacenamiento masivo. 

