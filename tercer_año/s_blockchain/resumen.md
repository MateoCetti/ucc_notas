# Seminario de Blockchain

## Notas:

* Libro: Andreas M. Antonopoulos
* Parciales presenciales (quizas)

## Introduccion

Concepto economico de **dinero**:

Todo activo bien aceptado como medio de pago o medicion del valor...

Propiedades del dinero:
* Unidad de cuenta y patron de precios
* Medio de pago
* Deposito de valor

"El dinero es una tecnologia y una forma de lenguaje tan antigua como el mismo"

Etapas del **dinero**:
* Trueque
* Dinero mercancia
* Dinero metalico (oro)
* Dinero papel
* Dinero Fiduciario (fe)
* Dinero de plastico/ Bancario

`Nota: Acuerdos de Bretton Woods 1944`

`Nota: Emision de dinero es centralizada`

`Nota: Mayor cantidad de dinero es digital`

## Bitcoin

Bitcoin propone un nuevo modelo de confianza, la confianza en la tecnologia. Surgio debido a la crisis del 2008

Bitcoin es dinero digital, una moneda, una tecnologia, y una red internacional de pagos e intercambios totalmente **descentralizada**, no sustentada en los bancos ni en cualquier gobierno.

Bitcoin es el internet del dinero, no el dinero de internet.

* Bitcoin es dinero digital, se puede enviar a cualquier lugar del mundo de manera instantania con una comicion minuscula.
* No es una compania ni una organizacion, sino un protocolo estandar. (regulada por una organizacion)

`Nota: Blockchain es 1 de las 4 tecnologias de bitcoin (Bitcoin protocol, blockchain, consensus rules, proof-of-work algorithm)`

`Nota: Satoshi nakamoto, cypherpunks`

Bitcoin soluciona: 
* La necesidad de contar con un intermediario al realizar una transaccion
* El problema del doble gasto

Bitcoin es:
- Unidad monetaria
- Red p2p
- Software

**Red P2P**: Red de usuarios o pares en donde no hay un **servidor central**, sino que las partes actuan de manera autonoma respondiendo a un protocolo de comunicaciones y consenso comun. (Todos los usuarios conectados a la red p2p son usuarios y servidor al mismo tiempo, por lo que la velocidad de transferencia de archivos se mejora, como bittorrent)

**Criptografia asimetrica**: Metodo criptografico que usa un **par** de claves para el envio de mensajes. Una publica y una privada (la privada es la que nos da propiedad sobre el bitcoin). El hasheo es de una sola direccion.

**Firma digital**: A travez de ambas claves de la criptografia asimetrica se firma la transaccion (mensajes).

## Blockchain


**SHA 256 - Secure Hash Algorithm**: Huella digital de cualquier tipo de dato o informacion

Caracteristicas de SHA 256:

* **Unidireccional**: No se puede descifrar un contenido sifrado
* **Equilibrio** entre **seguridad** y **costo computacional** adecuado, por lo que es el mas usado
* La **longitud** del hash es **siempre igual**

**Bloque**:

Es como un elemento o como un nodo que tiene los campos 
* Nonce: Numero que se busca obtener para que haya x cantidad de ceros al principio del hash. 
* datos: Los datos del bloque
* hash: La "firma"

`Nota: Un hash que empieza con 4 ceros es admitido por la blockchain, significa que el bloque esta confirmado o firmado`

Una blockchain es una cadena de bloques, cada bloque apunta al anterior.

**Bloque genesis**: El primer bloque, no tiene antecesor.

Si modificamos un bloque, todos los demas bloques d ela cadena que apuntan a dicho bloque, o a bloques q apuntan a este bloque se rompen

**Blockchain Distribuida**

Es una blockchain con x cantidad de copias de la misma (Peers). Si hay alguna copia distinta de las demas, esta se descarta.

**Criptomoneda**: Sistema de intercambio de valor autosostenible

**Token**: Medio para representar cosas del mundo real, no es autosostenible, depende de otro sistema para funcionar.

**Criptomoneda != Token**

**Coinbase transactions (?)**

Cuando un minero resuelve la transaccion / termina de minar un bloque, recibe una cantidad de coins, estos coins son otorgados en base a la cantidad de bloques actulales y la "coinbase" 

para 2140 no va a haber mas bitcoins nuevos (21 millones).

**Tipos de redes**

![](./img/redes.png)

La **red centralizada** es aquella en el que los ordenadores son perifericos y todos estan conectados a unidad central sobre la que recae todo el control y gestion de la red.

