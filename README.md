# Wemos D1 Mini Weather Station

# Getting Started

* [Arduino ESP8266 Toolchain](https://arduino-esp8266.readthedocs.io/en/latest/installing.html#using-git-version)

# Hardware

## Wemos D1 Mini

[Wemos D1 Mini Specifications](https://www.wemos.cc/en/latest/d1/d1_mini.html)

### Pinout

| Interface        | Pin | ESP8266 Pin | Pin Mode | Address | Verb | Library |
| ---------------- | --- | ----------- | -------- | ------- | ---- | ------- |
| BME280 SCL (SCK) | D1  | GPIO 5      |          |         |      |         |
| BME280 SDA (SDI) | D2  | GPIO 4      |          |         |      |         |
| BME280 Vin       | 3v3 |             |          |         |      |         |
| BME280 I2C       |     |             |          | 0x76    |      |         |
| Photoresistor    | A0  | A0          |          |         |      |         |
| Reserved open    | D3  | GPIO 0      |          |         |      |         |
| LED built-in     | D4  | GPIO 2      |          |         |      |         |
| LED (extra))     | D8  | GPIO 15     |          |         |      |         |

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

# Notes

## Azure IoT Hub with ESP8266

[Arduino ESP8266 Secure Http Azure IoT Hub Client](https://gloveboxes.github.io/Arduino-ESP8266-Secure-Http-Azure-IoT-Hub-Client-V2/)
How cool is this link! Looks like it does a lot of what I need, even includes a BME280 sensor.
* Command to get certificate on site differs in quoting. Use: `echo -n | openssl s_client -connect gardeniothub.azure-devices.net:443 | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > cert.pem`
* `$ openssl x509 -noout -in cert.pem -fingerprint`
  * Results in: `SHA1 Fingerprint=5E:BC:E7:4C:D8:29:06:14:74:32:9F:F7:5A:4A:43:82:64:E6:01:28`

## MicroPython

* ok, so I'm frustrated with the inconsistency in establishing a consistent development environment using Arduiono IDE. I can't seem to repeat package management from past projects. Doing some investigation into other technologies starting with Micropython and depending on my success, might move over to FreeRTOS or something else.
* Getting Started
  * https://realpython.com/micropython/
  * https://randomnerdtutorials.com/getting-started-micropython-esp32-esp8266/
  * https://randomnerdtutorials.com/getting-started-thonny-micropython-python-ide-esp32-esp8266/
  * [Flashing MicroPython Firmware with esptool.py on ESP32 and ESP8266](https://randomnerdtutorials.com/flashing-micropython-firmware-esptool-py-esp32-esp8266/)
    * [Python (Windows)](https://www.python.org/downloads/windows/)
    * [MicroPython ESP8266 Firmware](https://micropython.org/download/esp8266/)
      * Current version as of 2021-05-23 [esp8266-20210418-v1.15.bin](./esp8266-20210418-v1.15.bin)
* IDE's
  * [Thonny IDE](https://thonny.org/)
  * [uPyCraft](https://dfrobot.gitbooks.io/upycraft/content/)
* BME280
  * https://randomnerdtutorials.com/micropython-bme280-esp32-esp8266/
* Photoresistor
  * https://micropython-on-esp8266-workshop.readthedocs.io/en/latest/advanced.html
  * P2: https://blog.gypsyengineer.com/en/diy-electronics/reading-photoresistor-on-esp32-with-micropython.html
  * https://www.instructables.com/NodeMCU-With-LDR/
  * https://www.instructables.com/Auto-LED-Using-LDR-With-NodeMCU/
* LED
  * Assumed this will be simple digital io, not investigating.
* Azure IoT Integration
  * http://blogs.recneps.org/post/Connecting-the-ESP-8266-to-Azure-IoT-Hub-using-MQTT-and-MicroPython
  * http://blogs.recneps.net/post/Sending-data-from-the-ESP-8266-to-the-Azure-IoT-hub-using-MQTT-and-MicroPython
  * https://techcommunity.microsoft.com/t5/internet-of-things/micro-python-on-esp32-to-send-telemetry-to-azure-iot-hub-with/ba-p/1236022
  * https://github.com/bechynsky/Micropython/blob/master/iothub.py
  * http://thewindowsupdate.com/2020/03/18/micro-python-on-esp32-to-send-telemetry-to-azure-iot-hub-with-mqtt/
  * https://sandervandevelde.wordpress.com/2019/05/07/connection-a-cheap-esp8266-to-azure-iot-central/
  * https://forum.pycom.io/topic/5713/send-data-to-azure-iothub-with-mqtt-protocol-without-using-pybytes-solved
* Wifi
  * https://blog.miguelgrinberg.com/post/micropython-and-the-internet-of-things-part-iv-wi-fi-and-the-cloud
