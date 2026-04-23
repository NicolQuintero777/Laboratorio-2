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


## DESARROLLAR UN JUEGO SENCILLO EN UNA OLED UTILIZANDO ARDUINO

## 1. ¿Qué es este proyecto?
Es un sistema de interfaz gráfica de usuario (GUI). El objetivo es demostrar cómo un microcontrolador puede procesar datos de entrada (teclado) y generar una respuesta visual compleja en tiempo real sobre una pantalla de tecnología OLED.

## 2. Componentes 
Arduino Uno: Actúa como el motor del juego, calculando la física del movimiento y las colisiones

Pantalla OLED SSD1306: Es el periférico de salida, tiene una resolución de 128x64 pixeles y utiliza luz propia

Protocolo I2C: Es el sistema de comunicación que usa solo 2 cables de datos (SDA en A4 y SCL en A5) para enviar toda la información visual

Puerto Serial: Funciona como el control remoto o mando del juego a través del teclado del PC

## 3. ¿Cómo funciona el código? (Lógica)
El código utiliza un ciclo de renderizado similar al de las consolas de videojuegos profesionales:
Inicialización (setup): Configura la comunicación serial a alta velocidad (115200 baudios) y "despierta" la pantalla. Si la pantalla no responde, el código se detiene para evitar errores.
El "Oído" del Jugador (Serial.available): El programa revisa si presionaste una tecla. Si envías una 'a', resta posición al eje X (izquierda); si envías una 'd', suma posición (derecha).
Física del Juego: El objeto que cae aumenta su posición en el eje Y constantemente. Cuando llega al final de la pantalla (64 píxeles), se reinicia arriba en una posición aleatoria (random) y te suma un punto.
Refresco de Pantalla: En cada vuelta del ciclo, el Arduino hace tres cosas:
Borra todo lo que había (clearDisplay).
Dibuja las nuevas posiciones de la nave y el objeto.

Muestra el resultado final (display).

## 4. Flujo de Datos
Entrada: Carácter ASCII enviado desde el Monitor Serial.

Procesamiento: El Arduino actualiza las coordenadas matemáticas en la memoria RAM.

Salida: Envío de paquetes de datos por el bus I2C hacia la pantalla para iluminar los píxeles correspondientes.