**Beneficios**
* Mucho mas rapido
* Entre otras

**Contras**
* Si se ataca al servidor, se cae todo el sistema.

Hay "blockchain's" centralizadas como Ripple y Hyperledger

Las **redes descentralizadas** (Dash, EOS) no llegan a ser **distribuidas**. Hay ciertos nodos con mucho mas poder que otros. Los nodos no son todos iguales

Las **redes distribuidas** (Bitcoin, Bittorrent) no tienen ningun centro individual o colectivo. los ordenadores se unen uno a otro de tal forma que ninguno de ellos tiene el poder de filtro sobre la info que se transmite en la red. Este tipo de red es practica, robusta y eficiente.

## Doble gasto

Un acto / ataque en el que se hace una copia de una moneda y se utiliza para realizar mas de una transaccion. Es un efecto potencial del dinero digital.

Bitcoin para prevenir el doble gasto realiza una validacion y registro de todas las transacciones realizadas y se realiza una verificacion para comprobar la autenticidad de cada operacion mediante la aplicacion de un instrumento conocido como prueba da trabajo.

## Generales bizantinos

Se puede atacar al sistema si se tiene una cantidad de nodos muy grande dedicado a atacar dicho sistema. Bitcoin y Blockchain preveen esto.

**Tecnologias del Bitcoin**

* **Bitcoin protocol**: Red descentralizada P2P
* **The Blockchain**: Libro de registros publicos de transacciones en forma de cadena de bloques
* **Reglas de consenso**: Reglas para la validacion de transacciones y emision monetaria
* **Proof of work**: Sistema descentralizado de verificacion de transacciones
* Criptografia asimetrica

## Nodo

Punto de conexion fisico o virtual donde se puede crear, enviar y recibir toda clase de datos e informacion. Son ordenadores que estan interconectados a la red de una criptomoneda

* **Nodos completos**: Implementan el cliente de bitcoin y almaecenan una copia exacta, completa y actualizada de la blockchain de bitcoin
* **Supernodos**: Son todos aquellos **nodos completos** que **operan** en la red de bitcoin de forma publica y abierta.
* **Nodo de mineria**: **Nodos completos** que ejecutan un **software de mineria**
* **Nodos ligeros**: Aquellos nodos que dependen de un tercero para realizar las validaciones de las transacciones de la red. No almacenan una copia completa de la blockchain, reciben la info de supernodos. Se utilizn apra ejecutar operaciones en dispositivos moviles o brindar servicios como wallets.

## Blockchain

Cadena de bloques, un libro mayor de acontecimientos digitales que esta distribuido o compartido entre muchas partes diferentes. Solo puede ser actualizado a partir del ocnsenso de la mayoria de participantes del sistema y, una vez introducida, la info nunca puede ser borrada.

Los bloques tienen mas o menos 2000 transacciones, que es el equivalente a 2 megas de informacion. Pero gracias a la blockchain, cada bloque tiene indirectamente todas las transacciones porque cada bloque apunta al bloque anterior, que contiene otras 2000 transacciones

Pilares de las **blockchains publicas**

* Son **revolucionarias** 
* **Open**: Accesible por todos 
* **Borderless**: Internacional / global / universal
* **Neutrales**: Se puede transferir sin interceptar o cuestionar dicha transaccion.
* **Incensurable**: Ninguna autoridad puede detener la transferencia de fondos de una cuenta a otra.
* **Inmutable**: Es muy dificil de mutar.
* Auditable/transparente/publica: Todas las transacciones pueden ser verificables por todos los usuarios de la red.
* **Privada**: Es anonimo

## Reglas de concenso

Tener consenso respecto a la historia de las transacciones y sobre las reglas necesarias para agregar transacciones.

![](./img/consenso.png)

Para evitar que se añadan bloques erroneos, cada uno de esos bloques necesita una revision y confirmacion. 

Todos los nodos deben aceptar los datos para confirmar la integridad de los nuevos bloques.

Los mineros son imprecindibles para que las transaccines sean incluidas en un bloque.

Con este sistema nos aseguramos que ninguna entidad puede manipular o controlar la red.

Cuando se rompe el consenso se generan bifurcaciones (hard fork o soft fork)

