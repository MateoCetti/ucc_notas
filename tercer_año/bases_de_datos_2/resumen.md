# Bases de datos II

## Notas

**Profe**:
* Mariano Alberto Garcia Mattio

## Repaso

* SGBD
* Diseños de DB --> Modelados conceptuales
* Modelos conceptuales --> ER
* Modelos mas avanzados --> Modelo relacional

magm3333@gmail.com

data en el mail a mandar:

![](./img/email.png)

## Docker

Crear contenedores **ligeros** y **portables** que puedan ejecutarse en maquina **independientemente** del **sistema operativo** que la maquina tenga por debajo **facilitando** sus **desplieges**.

Ventajas:
* **Desarrolladores** (se puede mandar todo el proyecto a desplegar o testear con la certeza de que va a andar igual que en el environment del desarrollador)
* **Testers**
* **Sysadmin**
* **Menos pesado** que una VM
* **Open source**
* **Prototipado** (servicios, microservicios, redes, interacciones complejas y heterogeneas)

![](./img/docker_vs_vm.png)

**Imagen**

Es como una clase, una plantilla. Luego generamos un contenedor a partir de una imanen, este seria como la instancia o objeto.

Volumen: Espacio fisico que almacena los datos de cada contenedor. Se crean en el host real y se asocian a cada contenedor creado. (Locacion por defecto: /var/lib/docker/volumes).

Se pueden crear volumenes con nombres familiares para facilitar la gestion

docker run: prende el contenedor y ejecuta el comando, luego lo apaga.

docker exec: ejecuta un comando en un contenedor ya activado.

## Federacion de mysql

En dos servicios de MySQL, uno de ellos puede funcionar como cliente del otro reexponiendo rescources como por ejemplo tablas.

## Eventos

Objetos que contienen codigo que se pueden ejecutar de forma scheduled.

## Triggers

Es un objeto de la DB q esta asociado a una tabla y se activa cuando se ejecuta una accion sobre esa tabla (insert, update o delete).

## Funciones

Porcion de codigo que recibe parametros y devuelve elementos.

## Procedimientos almacenados

Ventajas:
* Ahorran ancho de banda
* Centralizan logica de negocios
* Aumentan la performance y respuesta general

![](./img/proc_alm.png)