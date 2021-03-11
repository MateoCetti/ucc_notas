# Resumen lenguajes formales y automatas

## Indice

- [Resumen lenguajes formales y automatas](#resumen-lenguajes-formales-y-automatas)
  - [Indice](#indice)
  - [Lenguajes gramaticales y formales](#lenguajes-gramaticales-y-formales)
    - [Introduccion](#introduccion)
    - [Definiciones](#definiciones)
    - [Gramatica](#gramatica)
    - [Lenguaje](#lenguaje)

## Lenguajes gramaticales y formales

### Introduccion

Lenguaje: Genera un **vinculo comunicacional** entre el emisor y el receptor en donde **ambos entienden lo mismo**.

Ejemplo de lenguaje **gramatical**: un idioma

Ejemplo de lenguaje **formal**: Lenguaje de programacion.

Los lenguajes formales no deben dar lugar a la **ambiguedad**

### Definiciones

Para crear un lenguaje se necesita:
- **Simbolos**: Entidad abstracta no definible (a,b,c, etc.)
- vocabulario/**alfabeto**: conjunto **finito** y n**o vacio** de simbolos
- **Cadena** / **palabra**: Secuencia finita de simbolos de un determinado alfabeto.
- **Longitud de simbolos**: Cantidad de simbolos en una cadena
- **Cadena vacia**: Se denota con |λ|
- **Concatenacion de cadenas**: α.β = αβ. El elemento neutro de la concatenacion es λ 
- **Universo del discurso**: conjunto de **todas las cadenas** que se pueden formar con los simbolos de un alfabeto. 
  - Se denota W(V)
  - W(V) es un conjunto infinito
  - La cadena vacia pertenece a W(V)

- **Lenguaje**: Subconjunto del universo del discurso de un alfabeto V. Este se puede definir por:
  - **Enumeracion**: {a,aa,aab,aaab}
  - **definicion**: {a^i b^j | i>=1 ^ b>=0}
- **Lenguaje vacio**: Conjunto vacio denotado por {∅}
- **Gramatica**:ente formal para especificar, de una manera finita, el conjunto de cadenas de símbolos que constituyen un lenguaje.

### Gramatica
Cuadrupula: G{VT,VN,S,P}

Donde:
- **VT**: Simbolos terminales
- **VN**: Simbolos no terminales
- **S**: Simbolo inicial / axioma
- **P**: Producciones / reglas de derivacion

**Propiedades**:
- Todas las **cadenas** del lenguaje definido por la gramática están formados con símbolos del **vocabulario terminal** VT. 
- El **vocabulario terminal** se define por **enumeración** de los **símbolos terminales**.
- El **vocabulario no terminal** VN es el conjunto de símbolos introducidos como **elementos auxiliares** para la definición de la gramática, y que **no figuran** en las **sentencias del lenguaje**. 
- El vocabulario no terminal se define por **enumeración** de los **símbolos no terminales**.
- La **intersección** entre el **vocabulario terminal** y **no terminal** es el **conjunto vacio** : {VN} ∩ {VT} = {∅}

### Lenguaje

El lenguaje L(G) generado por una gramática G es el **conjunto** de **todas las sentencias** que puede **generar G** (L(G)= {η ∈VT / S→ η}).

Una **sentencia** pertenece a L(G) si :
- Está compuesta de **símbolos terminales**
- La sentencia puede **derivarse** del símbolo inicial **S** aplicando las reglas de **producción** de la gramática.

Dos gramáticas son **equivalentes** si ambas **generan** el **mismo lenguaje** (L(G1)=L(G2)). 