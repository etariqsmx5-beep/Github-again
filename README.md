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
## Preparación del entorno

### 0.1. Objetivo

Preparar el ordenador y el entorno de desarrollo para poder programar la placa ESP32.

### 0.2. Materiales y herramientas

| Elemento | Función |
|---|---|
| ESP32-WROVER | Ejecutar el programa |
| Arduino IDE | Escribir y cargar código |
| Cable USB | Conectar el ESP32 al ordenador |
| Driver USB | Permitir la comunicación serie cuando sea necesario |
| Espressif Board Package | Añadir soporte para programar placas ESP32 |

### 0.3. Instalación de Arduino IDE

**Procedimiento:**

1. Acceder a la página oficial de Arduino.
2. Descargar Arduino IDE para Windows.
3. Ejecutar el instalador.
4. Completar la instalación.
5. Abrir Arduino IDE.

**Página oficial:** https://www.arduino.cc/en/software

### 0.4. Instalación del soporte ESP32

**Procedimiento:**

1. Abrir Arduino IDE.
2. Acceder a `File > Preferences`.
3. Añadir la URL del gestor de placas ESP32.
4. Abrir `Boards Manager`.
5. Buscar `esp32`.
6. Instalar `esp32 by Espressif Systems`.

### 0.5. Configuración de la placa

**Placa utilizada:** ESP32 Wrover Module.

**Procedimiento:**

1. Conectar el ESP32 mediante USB.
2. Acceder a `Tools > Board`.
3. Seleccionar `ESP32 Wrover Module`.
4. Acceder a `Tools > Port`.
5. Seleccionar el puerto COM correspondiente.

### 0.6. Comprobación

Para comprobar el funcionamiento se puede utilizar el ejemplo Blink.

**Resultado esperado:** el ESP32 recibe correctamente el código y ejecuta la secuencia programada.

### 0.7. Evidencias

Pendiente de añadir:

- Captura de Arduino IDE instalado.
- Captura del gestor de placas.
- Captura de la configuración de ESP32.
- Captura de compilación y carga.

### 0.8. Qué he aprendido

He aprendido a instalar Arduino IDE, configurar el soporte ESP32, identificar el modelo de mi placa y seleccionar el puerto de comunicación.

[Volver al índice](#2-índice-general)

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
