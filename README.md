# ESPHome QuinLED-An-Penta-Mini Motion Controller Light with Day Schedule

This repo contains a set of configuration files for creating an ESPHome
firmware for a QuinLED-An-Penta-Mini board with a motion sensor to control
a light based on motion and a day schedule taking into account both sunrise
and sunset times as well as day/night transition times.

## Web Interface

![ESPHome Webinterface](images/ESPHome-web-interface.png)

## Day/Night Schedule

![Day Night Schedule](./images/DayNight-Schedule.svg)

## Hardware

### Motion Sensor

I am using two C4001 24GHz mmWave radar sensor to detect presence.

While it is not cheap, it is capable of flawless detection of presence
even without motion over quite a lot of distance (I tested up to 4 meters).

It supports configuration via UART, but I simply use it in its default config
which only needs three wires (per sensor).

![C4001 24GHz mmWave Sensor](./images/C4001-mmWave.png)

### Wiring

TODO
