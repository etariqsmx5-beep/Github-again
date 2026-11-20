# ARDUINO & ESP32
## Cuaderno de prácticas y documentación técnica

**Curso:** SMX2  
**Módulo:** Arduino  
**Placa utilizada:** Freenove ESP32-WROVER  
**Entorno:** Arduino IDE 2.3.11  
**Lenguaje:** C/C++

---

# 1. Presentación

Este repositorio funciona como un cuaderno digital donde documento las actividades realizadas durante el módulo de Arduino.

El objetivo es aprender a utilizar microcontroladores ESP32, comprender las conexiones electrónicas, desarrollar programas y resolver incidencias técnicas.

En cada actividad se documentarán:

- Los objetivos de aprendizaje.
- Los componentes utilizados.
- Los conceptos teóricos.
- El procedimiento paso a paso.
- El código de programación.
- Las fotografías y capturas de pantalla.
- Los errores encontrados y sus soluciones.
- Los resultados y conclusiones.

---

# 2. Índice general

## Actividades

### [A0 — Preparación del entorno](#a0)

### [A1 — Blink + Semáforo](#a1)

### [A2 — LED + Button](#a2)

### [A3 — LED RGB](#a3)

### [A4 — LED Bar](#a4)

### [A5 — Serial IO](#a5)

### [A6 — WiFi](#a6)

## Apuntes y documentación

### [Conceptos importantes](#conceptos-importantes)

### [Registro de incidencias](#registro-de-incidencias)

### [Bibliografía y recursos](#bibliografia)

---

# A0
# 2. Investigación sobre Arduino

## 2.1. ¿Qué es Arduino?

Es una plataforma de creación de código abierto que permite crear
diferentes tipos de microordenadores de una sola placa base. Está basada
en hardware y software libre y fácil de usar para los creadores y
desarrolladores. Hay muchos dispositivos que se pueden conectar a
Arduino incluye sensores, luces, actuadores, plantillas y altavoces y otros
más.

## 2.2. ¿Cuáles son sus características más importantes?

Las características más importantes de Arduino son:

- **Fácil de programar:** Arduino utiliza un entorno de programación llamado Arduino IDE, que funciona en Windows, macOS y Linux.
- **Hardware y software libre:** Sus diseños y herramientas son de código abierto, lo que permite estudiar, modificar y compartir proyectos.
- **Microcontrolador:** Es el componente principal de la placa y se encarga de ejecutar las instrucciones del programa. El tipo de microcontrolador depende del modelo de Arduino.
- **Pines de entrada y salida:** Permiten conectar sensores, botones, luces y motores. Dispone de pines digitales y entradas analógicas.
- **Alimentación:** Algunas placas, como Arduino UNO R3, pueden funcionar mediante USB de 5 V o una fuente externa recomendada de 7 a 12 V.
- **Versatilidad:** Se puede utilizar para crear muchos proyectos diferentes, como robots, alarmas o sistemas de iluminación automática.

## 2.3. Origen de Arduino

#. ¿Cuál es el origen de Arduino?

Arduino nació en el año 2005 en el Instituto de Diseño Interactivo de Ivrea, en Italia.

Este proyecto surgió porque los estudiantes necesitaban una herramienta económica y fácil de utilizar para aprender electrónica y programación en las aulas.

Con el tiempo, Arduino se hizo muy popular y empezó a utilizarse en escuelas, universidades y proyectos de robótica.

## 2.4. Modelos de Arduino

## 2.4. ¿Qué modelos de Arduino hay?

Los modelos más conocidos de Arduino son Arduino UNO R3, Arduino Mega 2560 y Arduino Leonardo. Cada modelo tiene diferentes características, como el número de pines, la memoria y el microcontrolador que utiliza.

| Características | Arduino UNO R3 | Arduino Mega 2560 | Arduino Leonardo |
|---|---|---|---|
| Microcontrolador | ATmega328P | ATmega2560 | ATmega32U4 |
| Voltaje de funcionamiento | 5 V | 5 V | 5 V |
| Voltaje de entrada recomendado | 7–12 V | 7–12 V | 7–12 V |
| Pines digitales | 14 | 54 | 20 |
| Entradas analógicas | 6 | 16 | 12 |
| Memoria Flash | 32 KB | 256 KB | 32 KB |
| Memoria SRAM | 2 KB | 8 KB | 2,5 KB |
| Reloj | 16 MHz | 16 MHz | 16 MHz |


