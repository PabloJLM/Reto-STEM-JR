# Proyecto BALAM - Reto STEM JR 

STEM JR es un carrito robótico educativo diseñado para introducir a estudiantes en conceptos fundamentales de robótica, programación y sistemas embebidos utilizando la placa micro:bit y el entorno de programación MicroBlocks. El proyecto forma parte del **Reto STEM JR**, una categoría educativa dentro de **Proyecto BALAM – Encuentro Nacional de Robótica de Guatemala**, cuyo objetivo es fomentar el aprendizaje práctico de tecnologías STEM en estudiantes de nivel escolar.

El sistema integra control de motores mediante puente H, sensores de proximidad y una librería de funciones personalizadas que simplifican la programación del robot. Este repositorio contiene la librería principal utilizada para controlar el robot, proyectos de ejemplo y documentación técnica del hardware y software del sistema.

---

# Proyecto BALAM

**Proyecto BALAM** es el Encuentro Nacional de Robótica de Guatemala, una iniciativa que busca promover la innovación, el desarrollo tecnológico y el aprendizaje en áreas STEM mediante competencias, retos educativos y actividades formativas.

El **Reto STEM JR** está orientado a estudiantes que comienzan en el mundo de la robótica, proporcionando una plataforma accesible que permite aprender:

- fundamentos de programación
- control de motores
- uso de sensores
- lógica de navegación básica
- pensamiento computacional

STEM JR sirve como plataforma base para desarrollar estas habilidades mediante el uso de micro:bit y MicroBlocks.

---

# Objetivos del Proyecto

El proyecto STEM JR busca:

- Introducir a estudiantes a la robótica educativa utilizando hardware accesible.
- Simplificar la programación mediante bloques personalizados en MicroBlocks.
- Proporcionar una plataforma modular para experimentar con sensores y actuadores.
- Servir como base tecnológica para el **Reto STEM JR dentro de Proyecto BALAM**.
- Facilitar el desarrollo de actividades educativas en entornos STEM.

---

# Hardware

El robot utiliza una placa **micro:bit** como controlador principal del sistema. El movimiento se realiza mediante dos motores DC controlados por un puente H y sensores que permiten detectar obstáculos o condiciones del entorno.

## Componentes principales

- micro:bit
- Driver de motores tipo puente H
- 2 motores DC con caja reductora
- Sensor ultrasónico
- Sensores infrarrojos (IR)
- Sensores Sharp de distancia (pendiente de integración)
- Neopixel (pendiente de integración)
- Chasis robótico tipo carrito
- Sistema de alimentación

---

# Pinout

## Sensores Sharp

- P0
- P1
- P2

## Sensores IR

- P3
- P4

## Sensor Ultrasónico

Trigger → P14  
Echo → P13  

## Motores

Motor A  
PWM → P6  
AIN1 → P7  
AIN2 → P19  

Motor B  
PWM → P9  
BIN1 → P15  
BIN2 → P16  

## Neopixel

P8

---

# Software

La programación del sistema se realiza utilizando **MicroBlocks**, un entorno de programación basado en bloques que permite desarrollar programas para micro:bit de manera interactiva.

Para facilitar el uso del robot se desarrolló una **librería de funciones personalizadas**, que encapsula el control del hardware en bloques reutilizables.

Estas funciones permiten a los estudiantes programar el robot sin tener que interactuar directamente con los pines del microcontrolador.

---

# Funciones de Movimiento

Las funciones de movimiento controlan el desplazamiento del robot mediante el puente H y señales PWM hacia los motores.

Todas las funciones de movimiento utilizan los siguientes parámetros:

- duración (segundos)
- velocidad motor 1 (0–1023)
- velocidad motor 2 (0–1023)

Funciones disponibles:

- adelante(duración, velocidad_motor1, velocidad_motor2)
- atras(duración, velocidad_motor1, velocidad_motor2)
- izquierda(duración, velocidad_motor1, velocidad_motor2)
- derecha(duración, velocidad_motor1, velocidad_motor2)

---

# Función de Detención

apagar()

Detiene completamente el robot colocando en cero todas las señales PWM y desactivando el puente H.

---

# Funciones de Sensores

Estas funciones están implementadas como **reporter blocks** y devuelven lecturas de sensores del sistema.

Funciones disponibles:

- sensor_ultrasonico()
- sensor_ir_izquierdo()
- sensor_ir_derecho()

Estas funciones no requieren parámetros.

---

# Funciones de Diagnóstico

prueba_motores()

Realiza una secuencia automática para verificar el funcionamiento de los motores del robot.

Secuencia de prueba:

1. Adelante durante 2 segundos
2. Atrás durante 2 segundos
3. Giro a la izquierda durante 2 segundos
4. Giro a la derecha durante 2 segundos

Esta función permite validar conexiones, direcciones de giro y funcionamiento del puente H.

---

# Funciones Planificadas

Las siguientes funciones aún no han sido implementadas y están previstas para versiones futuras del sistema.

## Sensores

- lectura de sensores Sharp
- funciones de calibración de sensores

## Iluminación

- control de Neopixels

Estas funciones permitirán diferenciar y agregar toques esteticos al robot

---

# Ejemplos Incluidos en el Repositorio

El repositorio incluye proyectos de ejemplo que muestran distintas formas de controlar el robot.

Estos proyectos no forman parte de la librería principal y se incluyen únicamente como demostraciones.

Entre ellos se encuentran:

- Control del robot utilizando **OctoStudio**
- Control del robot mediante **otro micro:bit utilizando su acelerómetro**

Estos ejemplos permiten experimentar con control remoto y explorar diferentes formas de interacción con el robot.
