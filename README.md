# Wemos D1 Mini Weather Station

## Wemos D1 Mini

[Wemos D1 Mini Specifications](https://www.wemos.cc/en/latest/d1/d1_mini.html)

## BME280

[ESP8266 Weather Station](https://lastminuteengineers.com/bme280-esp8266-weather-station/)

* [BME280 I2C Address Change Procedure](https://lastminuteengineers.com/bme280-arduino-tutorial/#procedure-to-change-i2c-address)

## LDR (Photoresistor) 

[ESP32 LDR (Photoresistor) Example](http://www.esp32learning.com/code/esp32-and-ldr-example.php)

* LDR between A0 and 3v3
* 10k resistor between A0 and Ground

## LED

[ESP32 Push Button & LED example](https://microcontrollerslab.com/push-button-esp32-gpio-digital-input/)

* Use D4 as built-in LED.

# Pinout

| Interface        | Pin | ESP8266 Pin | Pin Mode | Address | Verb | Library |
| ---------------- | --- | ----------- | -------- | ------- | ---- | ------- |
| BME280 SCL (SCK) | D1  | GPIO 5      |          |         |      |         |
| BME280 SDA (SDI) | D2  | GPIO 4      |          |         |      |         |
| BME280 Vin       | 3v3 |             |          |         |      |         |
| BME280 I2C       | .   | .           | .        | 0x76    | .    |         |
| Photoresistor    | A0  | A0          |          |         |      |         |
| Reserved open    | D3  | GPIO 0      |          |         |      |         |
| LED built-in     | D4  | GPIO 2      |          |         |      |         |
| LED (extra))     | D8  | GPIO 15     |          |         |      |         |