## 2.5. ¿Para qué sirve Arduino?

Arduino sirve para crear proyectos electrónicos y controlar diferentes dispositivos mediante programación.

Gracias a los **sensores**, puede recibir información del entorno, como la temperatura, la luz o el movimiento. Después, el **microcontrolador** procesa esa información y, mediante los **actuadores**, puede realizar acciones, como encender una luz o mover un motor.

Arduino se utiliza en diferentes ámbitos:

- **Proyectos personales:** creación de robots, luces decorativas y sistemas de automatización.
- **Educación y prototipos:** permite aprender programación y electrónica y probar nuevas ideas.
- **Industria y negocios:** se utiliza para desarrollar prototipos de sistemas de control, monitorizar procesos y recoger datos mediante sensores.

**Ejemplo:** Arduino puede detectar cuando una habitación está oscura y encender automáticamente una luz.

## 2.6. ¿Qué lenguaje utiliza Arduino?

Arduino utiliza un lenguaje de programación basado en **C/C++**, que es relativamente fácil de aprender gracias a sus funciones y bibliotecas.

Este lenguaje permite escribir instrucciones para controlar sensores, luces, motores y otros componentes electrónicos.

## 2.7. ¿Qué es Arduino IDE?

Arduino IDE (Entorno de Desarrollo Integrado) es un software gratuito y de código abierto que permite escribir, compilar y cargar programas en las placas Arduino. También ofrece herramientas para detectar errores y depurar programas compatibles.

Está compuesto por diferentes herramientas:

- **Editor de código:** permite escribir y modificar el código fuente.
- **Compilador:** convierte el código escrito en C/C++ en instrucciones que puede ejecutar el microcontrolador.
- **Herramienta de carga:** permite enviar el programa compilado a la placa Arduino mediante USB.
- **Depurador:** ayuda a detectar y corregir errores durante la ejecución, en placas compatibles.

Arduino IDE es compatible con Windows, macOS y Linux.
---
# A1
## Blink + Semáforo

### 1.1. Introducción

En esta actividad se trabaja con las salidas digitales de la placa ESP32 para controlar el encendido y apagado de diferentes LED.

La actividad se divide en tres partes:

1. Capítulo 0 — Blink.
2. Práctica 1 — LED externo.
3. Práctica 2 — Semáforo.

---

## 1.2. Capítulo 0 — Blink

### Objetivo

Comprender cómo funciona el parpadeo de un LED mediante programación.

### Conceptos fundamentales

**`void setup()`**

Es una función que se ejecuta una sola vez cuando arranca el ESP32.

Se utiliza para configurar los pines y preparar el programa.

**`void loop()`**

Es una función que se ejecuta continuamente mientras el ESP32 está funcionando.

**`pinMode()`**

Permite configurar un pin como entrada o salida.

**`digitalWrite()`**

Permite cambiar el estado de un pin digital.

- `HIGH`: nivel lógico alto.
- `LOW`: nivel lógico bajo.

**`delay(1000)`**

Detiene la ejecución durante 1000 milisegundos, equivalentes a un segundo.

### Procedimiento

1. Abrir el ejemplo Blink.
2. Identificar el pin del LED utilizado.
3. Revisar las funciones del programa.
4. Compilar el código.
5. Cargarlo en el ESP32.
6. Comprobar el parpadeo.

### Evidencias

Pendiente de añadir las capturas y fotografías correspondientes.

---

## 1.3. Práctica 1 — LED externo

### Objetivo

Aprender a conectar y controlar un LED externo utilizando una protoboard, una resistencia y un pin GPIO del ESP32.

### Materiales

- Placa ESP32.
- GPIO Extension Board.
- Protoboard.
- LED.
- Resistencia de 220 Ω.
- Cables jumper.

### Conceptos

**GPIO:** pin de entrada o salida que permite controlar dispositivos electrónicos.

**GND:** referencia de 0 voltios que permite cerrar el circuito eléctrico.

**Resistencia:** componente que limita la corriente para proteger el LED.

**Protoboard:** placa que permite realizar conexiones eléctricas sin necesidad de soldar.

### Procedimiento

1. Desconectar el ESP32 de la alimentación.
2. Identificar las patas del LED.
3. Introducir el LED en la protoboard.
4. Colocar la resistencia de 220 Ω.
5. Conectar el pin GPIO correspondiente.
6. Conectar GND.
7. Revisar las conexiones.
8. Conectar el USB y cargar el programa Blink.
9. Comprobar el funcionamiento.

