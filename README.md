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


# A0 — PREPARACIÓN DEL ENTORNO

**Actividad:** M12UF1A0  
**Curso:** SMX2  
**Módulo:** Arduino


# 2. Investigación sobre Arduino

## 2.1. ¿Qué es Arduino?

Es una plataforma de creación de código abierto que permite crear diferentes tipos de microordenadores de una sola placa base. Está basada en hardware y software libre y fácil de usar para los creadores y desarrolladores.

Hay muchos dispositivos que se pueden conectar a Arduino, incluidos sensores, luces, actuadores, pantallas, altavoces y otros componentes.

## 2.2. ¿Cuáles son sus características más importantes?

Las características más importantes de Arduino son:

- **Fácil de programar:** Arduino utiliza un entorno de programación llamado Arduino IDE, que funciona en Windows, macOS y Linux.

- **Hardware y software libre:** Sus diseños y herramientas son de código abierto, lo que permite estudiar, modificar y compartir proyectos.

- **Microcontrolador:** Es el componente principal de la placa y se encarga de ejecutar las instrucciones del programa. El tipo de microcontrolador depende del modelo de Arduino.

- **Pines de entrada y salida:** Permiten conectar sensores, botones, luces y motores. Dispone de pines digitales y entradas analógicas.

- **Alimentación:** Algunas placas, como Arduino UNO R3, pueden funcionar mediante USB de 5 V o una fuente externa recomendada de 7 a 12 V.

- **Versatilidad:** Se puede utilizar para crear muchos proyectos diferentes, como robots, alarmas o sistemas de iluminación automática.

## 2.3. ¿Cuál es el origen de Arduino?

Arduino nació en el año 2005 en el Instituto de Diseño Interactivo de Ivrea, en Italia.

Este proyecto surgió porque los estudiantes necesitaban una herramienta económica y fácil de utilizar para aprender electrónica y programación en las aulas.

Con el tiempo, Arduino se hizo muy popular y empezó a utilizarse en escuelas, universidades y proyectos de robótica.

## 2.4. ¿Qué modelos de Arduino hay?

Los modelos más conocidos de Arduino son Arduino UNO R3, Arduino Mega 2560 y Arduino Leonardo.

Cada modelo tiene diferentes características, como el número de pines, la memoria y el microcontrolador que utiliza.

### Tabla comparativa de modelos Arduino

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

Gracias a los **sensores**, puede recibir información del entorno, como la temperatura, la luz o el movimiento.

Después, el **microcontrolador** procesa esa información y, mediante los **actuadores**, puede realizar acciones, como encender una luz o mover un motor.

Arduino se utiliza en diferentes ámbitos:

- **Proyectos personales:** creación de robots, luces decorativas y sistemas de automatización.

- **Educación y prototipos:** permite aprender programación y electrónica y probar nuevas ideas.

- **Industria y negocios:** se utiliza para desarrollar prototipos de sistemas de control, monitorizar procesos y recoger datos mediante sensores.

**Ejemplo:** Arduino puede detectar cuando una habitación está oscura y encender automáticamente una luz.

## 2.6. ¿Qué lenguaje utiliza Arduino?

Arduino utiliza un lenguaje de programación basado en **C/C++**, que es relativamente fácil de aprender gracias a sus funciones y bibliotecas.

Este lenguaje permite escribir instrucciones para controlar sensores, luces, motores y otros componentes electrónicos.

## 2.7. ¿Qué es Arduino IDE?

Arduino IDE (Entorno de Desarrollo Integrado) es un software gratuito y de código abierto que permite escribir, compilar y cargar programas en las placas Arduino.

También ofrece herramientas para detectar errores y depurar programas compatibles.

Está compuesto por diferentes herramientas:

- **Editor de código:** permite escribir y modificar el código fuente.

- **Compilador:** convierte el código escrito en C/C++ en instrucciones que puede ejecutar el microcontrolador.

- **Herramienta de carga:** permite enviar el programa compilado a la placa Arduino mediante USB.

- **Depurador:** ayuda a detectar y corregir errores durante la ejecución, en placas compatibles.

Arduino IDE es compatible con Windows, macOS y Linux.

---

# 3. Instalación de Arduino IDE

## 3.1. Descarga de Arduino IDE

Para instalar Arduino IDE debemos acceder a la página oficial:

**Enlace:** https://www.arduino.cc/en/software

Desde esta página podemos descargar la versión correspondiente a nuestro sistema operativo.

