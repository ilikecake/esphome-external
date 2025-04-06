# External Components for ESP Home

In general, these components will be submitted to be included in the official ESP Home repo, but that can take a while. So that I can use the components in my projects in the meantime, I have created this repo to store them temporarially.

## Components

### LC709203f Battery Monitor

**Status:** [Submitted on 1/5/2025.](https://github.com/esphome/esphome/pull/8037) No further changes expected.

A component for the battery monitor chip used on some of the Adafruit feather boards. See [here](https://github.com/ilikecake/esphome-docs/blob/9fd848a7df08a12a41c29e7bce224529517cb68e/components/sensor/lc709203f.rst) for more documentation on usage. Basic YAML setup:

```yaml
sensor:
  - platform: lc709203f
    size: 2000
    voltage: 3.7
    battery_voltage:
      name: "Battery Voltage"
    battery_level:
      name: "Battery"
```

### HT16K33 Character Display Driver



**Changes from the submitted copy**

* define `CONF_CONTINUOUS` locally in display.py.
* Remove reference to `get_i2c_address()` from the `dump_config()` function.

## Usage

To use these components add this to your YAML file:

```yaml
external_components:
  - source: github://ilikecake/esphome-external
    refresh: 12h
```

Note: The software will only check for changes to the git repo after `refresh` time. If you want to make it check faster, change `refresh` to something short like `10s`. However, don't leave it at a short time interval. Once it is updated the way you want, change it back to `12h` or something.
