# External Components for ESP Home

In general, these components will be submitted to be included in the official ESP Home repo, but that can take a while. So that I can use the components in my projects in the meantime, I have created this repo to store them temporarially.

## Components

### LC709203f Battery Monitor

**Status:** [Submitted on 1/5/2025.](https://github.com/esphome/esphome/pull/8037) No further changes expected.

A component for the battery monitor chip used on some of the Adafruit feather boards. See [here](https://github.com/ilikecake/esphome-docs/blob/9fd848a7df08a12a41c29e7bce224529517cb68e/components/sensor/lc709203f.rst) for more documentation on usage. Basic YAML setup:

    sensor:
      - platform: lc709203f
        size: 2000
        voltage: 3.7
        battery_voltage:
          name: "Battery Voltage"
        battery_level:
          name: "Battery"

### HT16K33 Character Display Driver



**Changes from the submitted copy**

* define `CONF_CONTINUOUS` locally in display.py.
* Remove reference to `get_i2c_address()` from the `dump_config()` function.

## Usage
