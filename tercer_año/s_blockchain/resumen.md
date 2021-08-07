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

para 2140 no va a haber mas bitcoins nuevos.