* **fork**: difurcación de la blockchain por descubrimiento de bloques simultaneos (gana la cadena mas larga)
* **soft fork**: Cambian las reglas de consenso, pero todos los nodos se ponen de acuerdo y se sigue la misma cadena.
* **hard fork**: Cambian las reglas de consenso, generando una pelea entre los nodos y formando 2 cadenas distintas (etherium / etherium classic)

## Proof of work (Mineria)

**Ataque Sybil**:

![](./img/sybil.png)

En bitcoin, una PC solo puede realizar 1 voto mediante la proof of work (Este fue creado en un principio para evitar el spam). Para resolver y activar un nodo, se debe de resolver un problema matematico (hash) mediante un mecanismo de pureba y error. Esto es muy costoso y lleva su tiempo, por lo que una PC tiene q estar dedicada solo a eso.

* **Etapa 1**: El cliente se conecta con la red P2P y se le asigna una tarea costosa (+ o - costosa depende de la cantidad de ceros asignados al hash) para recibir un incentivo economico.
* **Etapa 2**: Se resuelve el acertijo (mineria), cosa que conlleva el uso de mucha potencia de computacion.
* **Etapa 3**: Una vez resuelta la terea computacional, el cliente comparte con la red para verificar los resultados. Si se cumplen los requisitos, se brinda el acceso a los recursos de la red.
* **Etapa 4**: Con la confirmacion de la tarea, el cliente accede a los recursos de la red y recibe una ganancia por el trabajo computacional realizado.

## Clase practica N°2

Claves **publicas** y **privadas** / funcionamiento de las **firmas digitales**

**Clave privada**: Numero largo y random, secreta y perteneciente a cada usuario.

**Clave publica**: Es como el CBU o DNI, es decir que es publica y se comparte con todo el mundo. Teniendo una clave publica **no se puede obtener** la privada.

Para **encriptar** un mensaje, se usa la **llave publica**, para **desencriptarlo** la **privada**.

Para **firmar** un mensaje se utiliza la **clave privada**, para **verificar** la firma, se usa la **clave publica**.

### Dash

Dash es una moneda digital que aporta elementos propios llamados **nodos maestros**. Tiene una (DAO, organizacion autonoma descentralizada) y cuenta confucniones especificas opcionales para enviar transacciones (privateSend e instantSend). Para el año  va a haber  18.900.000 monedas como maximo, un bloque se genera cada 2.6 minutos y el halving es de 1 año y se reduce un %7.14 mas rapido que en bitcoin.

Dash soluciona la privacidad y rapidez de bitcoin. (privacidad porque en bitcoin los registros son publicos, por lo que se pueden trackear las transacciones.)

Los nodos maestros son como nodos completos de bitcoin pero con funcionalidades adicionales. Estos confirman transacciones sin que toda la red participe en el proceso, lo que reduce el tiempo y costo de las operaciones.

El privateSend cruza nuestra operacion con la de otros usuarios, por lo que no se van a poder rastrear y asi se puede mejorar la privacidad.

Los nodos maestros solo son usados al realizar operaciones instantaneas o privadas.

## Transacciones

Una transaccion esta formada por:
- input: referencias de una transaccion pasada que no ha sido empleada en ninguna otra transaccion
- output: Direccion a la cual se realiza la transferencia y la direccion de cambio o retorno
- identificador(TXid): Direccion de hash que se genera a partir de las entradas y las salidas.
- tarifa de comicion(fee): Pequeño pago que reciben los mienros por procesar una transaccion.

## Mineros / mineria

**Rol**

* Guardan y transmiten bloques en la blockchain
* validan transacciones nuevas
* votan sobre el consenso con el poder del hash

`Nota: ASIC de mineria`

**¿Se puede hacer dinero minando?**

Respuesta corta: si

Pasos para minar;

* Unirse a la red y recibir transacciones (validarlas)
* Recibir nuevos bloques (validarlos)
* Armar un nuevo bloque
* Encontrar el nonce que hace tu bloque valido
* Esperar que todos acepten tu nuevo bloque
* Disfrutar de las ganancias!

**Opciones de minerias**

* Opcion 1
    * Bajar un software de minado
    * Conectarse a internet y correr el software
* Opcion 2
    * Comprar un hardware especializado
    * Conectarlo a internet y hacerlo andar
* Opcion 3
    * Unirse a una pool de mining

![](./img/ev_minado.png)

**Consumo de energia del minado**

La energia para manufacturar las PC's deberia disminuir con el tiempo. 
Sin embargo, la energia para mantener dichas computadoras deberia aumentar con el tiempo (Esta es la gran contra del proof of work).

