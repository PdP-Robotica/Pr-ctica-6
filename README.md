# Práctica-6

## Integrantes:
•	Luis Fernando Duarte Reséndiz.

•	Mauricio Alberto Gómez Arroyo.

•	Diego Brandon Guzmán Sierra.

•	Bryan Hiadim Vera Hernández.



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

```plaintext

// Definir el pin para el LED y el pin PWM
const int ledPin = 13;      // Pin para cambio de jiro
const int pwmPin = 9;       // Pin para la señal PWM (Arduino Uno usa el Timer 1 en este pin)
const int pwmFreq = 1600;   // Frecuencia PWM en Hz
int i;

void setup() {
  pinMode(ledPin, OUTPUT);  // Configurar el pin del LED como salida
  pinMode(pwmPin, OUTPUT);  // Configurar el pin PWM como salida

}
void loop() {
  // Giro derecha
  digitalWrite(ledPin, LOW);
  // inicio pwm
  for(i=0;i<800;i++){
  digitalWrite(pwmPin, HIGH);
  delayMicroseconds(160);

  digitalWrite(pwmPin, LOW);
  delayMicroseconds(1000-160);

  digitalWrite(pwmPin, HIGH);
  delayMicroseconds(160);

  digitalWrite(pwmPin, LOW);
  delayMicroseconds(1000-160);
  digitalWrite(pwmPin, HIGH);
  delayMicroseconds(160);

  digitalWrite(pwmPin, LOW);
  delayMicroseconds(1000-160);

  digitalWrite(pwmPin, HIGH);
  delayMicroseconds(160);

  digitalWrite(pwmPin, LOW);
  delayMicroseconds(1000-160);
  }
  delay(1000);

  for(i=0;i<800;i++){
  // Giro Izquierda
  digitalWrite(ledPin, HIGH);

  digitalWrite(pwmPin, HIGH);
  delayMicroseconds(160);

  digitalWrite(pwmPin, LOW);
  delayMicroseconds(1000-160);
  
  digitalWrite(pwmPin, HIGH);
  delayMicroseconds(160);

  digitalWrite(pwmPin, LOW);
  delayMicroseconds(1000-160);
  }
  delay(1000);
}


```
Explicación del código:
1.	Definición de los pines:
   
- ledPin es el pin 13, usado para indicar el cambio de giro (a través de encender o apagar un LED).
-	pwmPin es el pin 9, utilizado para generar la señal PWM (modulación por ancho de pulso) que controla la velocidad y el giro del motor.
  
2.	Configuración inicial:
- En la función setup(), los pines ledPin y pwmPin se configuran como salidas para controlar las señales de dirección y frecuencia.
  
3.	Ciclo principal (loop()):
   
- Giro hacia la derecha: Se envía una señal baja en ledPin para indicar el giro hacia la derecha. Luego, se genera la señal PWM con 800 pulsos, lo que corresponde a una revolución del motor. La frecuencia se ajusta usando el delayMicroseconds().
  
- Pausa: Después de cada giro, se introduce un retardo de 1 segundo (delay(1000)).
  
- Giro hacia la izquierda: Se envía una señal alta en ledPin para indicar el giro hacia la izquierda, repitiendo el proceso de generar 800 pulsos.
En ambos giros, se usa la misma frecuencia de 1600 Hz, ya que los cálculos previamente realizados muestran que tanto para el giro hacia la derecha como hacia la izquierda se requiere la misma frecuencia.

## Ejecución.
Se conecta el Arduino a los puertos donde recibe la velocidad de frecuencia y la dirección de jiro y se ejecuta el código obteniendo los resultados deseados.



https://github.com/user-attachments/assets/67f8eceb-01b8-4b50-9c38-bdf646b933ad


## Conclusiones.

Luis Fernando Duarte Reséndiz.

El control preciso de la dirección y velocidad de un motor a pasos es posible mediante la programación de un Arduino, permitiendo realizar movimientos específicos según las necesidades del sistema. La utilización de una frecuencia común para ambas direcciones de giro simplifica el diseño y asegura uniformidad en el comportamiento del motor.

Mauricio Alberto Gómez Arroyo.

La implementación de señales PWM, junto con la correcta configuración de pines de salida en el Arduino, facilita el manejo de motores a pasos. En este caso, el uso de 800 pulsos por revolución y una frecuencia de 1600 Hz permitió controlar con éxito los movimientos requeridos, cumpliendo con las especificaciones del proyecto.

Diego Brandon Guzmán Sierra.

El cálculo previo de la frecuencia y los pulsos necesarios es esencial para lograr un control eficiente y preciso del motor. Este enfoque evita errores durante la ejecución del código y garantiza que los tiempos de respuesta y los giros del motor cumplan con las especificaciones programadas.

Bryan Hiadim Vera Hernández.

Este proyecto demostró que, con una configuración adecuada y una programación precisa, es posible controlar un motor a pasos con gran precisión utilizando hardware de bajo costo como el Arduino. Además, el uso de una misma frecuencia para giros en ambos sentidos optimiza el control, reduciendo la complejidad del código sin afectar el rendimiento del sistema.

