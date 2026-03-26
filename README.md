# External Components for ESP Home

In general, these components will be submitted to be included in the official ESP Home repo, but that can take a while. So that I can use the components in my projects in the meantime, I have created this repo to store them temporarially.

## Components

### HT16K33 Character Display Driver

**Status:** [Submitted on 4/5/2025.](https://github.com/esphome/esphome/pull/8520) As of 3/25/2026, this version is up-to-date with the PR.

A driver for HT16K33 based character displays. See [here](https://github.com/ilikecake/esphome-docs/blob/f764c658b156498e4d027ab4ed47ba3fc3f97e88/components/display/ht16k33-char.rst) for more documentation on usage.

Basic YAML setup:

```yaml
display:
  - platform: ht16k33_char
    device: ADAFRUIT_7SEGMENT_1.2IN
    address: 0x70
    max_buffer_length: 8
    lambda: |-
      auto time = id(sntp_time).now();
      it.clock_display(0, true, false, true, time);
```

**Changes from the submitted copy**

* None

## Usage

To use these components add this to your YAML file:

```yaml
external_components:
  - source: github://ilikecake/esphome-external
    refresh: 12h
```

Note: The software will only check for changes to the git repo after `refresh` time. If you want to make it check faster, change `refresh` to something short like `10s`. However, don't leave it at a short time interval. Once it is updated the way you want, change it back to `12h` or something.
