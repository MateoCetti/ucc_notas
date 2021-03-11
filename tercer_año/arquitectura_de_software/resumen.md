# Resumen Arquitectura de software

- [Resumen Arquitectura de software](#resumen-arquitectura-de-software)
  - [Introduccion](#introduccion)
    - [Repaso de POO](#repaso-de-poo)
    - [SOLID](#solid)
  - [Principio de responsabilidad simple](#principio-de-responsabilidad-simple)
    - [Cuando aplicar este principio](#cuando-aplicar-este-principio)

## Introduccion

Los **principios de programacion** son un conjunto de reglas que al aplicarlas al escribir codigo mejoran la **mantenibilidad** y **extensibilidad** del mismo.

Uno de estos principios es conocido como principios **SOLID** (Principios, no reglas)

Algunos de los problemas que empeoran la "calidad" del codigo son por ejemplo:
- Codigo muy grande
- Codigo repetido
- Necesidad de retocar codigo ya desarrollado para realizar un cambio al programa
- Complejidad ciclomatica elevada (Muchas sentencias dentro de otras sentencias)

### Repaso de POO

Pilares:

1. Encapsulamiento
2. Herencia
3. Polimorfismo
4. Abstraccion

**Buenas practicas** de POO:

- Poco **acoplamiento**: relacion entre modulos del sistema y su interdependencia. Si hay poca dependencia, hay mayor reusabilidad en otros sistemas
- Mucha **cohesion**: 1 modulo tiene 1 responsabilidad

**Design smells**:
Decimos que el codigo "Huele" cuando este funciona, pero tenemos una intuicion de que algo no esta bien y puede ser mejorado. Algunos smells son:
- Rigidez (Cuando un cambio genera una cascada de cambios)
- Fragilidad (Un cambio explota el codigo)
- Inmovilidad (Codigo poco rehusable)
- Viscocidad (El codigo induce a hacer malas practicas)
- Complejidad innecesaria
- Repeticion innecesaria
- Opacidad (Complejo de leer, poco intuitivo)

**Principios de diseño en POO**

- **DRY** (Dont Repeat Yourself)
- **KISS** (Keep it simple stupid)
- **YAGNI** (You Are Gonna Need It)
- **SOLID**

### SOLID

* Single responsability
* Open closed
* Liskov substitution
* Interface segregation
* Dependency inversion

## Principio de responsabilidad simple 

Una clase debe tener una y solo una razon de cambio / responsabilidad

### Cuando aplicar este principio
- Clase muy larga (+300 lineas Aprox.)
- Metodo muy largo (+40 lineas Aprox.)
- Muchas dependencias a otros objetos (+20 Aprox)
- Baja cohesion
- nombres muy genericos
- uso del antipatron [Spaghetti code](https://es.wikipedia.org/wiki/C%C3%B3digo_espagueti)

**Sobre que elementos aplicar este principio**

  - Metodos
  - Clases
  - Bibliotecas
  - Modulos
  - Sistemas

**Contras del principio**
- Genera muchas clases
- Codigo mas complicado de leer (no siempre)