## 3.2. Instalación en el equipo

Según el enunciado, Arduino IDE debe instalarse en la partición **D:** del equipo del aula.

### Procedimiento

1. Accedemos a la página oficial de Arduino.
2. Seleccionamos la versión para Windows.
3. Descargamos el instalador.
4. Ejecutamos el archivo descargado.
5. Seleccionamos la partición D: como destino de instalación, cuando el instalador lo permita.
6. Completamos la instalación.
7. Abrimos Arduino IDE para comprobar que funciona correctamente.

**Versión utilizada durante las prácticas:** Arduino IDE 2.3.11.

### Evidencias de instalación

**Captura 01 — Instalación de Arduino IDE**

*Pendiente de insertar la captura.*

**Captura 02 — Arduino IDE abierto**

*Pendiente de insertar la captura.*

---

# 4. Puesta a punto de Arduino IDE

## 4.1. Comprobación del controlador CH343

El controlador CH343 permite la comunicación USB serie con la placa ESP32-S3 WROOM descrita en el manual de referencia.

### Procedimiento

1. Conectamos la placa al ordenador mediante el cable USB.
2. Abrimos el Administrador de dispositivos de Windows.
3. Buscamos el apartado **Puertos (COM y LPT)**.
4. Comprobamos si aparece el dispositivo USB serie correspondiente.
5. Si el controlador no está instalado correctamente, seguimos el procedimiento del manual Freenove para instalarlo.

**Referencia:** Manual Freenove, apartado CH343.

### Evidencia

**Captura 03 — Comprobación del controlador USB**

*Pendiente de insertar la captura.*

## 4.2. Configuración del entorno de Arduino

Para utilizar la placa ESP32 debemos instalar el soporte correspondiente en Arduino IDE.

### Procedimiento

1. Abrimos Arduino IDE.
2. Seleccionamos `File > Preferences`.
3. Buscamos la opción `Additional Boards Manager URLs`.
4. Añadimos la URL del paquete ESP32:

`https://espressif.github.io/arduino-esp32/package_esp32_index.json`

5. Guardamos los cambios.
6. Abrimos `Boards Manager`.
7. Buscamos `esp32`.
8. Instalamos `esp32 by Espressif Systems`.
9. Comprobamos que aparece como instalado.

### Evidencia

**Captura 04 — Instalación del paquete ESP32**

*Pendiente de insertar la captura.*

## 4.3. Selección de la placa ESP32

Después de instalar el paquete, debemos seleccionar el modelo de placa que utilizamos.

### Procedimiento

1. Conectamos la placa al ordenador.
2. Abrimos Arduino IDE.
3. Entramos en `Tools > Board`.
4. Seleccionamos el modelo correspondiente.

**Placa utilizada en nuestro montaje:** Freenove ESP32-WROVER.

**Modelo seleccionado:** `ESP32 Wrover Module`.

### Evidencia

**Captura 05 — Selección de ESP32 Wrover Module**

*Pendiente de insertar la captura.*

## 4.4. Comprobación del puerto USB

Para comprobar que Arduino IDE reconoce la placa:

### Procedimiento

1. Conectamos el ESP32 al ordenador con el cable USB.
2. Entramos en `Tools > Port`.
3. Seleccionamos el puerto COM correspondiente.
4. Comprobamos que Arduino IDE reconoce la placa.

Durante nuestras pruebas utilizamos el puerto **COM3**.

### Evidencia

**Captura 06 — Selección del puerto COM3**

*Pendiente de insertar la captura.*

## 4.5. Verificación del funcionamiento

Después de configurar el entorno, comprobamos que podemos compilar y cargar un programa en el ESP32.

### Procedimiento

1. Abrimos un programa de prueba en Arduino IDE.
2. Seleccionamos la placa y el puerto COM.
3. Pulsamos `Verify` para comprobar el código.
4. Pulsamos `Upload` para enviar el programa a la placa.
5. Comprobamos que la carga finaliza correctamente.

### Evidencia

**Captura 07 — Compilación y subida correcta del programa**

*Pendiente de insertar la captura.*

---

**Fin de la actividad M12UF1A0.**

[Volver al índice principal](../README.md)



---
# A1
## Blink + Semáforo

### 1.1. Introducción

## 1.2. Capítulo 0 — Blink

### Objetivo

### Conceptos fundamentales


### Procedimiento


### Evidencias


## 1.3. Práctica 1 — LED externo

### Objetivo


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
