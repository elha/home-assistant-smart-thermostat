# custom_components
missing feature test repository

## PID controller thermostat

### Installation:
1. Go to <conf-dir> default /homeassistant/.homeassistant/ (it's where your configuration.yaml is)
2. Create <conf-dir>/custom_components/ directory if it does not already exist
3. Clone this repository content into <conf-dir>/custom_components/
4. Set up the smart_thermostat and have fun

### Usage:
pid controller will be called periodically.
output is a analog value

#### Autotune:
You can use the autotune feature to set the PID parameters.

### Parameters:

#### Still same:

* name (Required): Name of thermostat
* heater (Required): entity_id for heater switch, must be a analog device.
* target_sensor (Required): entity_id for a temperature sensor, target_sensor.state must be temperature.
* max_temp (Optional): Set maximum set point available (default: 35)
* target_temp (Optional): Set initial target temperature. 
* noiseband (Optional): (default : 0.5), set noiseband (float): Determines by how much the input value must overshoot/undershoot the setpoint before the state changes.

#### configuration.yaml
```
climate:
  - platform: smart_thermostat
    name: Study
    heater: switch.study_heater
    target_sensor: sensor.study_temperature
    max_temp: 21
    target_temp: 17
    noiseband : 0.5
```