### Evidencias

Pendiente de añadir el esquema, fotografías y resultados.

---

## 1.4. Práctica 2 — Semáforo

### Objetivo

Construir un semáforo utilizando tres LED que se enciendan de forma secuencial, sin encenderse simultáneamente.

### Materiales

| Componente | Cantidad |
|---|---|
| ESP32-WROVER | 1 |
| GPIO Extension Board | 1 |
| Protoboard | 1 |
| LED rojo | 1 |
| LED verde | 1 |
| LED azul (prueba provisional) | 1 |
| Resistencias de 220 Ω | 3 |
| Cables jumper | Según las conexiones |

**Nota:** Para la entrega definitiva, el LED azul debe sustituirse por uno amarillo, tal como indica el enunciado.

### 1.4.1. Conexiones del circuito

| Conexión | Rojo | Azul | Verde |
|---|---|---|---|
| Pata larga (+) | J40 | J45 | J50 |
| Pata corta (−) | J41 | J46 | J51 |
| Resistencia de 220 Ω | F40–F43 | F45–F48 | F50–F53 |
| GPIO — extremo protoboard | G43 | G48 | G53 |
| GPIO — extremo ESP32 | GPIO2 | GPIO13 | GPIO14 |
| GND — extremo protoboard | G41 | G46 | G51 |
| GND — extremo ESP32 | GND | GND | GND |

Estas son las conexiones finales planificadas y comprobadas mediante el funcionamiento del montaje.

### 1.4.2. Funcionamiento del semáforo

El programa utiliza tres salidas digitales para controlar cada LED.

| Orden | LED | GPIO | Duración |
|---|---|---|---|
| 1 | Rojo | GPIO2 | 3 segundos |
| 2 | Azul | GPIO13 | 3 segundos |
| 3 | Verde | GPIO14 | 1 segundo |

Cuando termina la secuencia, el programa vuelve a comenzar automáticamente.

### 1.4.3. Código Arduino

El programa utiliza tres constantes:

- `LED_ROJO = 2`
- `LED_AZUL = 13`
- `LED_VERDE = 14`

En `setup()` se configuran los tres pines como salidas.

En `loop()` se enciende cada LED durante el tiempo establecido y se apagan los demás para evitar que funcionen simultáneamente.

**Archivo de código:** Pendiente de subir `Semaforo.ino`.

### 1.4.4. Compilación y carga

**Procedimiento:**

1. Abrir Arduino IDE.
2. Escribir el programa.
3. Seleccionar `ESP32 Wrover Module`.
4. Seleccionar el puerto COM correspondiente.
5. Pulsar `Verify`.
6. Comprobar que no existen errores.
7. Pulsar `Upload`.
8. Esperar a que finalice la transferencia.
9. Observar el funcionamiento de los LED.

### 1.4.5. Resultado

La placa ESP32 ejecuta correctamente el programa y los tres LED utilizados en la prueba se encienden de forma secuencial.

**Estado:** Programación y montaje provisional comprobados.

### 1.4.6. Evidencias de la práctica

Pendiente de adjuntar:

- Fotografía del circuito.
- Captura del código.
- Captura de compilación correcta.
- Captura de subida correcta.
- Diagrama de Draw.io.
- Vídeo personal del funcionamiento.

### 1.4.7. Incidencias encontradas

**Incidencia 1 — Selección incorrecta de placa**

Inicialmente se utilizó la configuración ESP32S3 Dev Module, pero la placa física correspondía a ESP32-WROVER.

**Solución:** seleccionar ESP32 Wrover Module en Arduino IDE.

**Incidencia 2 — Error de compilación**

El programa mostraba el error `LED_AZUL was not declared in this scope`.

**Solución:** corregir el identificador utilizado en el código para que coincidiera con el definido al principio del programa.

**Incidencia 3 — LED sin funcionamiento**

Se revisaron las conexiones de la protoboard, las filas eléctricas, los cables GPIO y las conexiones GND.

**Solución:** corregir las posiciones de los cables y comprobar el funcionamiento de los tres LED.

### 1.4.8. Conclusión

Con esta práctica he aprendido a conectar varios LED a un ESP32, utilizar pines GPIO diferentes y crear una secuencia automática mediante programación.