**Mining pool**

Es como un pool de siembra. En vez de dinero brindamos poder de computo.
Todos los miembros minan como si fuesen uno. Cuando la pool es recompenzada por enonctar 
un hash correcto, la recompensa es distribuida por todos los miembros involucrados
en dicha mineria.

**Ventajas**

* Minado mas predecible
* Mineros pequeños pueden participar en la red
* Mas mineros con software actualizado (?)

**Desventajas**

* Centralizacion y menos mineros corriendo nodos completos.

**Proof of work**

El procedimiento consiste en encontrar un NONCE tal que hasheando con los datos del bloque el hash sea menor a cierto numero TARGET que determina la dificultad (inverso a la cantidad de ceros).

Si se encuentran 2 nonce al mismo tiempo para un bloque, entonces se difurca la blockchain y va a ganar la blockchain que mas bloques tenga despues.

![](./img/2_target.png)

A los bloques que no son aceptados en la blockchain (bloques azules) se los denomina bloques huerfanos.

**Proof of stake "Prueba de participacion"**

Tambien referenciado como virtual mining.

Beneficios:

* Menores costos
    * No hay gasto de recursos
    * Ahorro redistribuido al ecosistema
    * No hay daños al medioambiente
* Los que poseen monedas tienen un incetivo a portarse vien
* Un ataque del 51% es aun mas dificil

![](./img/pf_vs_ps.png)

**Tamper proof**

Una blockchain esta a prueba de modificaciones ya que al modificar una simple transaccion, se modifica todo el hash, por lo que se modifica toda la blockchain.

## Transacciones

Una transaccion es un mensaje en donde yo le doy a otro el derecho a gastar.

Las transacciones tienen:

* **Inputs**: referencia de una transaccion pasada
* **Outputs**:
    * Direccion de destino
    * Direccion de retorno
* **TXid**: hash propio (generado por input, output y fee)
* **fee**: pago a los mineros

## Arbol de Merkle

Dentro de un bloque en bitcoin tenemos un arbol de merkle.

Estructura de datos dividida en varias capas que tiene como finalidad relacionar cada nodo con una raiz unica asociada a los hijos.

![](./img/merkle.png)

La raiz de este arboles un hash con el resumen de todas las transacciones de un bloque. cada nodo tiene el hash de x cantidad de transacciones, excepto los nodos raiz que solo tienen el hash de 1 transaccion.

Etapas del minado:
* **Transaccion** (se crean las transacciones)
* **Compilacion** (agarrar todas las transacciones y agruparlas en un bloque)
* **Formacion** (formar el merkle y agregar mas datos al bloque)
* **Prueba de trabajo** (encontrar un nonce)
* **Transmision** (mandar el bloque con el nonce y el hash a la red para q sea aceptado)
* **Verificacion** (se verifica la legitimidad del bloque)
* **Confirmación** (Cuando se añade un nuevo bloque al bloque en cuestion)

## Forks

Un fork hace referencia al despliegue de cambios en el codigo de una crypto o token. Es una bifurcación que ocurre cuando los desarrolladores implementan cambios en la version actual del codigo.Tomando en cuenta que la blockchain es una estuctura de datos descentralizada y que hay diferentes copias alojadas en los nodos que no son consistentes, lo que ocurre es que estas acaban teniendo versiones diferentes en momentos distintos.

* Se utiliza cuando se **clona** un codigo fuente de una cripto. Las nuevas criptomonedas que se crean por un fork o bifurcacion son **altcoins**
* Surge como actualizacion del codigo fuente de una blockchain. puede ser intencional a **no intencional**.
* **Hard/ soft fork**: En este caso se refiere a cuando se introduce conscientemente cambios o implementaciones en el codigo Bitcoin de manera **consciente** (no accidental) Hard y soft fork se diferencian por el nivel de compatibilidad con las versiones anteriores.
    * **Hard fork**: Hay una division filosofica. La mayoria de los bloques son generados por un conjunto de nodos utiliando nuevas reglas de consenso (termina habiendo 2 monedas distintas) 
    * **soft fork**: Se hacen cambios sobre las reglas de consenso de tal manera que todos los nodos estan de acuerdo. pero en el caso de que hayan nodos q no esten de acuerdo, pueden seguir perteneciendo a la misma blockchain sin problema.

**DAO** (organizacion autonoma descentralizada autonoma, se gobierna a si misma.)

## Problemas de bitcoin y las cryptos

**Escalabilidad**

