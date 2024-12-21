# ESPHome QuinLED-An-Penta-Mini Motion Controller Light with Day Schedule

This repo contains a set of configuration files for creating an ESPHome
firmware for a QuinLED-An-Penta-Mini board with a motion sensor to control
a light based on motion and a day schedule taking into account both sunrise
and sunset times as well as day/night transition times.

## Web Interface

The web interface is provided by ESPHome and can be accessed by navigating to
the IP address of the ESPHome device in a web browser.

![ESPHome Webinterface](images/ESPHome-web-interface.png)

## Day/Night Schedule

The day/night schedule takes into account both user-configurable "morning time" and "night time",
as well as the state of the sun (below or above horizon). Based on these inputs a "schedule state"
is determined, which defines the brightness and color temperature of the light. The schedule state
includes the following states:

- `day`
- `transition`
- `night`

![Day Night Schedule](./images/DayNight-Schedule.svg)

## Hardware

### LED Controller

This config is setup for a [QuinLED-An-Penta-Mini](https://quinled.info/quinled-an-penta-mini/).

![QuinLED-An-Penta-Mini](https://quinled.info/wp-content/uploads/2024/05/P1063051-Enhanced-NR_website-scaled.jpg)

If you want to use a different controller, this repo should still work, but you will probably
have to change the `device_base` packages referenced in the main config and update the defined pins.

### LED Strip

I am using a 5m 24V 120LED/m CCT (Warm White + Cold White) LED Strip (`AXM-SL2835WWCW120NP-W245-H95`):

![LED Strip](./images/AXM-SL2835WWCW120NP-W245-H95.png)

Although this is a very high CRI strip (>95) my experience with it is mixed, see [here](https://www.reddit.com/r/led/comments/1741sh4/comment/m282rvo/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button).

The range of color temperature settings is reflected by this LED strip (2700K - 5500K). If you
have a different LED strip, you will have to adjust the `min` and `max` values in the [config.yaml](config.yaml)
accordingly.

### Motion Sensor

I am using two C4001 24GHz mmWave radar sensor to detect presence.

While it is not cheap, it is capable of flawless detection of presence
even without motion over quite a lot of distance (I tested up to 4 meters).

It supports configuration via UART, but I simply use it in its default config
which only needs three wires (per sensor).

![C4001 24GHz mmWave Sensor](./images/C4001-mmWave.png)

### Wiring

TODO
