# Home Assistant Climate Group (+Offset!)

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/custom-components/hacs)

### Groups multiple climate devices to a single entity

Inspired/copied from Home Assistant component ["Light group"](https://github.com/home-assistant/home-assistant/blob/dev/homeassistant/components/group/light.py)


## Changelog

### Wikibrikofix
    aligned the code to the original project

### fork of bjrnptrsn/climate_group

### 1.0.8
- Forked from @bjrnptrsn to add new features

### 1.0.7
- Changed behaviour for Action 'turn on': Use the most common HVAC mode

### 1.0.6
- Added support for Home Assistant Core Integration Generic turn on and off (thanks to @ladzar)

### 1.0.5
- Patched for Home Assistant core 2024.4.0 (thanks to @lweberru)

### 1.0.4
- Support for new service call `climate.toggle`

### 1.0.3
- New option: Change target temperature decimal accuracy to .5

### 1.0.2
- Minor changes to the behaviour of the states: HVACAction, HVACMode, HVACPresetMode

### 1.0.1
- Forked from [@daenny]((https://github.com/bjrnptrsn/climate_group)) based on 1.0.0-rc6
- Patched for Home Assistant core 2024.1.0



## How to install:

### HACS
Add this repo **https://github.com/gummiangler/climate_group** to the HACS store and install from there.

### Local installation
Copy both .py files to folder: ***config/custom_components/climate_group***

## Sample Configuration

Put this inside ***configuration.yaml*** in config folder of hass.io

```yaml
climate:
  - platform: climate_group
    custom_entity: 'climate.climate_group enitity_name'
    name: 'Climate Friendly Name'
    temperature_unit: C             # optional: C / F        [default: C]
    decimal_accuracy_to_half: True  # optional: True / False [default: False]
    unique_id: [UUID]               # optional: any UUID     [default: None]
    entities:
      - climate.clima1
      - climate.clima2
      - climate.clima3
      - climate.heater
      - climate.termostate
    offsets:
      climate.clima1: 0
      climate.clima: -2
      climate.clima3: 2
```