La cantidad de transacciones por segundo es muy baja. (bitcoin soporta hasta 7 transacciones por segundo)

La capacidad de un sistema para crecer y asi acomodar una demanda creciente.

![](./img/trilema.png)

**Soluciones on-chain**: soft-forks

**Soluciones off-chain**: realizar las transacciones por fuera de la blockchain (?) 

**Canales de pago**: Lightning network (?)

**Interoperabilidad**

No se puede realizar transacciones entre blockchains distintas. Para una blockchain, la otra no existe

## Guardar y usar criptomonedas

El metodo mas simple es usar un celular o una PC mediante una app. 

Siempre lo tenemos con nosotros, pero si se pierde o rompe la app, se pierde la clave y por lo tanto el derecho a usar las monedas (la posesion de las mismas)

La seguridad va a ser la que vos le brindes a tu dispositivo.

No deberias de tener todos tus ahorros siempre a mano.

Hot storage: internet / online

Cold storage: sin internet / offline (acceso mas dificil, pero mas seguro)

![](./img/hd.png)

Algunos dispositivos para guardar cold info son:

* Brain wallet
* Ledger
* Dispositivos especiales (tamperproof)

**Mas seguridad**

Las secret key se pueden dividir y compartir / separar para q al hacer una operacion se necesite el consenso de la mayoria de las partes.

**Online wallets**

Funcionan desde browsers o apps, administran las keys por nosotros.

**Exchanges**

Servicios que aceptan depositos de criptos y fiat money y implementan algun tipo de wallets.
Estos son muy similares a los bancos tradicionales pero con cryptos.

**Unidad minima de un bitcoin**

Un **satoshi** es la unidad mínima de medida que se puede utilizar en el sistema Bitcoin. Es la fracción más pequeña en la que puedes dividir un bitcoin. De igual forma que un euro es divisible en 100 céntimos, un bitcoin es divisible en 100,000,000 de “céntimos” llamados satoshis.

1 satoshi = 0,00000001 bitcoins

1 bitcoin = 100,000,000 satoshis

**Wallet**

Monedero virtual (llavero virtual) con el que podemos gestionar activos criptograficos, almacenando las claves publicas y privadas.

**Lightweight wallets**

Monederos que funcionan usando una conexion con una serie de servidores (nodos completos) que le permiten obtener toda la informacion que necesitan sobre los pagos en criptomonedas que hacen. Es una forma simplificada de un monedero que hace innecesario ejecutar un **full node**, mientras mantiene un buen equilibrio entre seguridad y usabilidad.

Nos permiten gestionar todos los activos con rapidez y seguridad sin necesidad de descargar toda la blockchain.

**Caracteristicas**:

1. Dispones del control de claves privadas
2. No necesitan descargar toda la blockchain
3. Se reduce el tiempo de sincronizacion
4. son gratuitas
5. etc.

**Simplified Payment verification**

Sistema implementado en la red para verificar pagos.

![](./img/spv_3.png)

![](./img/spv.png)

![](./img/sov2.png)


**Herarchical Deterministic wallets**

Monedero que ofrece una interfaz grafica y se encarga de **crear direcciones**. Estas tienen asociada una clave privada.

Emplean una unica semilla de 12, 18 o 24 palabras claves. con la que pueden generar un numero ilimitado de direcciones. Esto se realiza de forma automatica, jerarquica y secuencial.

Esto se genero en la BIP 32.

![](./img/hd_carac.png)

**Tipos de wallets**

Segun quien maneja las claves:
* Sin custodia: El usuario se encarga de manejar sus claves privadas
* Con custodia: El usuario delega en un tercero el manejo de sus claves privadas. (Exchangex centralizados, CEX)

Segun conectividad (?)
* Hot wallet: Estan conectadas a internet. Ofrecen un rapido y comodo acceso a los fondos. Pueden estar en smartphones, online o en desktops.
* Cold wallet: No estan conectadas a internet

**Exchange**

Casa de cambio de criptomonedas y/o moneda fiat. Han sido fundamentales para la introduccion de las personas al mundo de las criptos. Son estructuras muy centralizadas. (Binance)

Los exchange operan off-chain y funcionan como market maker (?)

**DEX exchange descentralizado**

Evolucion de los exchanges tradicionales. Sin custodia conecto mi wallet y hago la transaccion P2P

No existen intermediarios y la plataforma se autosustenta por su programacion. Ademas de que roveen altos niveles de privacidad y anonimato.

