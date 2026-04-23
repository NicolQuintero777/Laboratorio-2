## Laboratorio-2

# SISTEMA DE ILUMINACION Y MONITOREO DE TEMPERATURA MEDIANTE CHATBOT

## 1. ¿Qué es este proyecto?
Es un sistema de Internet de las Cosas y domótica básica. Su objetivo es permitir que un usuario interactúe con el hardware de su hogar en este caso leds y sensores a través de un lenguaje, simulando una conversación con un asistente inteligente.

## 2. Los componentenes
 AEDUINO UNO: Es el cerebro que procesa las ordenes y toma las decisiones.
 
 SENSOR DHT22: Es el sentido del tacto, mide la temperatura y humedad del ambiente y la convierte    en datos originales
 
 LEDS: Representa el sistema de iluminacion de una casa o industria.
 
 RESISTENCIAS: Protegen los LEDS para que no se quemen por el exceso de corriente.
 
 COMUNICACION SERIAL: Es el puente o canal por donde viajan los mensajes de texto entre el pc y el arduino.
 
## 3. ¿Cómo funciona el código? 
El código se divide en tres partes fundamentales:
Configuración : Aquí el Arduino "despierta", prepara sus pines como salidas de energía y activa el sensor. También envía el saludo inicial: "Chatbot de Miguel y Nicolle Activo".


Escucha Activa: El Arduino está constantemente preguntando: "¿Me escribieron algo?". Si detecta texto en el monitor serial, lo guarda en una variable llamada mensajeRecibido.


Procesamiento y Acción: Es el motor de decisiones.Si el texto es "luz encendida", envía energía a los pines 12 y 13.Si es "temp", detiene lo que está haciendo, le pide el dato al sensor DHT22 y nos lo devuelve escrito en pantalla.

<img width="900" height="400" alt="image" src="https://github.com/user-attachments/assets/0938f308-b375-4e79-b583-4004c6960bd7" />


## 4. Flujo de Datos
Entrada: El usuario escribe un comando en la PC.

Procesamiento: El Arduino recibe el mensaje, lo limpia y lo compara con sus comandos guardados

Salida: El sistema responde de dos formas: física (prendiendo LEDs) o informativa (enviando texto de vuelta con la temperatura).

## LUZ ENCENDIDA
<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/27990c0c-02f8-4605-a5e3-1214f06bfa82" />

## LUZ APAGADA
<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/47611505-f372-4018-a059-0e4849ae92aa" />

## TEMPERATURA
<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/9e0cd59a-fe30-42d7-b8bd-ab9754a3e0f3" />






