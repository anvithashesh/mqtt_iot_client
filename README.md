# mqtt_iot_client
## Project Overview
This project implements an IoT-based messaging system where a user can remotely request temperature sensor data from an nRF52840DK development board i.e our iot device via Telegram using MQTT-SN. The system utilizes an nRF52840 Dongle with raspberry pi as a border router to enable IPv6 communication and RSMB as the MQTT broker for protocol translation between MQTT-SN and MQTT.

A Python-based MQTT client runs on an AWS EC2 instance, subscribes to sensor data, and integrates with the Telegram Bot API to allow real-time interaction with the IoT device.

### Configure the broker IP and port in makefile of emcute_mqttsn
```make
BROKER_IP ?= "2600:1f18:3cfc:b60:9ba9:7acb:7f8:daeb"
BROKER_PORT ?= 1883
```

### Compile and flash the  to the nrf52840dongle and then connect it to raspberry pi
```bash
BOARD=nrf52840dongle make all flash term
```
### Compile and flash the  to the nRF52840DK
```bash
BOARD=nrf52840dk make all flash term
```
## Set up the RSMB brocker by following instructions on the below link
https://github.com/Varshraghu98/mosquitto.rsmb.git