También he comprendido mejor cómo se organizan las conexiones internas de la protoboard y cómo detectar errores eléctricos y de programación.

[Volver al índice](#2-índice-general)

---

# A2
## LED + Button

**Estado:** Pendiente de realizar.

### Objetivo

Aprender a utilizar un pulsador como entrada digital para controlar un LED.

### Apartados del cuaderno

- Materiales.
- Conceptos teóricos.
- Montaje del circuito.
- Código Arduino.
- Pruebas.
- Incidencias.
- Evidencias.
- Conclusiones.

[Volver al índice](#2-índice-general)

---

# A3
## LED RGB

**Estado:** Pendiente de realizar.

### Objetivo

Aprender a controlar un LED RGB y generar diferentes colores combinando sus componentes.

### Apartados del cuaderno

- Introducción.
- Materiales.
- Conexiones.
- Código.
- Resultados.
- Evidencias.
- Conclusión.

[Volver al índice](#2-índice-general)

---

# A4
## LED Bar

**Estado:** Pendiente de realizar.

### Objetivo

Aprender a controlar una barra de LED mediante distintas secuencias de encendido.

### Apartados del cuaderno

- Introducción.
- Esquema.
- Conexiones GPIO.
- Código.
- Pruebas.
- Evidencias.
- Conclusión.

[Volver al índice](#2-índice-general)

---

# A5
## Serial IO

**Estado:** Pendiente de realizar.

### Objetivo

Estudiar la comunicación serie entre el microcontrolador y el ordenador.

### Apartados del cuaderno

- Introducción.
- Comunicación serie.
- Monitor serie.
- Código.
- Pruebas.
- Errores y soluciones.
- Conclusiones.

[Volver al índice](#2-índice-general)

---

# A6
## WiFi

**Estado:** Pendiente de realizar.

### Objetivo

Aprender a utilizar las capacidades de conectividad inalámbrica del ESP32.

### Apartados del cuaderno

- Introducción.
- Conceptos de WiFi.
- Configuración.
- Código.
- Pruebas de conexión.
- Evidencias.
- Conclusiones.

[Volver al índice](#2-índice-general)

---

# Conceptos importantes

## Glosario de Arduino

| Concepto | Explicación sencilla |
|---|---|
| ESP32 | Microcontrolador que ejecuta programas |
| Arduino IDE | Programa utilizado para escribir y subir código |
| Sketch | Nombre que recibe un programa de Arduino |
| GPIO | Pin de entrada o salida |
| GND | Referencia eléctrica de 0 voltios |
| Protoboard | Placa para realizar conexiones sin soldadura |
| LED | Componente que emite luz |
| Resistencia | Limita el paso de corriente |
| HIGH | Nivel lógico alto |
| LOW | Nivel lógico bajo |
| INPUT | Configuración de un pin como entrada |
| OUTPUT | Configuración de un pin como salida |
| Verify | Compila y comprueba el código |
| Upload | Transfiere el programa al ESP32 |
| COM | Puerto de comunicación serie en Windows |

---

# Registro de incidencias

Este apartado permite recopilar los errores encontrados durante las prácticas y sus soluciones.

| Incidencia | Causa o diagnóstico | Solución |
|---|---|---|
| Error de compilación | Nombre de variable incorrecto | Corregir el identificador |
| Error de depuración USB-JTAG | Se intentó iniciar el depurador sin la conexión adecuada | Utilizar Upload para cargar normalmente el programa |
| LED no enciende | Posible conexión incorrecta | Revisar GPIO, resistencia y GND |
| Selección incorrecta de placa | Modelo configurado distinto del físico | Seleccionar ESP32 Wrover Module |
| Puerto serie no disponible | Puerto incorrecto o problema de conexión USB | Comprobar el puerto y el cable |

---

# Bibliografia

## Documentación oficial

- [Arduino — Sitio oficial](https://www.arduino.cc/)
- [Arduino — Referencia del lenguaje](https://www.arduino.cc/reference/en/)
- [Espressif — Documentación](https://docs.espressif.com/)
- [Freenove — Sitio oficial](https://www.freenove.com/)
- [Draw.io — Editor de diagramas](https://app.diagrams.net/)

## Documentación del repositorio

[Investigación sobre Arduino](Arduino.md)

---

**Fin del cuaderno de prácticas — Arduino & ESP32**

*Documento en desarrollo. Se actualizará con nuevas actividades, capturas y conocimientos adquiridos durante el curso.*
