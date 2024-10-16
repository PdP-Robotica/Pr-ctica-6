# Práctica-6

## Integrantes:
•	Luis Fernando Duarte Reséndiz
•	Mauricio Alberto Gómez Arroyo
•	Diego Brandon Guzmán Sierra
•	Bryan Hiadim Vera Hernández


## Introducción.
En este proyecto, se plantea el control de un motor a pasos mediante un Arduino, con el objetivo de generar movimientos específicos tanto hacia la derecha como hacia la izquierda. Para ello, se programó un código que envía señales de frecuencia y pulsos al controlador del motor, tomando en cuenta una resolución de 800 pulsos por revolución. El motor a pasos fue configurado para realizar cuatro vueltas a la derecha en dos segundos y dos vueltas a la izquierda en un segundo, utilizando una frecuencia de 1600 Hz en ambos sentidos. Esta implementación permite comprender de manera práctica el control de motores a pasos mediante señales PWM (modulación por ancho de pulso), fundamentales para aplicaciones de precisión en sistemas mecatrónicos.

## Instrucciones.
Se nos proporcionó una serie de instrucciones para generar movimientos en un motor a pasos utilizando su controlador. Para ello, enviaremos las señales de frecuencia y pulsos de dirección mediante un Arduino. En este caso, se nos indicó que el motor a pasos debía realizar cuatro vueltas hacia la derecha en un lapso de dos segundos y dos vueltas hacia la izquierda en un segundo.
Para comenzar, es necesario abrir la interfaz de Arduino y establecer la conexión con el microcontrolador.

![image](https://github.com/user-attachments/assets/bc657a0a-327d-4137-8024-b594074a2efa)

![image](https://github.com/user-attachments/assets/f5208f6a-3aad-40f7-9895-3d89cc6b8fd1)

A continuación, es necesario generar un código que permita controlar los parámetros previamente mencionados, considerando que el controlador tiene una resolución de 800 pulsos por revolución.
De esta manera, realizamos los cálculos correspondientes, obteniendo lo siguiente:
Frecuencia= (4 revoluciones * 800 pulsos/ revolución) / 2 Segundos= 1600 Hz.
Para la frecuencia hacia la izquierda, tenemos:
Frecuencia= (2 revoluciones * 800 pulsos/ revolución) / 1 Segundo= 1600 Hz.
Por lo tanto, en nuestro modelo se facilita el control, ya que se requiere la misma frecuencia en ambos sentidos.
Una vez realizados los cálculos, pasamos a la explicación del código obtenido, cuyo propósito es controlar la dirección y la frecuencia de rotación del motor a pasos.


