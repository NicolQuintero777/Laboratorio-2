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

## MODO FISICO 

<img width="500" height="400" alt="WhatsApp Image 2026-04-22 at 21 32 29" src="https://github.com/user-attachments/assets/f0b8f536-0c40-4878-a5f7-e7e2812720a5" />

<img width="700" height="400" alt="WhatsApp Image 2026-04-22 at 21 32 30" src="https://github.com/user-attachments/assets/8d6cbc09-5819-4c1d-b384-4357015276a5" />


https://github.com/user-attachments/assets/8ac13dfb-7d7f-419c-a5a4-554681d456e1






# DESARROLLAR UN JUEGO SENCILLO EN UNA OLED UTILIZANDO ARDUINO

## 1. ¿Qué es este proyecto?
Es un sistema de interfaz gráfica de usuario (GUI). El objetivo es demostrar cómo un microcontrolador puede procesar datos de entrada (teclado) y generar una respuesta visual compleja en tiempo real sobre una pantalla de tecnología OLED.

## 2. Componentes 
Arduino Uno: Actúa como el motor del juego, calculando la física del movimiento y las colisiones

Pantalla OLED SSD1306: Es el periférico de salida, tiene una resolución de 128x64 pixeles y utiliza luz propia

Protocolo I2C: Es el sistema de comunicación que usa solo 2 cables de datos (SDA en A4 y SCL en A5) para enviar toda la información visual

Puerto Serial: Funciona como el control remoto o mando del juego a través del teclado del PC

## 3. ¿Cómo funciona el código? 
Es un minijuego arcade que corre en un Arduino UNO con una pantalla OLED de 128x64 píxeles, simulado en Wokwi. El programa usa tres librerías: Wire.h para la comunicación I2C, y Adafruit_GFX.h junto con Adafruit_SSD1306.h para controlar la pantalla.

<img width="700" height="300" alt="image" src="https://github.com/user-attachments/assets/8f6184c7-0294-43f4-b6a7-a6a85f3ad741" />

Al iniciar, el programa establece las posiciones de inicio: la nave del jugador aparece cerca del centro en la parte inferior de la pantalla, y un objeto enemigo empieza a caer desde la parte superior. También inicializa el puerto serial a 115200 baudios para recibir los controles del jugador, y verifica que la pantalla OLED esté bien conectada por I2C, si no la encuentra, el programa se detiene con un mensaje de error.

Durante el juego, el jugador controla la nave escribiendo letras en el Monitor Serial: la tecla "a" mueve la nave hacia la izquierda y la tecla "d" la mueve hacia la derecha, cada pulsación desplaza la nave 8 píxeles. El código también limita el movimiento para que la nave no se salga de los bordes de la pantalla.
Al mismo tiempo, el objeto enemigo va cayendo desde arriba hacia abajo de manera continua. Si el jugador logra esquivarlo o reaccionar correctamente, el puntaje aumenta y el objeto reaparece en una nueva posición aleatoria en la parte superior, ese comportamiento aleatorio es posible gracias al randomSeed que se configuró al inicio con analogRead.
Todo esto se dibuja en tiempo real sobre la pantalla OLED  se puede ver el objeto como un punto blanco moviéndose, la nave como una pequeña línea en la parte inferior, y el marcador "Puntos:" actualizado en cada ciclo

<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/0a92344d-0867-40d9-b360-b91dc5eedbed" />


## 4. Flujo de Datos
Entrada: Carácter ASCII enviado desde el Monitor Serial.

Procesamiento: El Arduino actualiza las coordenadas matemáticas en la memoria RAM.

Salida: Envío de paquetes de datos por el bus I2C hacia la pantalla para iluminar los píxeles correspondientes.


# DESARROLLAR UN DETECTOR DE COLORES MEDIANTE EL SENSOR CNY70 Y EL USO DE ARDUINO

## 1. ¿Qué es este proyecto?
Es un Sistema de Seguridad Automatizado. Su función es monitorear un área específica y activar una respuesta inmediata cuando detecta la presencia de un cuerpo en movimiento a través de radiación infrarroja

## 2. Componentes
Arduino Uno: Es el cerebro que recibe la señal del sensor y decide cuando activar la alarma

Sensor de movimiento PIR: El componente de entrada detecta cambios en el calor del ambiente

LED Rojo: El componente de salida proporciona una señal de alerta visual instantánea

Resistencia 220: Protege al LED para que no se queme del voltaje del Arduino 

Monitor Serial: Interfaz de software donde se registra el historial de detecciones con fecha y mensaje

## 3. ¿Cómo funciona el código? 

Es un sistema de seguridad con sensor de movimiento PIR hecho en Arduino UNO y simulado en Wokwi, el circuito tiene tres componentes principales: el Arduino como cerebro del sistema, un sensor PIR conectado al pin 2 que detecta presencia humana a través del calor infrarrojo que emite el cuerpo, y un LED rojo conectado al pin 13 con una resistencia que funciona como alarma visual


Cuando el sistema arranca, primero imprime en el monitor serial un encabezado con el nombre del proyecto y avisa que el sensor está calibrando, lo cual es normal en los sensores PIR ya que necesitan unos segundos para estabilizarse antes de empezar a funcionar correctamente. Una vez calibrado, el programa entra en un ciclo que se repite indefinidamente cada medio segundo, leyendo constantemente el estado del sensor

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/8d40902a-e311-4b66-a409-a8fa5248a869" />


Si el sensor detecta movimiento, su pin de salida se pone en HIGH, el Arduino recibe esa señal, enciende el LED rojo y manda el mensaje de alerta al monitor serial avisando que hay un intruso en el área. Si por el contrario no hay ningún movimiento, el pin regresa a LOW, el LED se apaga y el monitor muestra que la zona está segura y despejada.

<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/911d16cc-e971-4604-ba44-958ca4c6e248" />

<img width="500" height="400" alt="WhatsApp Image 2026-04-15 at 14 43 22" src="https://github.com/user-attachments/assets/3662e498-9698-49c4-87d6-46f96aeb5ec0" />



Este proyecto es una aplicación real de lo que vemos en la vida cotidiana, como las luces automáticas de los pasillos o las puertas de los centros comerciales.

Aunque en un laboratorio físico usaríamos un sensor pequeño como el CNY70 (que es de corto alcance), el uso del sensor PIR en esta simulación nos permite entender cómo funcionan los Sistemas de Seguridad Perimetral, donde lo más importante es la velocidad de respuesta desde que el sensor capta el movimiento hasta que el LED se enciende


