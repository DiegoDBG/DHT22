# Practica con un sensor **DHT22** en una placa de desarrollo **ESP32**
Este repositorio muestra como podemos programar una ESP32 con el sensor DHT22.
## Introducción
- Descripción:

La **ESP32** la utilizamos en un entorno de adquision de datos, en esta practica ocuparemos un sensor **DHT22** para adquirir temperatura y humedad del entorno; todo siendo simulado en una pagina llamda **WOKWI**
### Material Necesario
Para realizar esta practica necesitas lo siguiente:

- WOKWI
- Tarjeta ESP32
- Sensor DHT22

### Requisitos previos:
Para poder usar este repositorio necesitas entrar a la plataforma WOKWI.

### Instrucciones de preparación de entorno:
1.-Abrir la terminal de programación y colocar la siguente programación:
```
#include "DHTesp.h"

const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}
```
2.- Instalar la libreria de **DHT sensor library for ESPx** como se muestra en la siguente imagen.
![]()
