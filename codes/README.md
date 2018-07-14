# Custom components for Home Assistant
## Broadlink IR Climate Component

#### Configuration variables:
**name** (Optional): Name of climate component<br />
**host** (Required): The hostname/IP address of the broadlink rm device<br />
**mac** (Required): The MAC address of the broadlink rm device <br />
**timeout** (Optional): Timeout in seconds for the connection to the device<br />
**ircodes_ini** (Required): The path of ir codes ini file<br />
**min_temp** (Optional): Set minimum set point available (default: 16)<br />
**max_temp** (Optional): Set maximum set point available (default: 30)<br />
**target_temp** (Optional): Set initial target temperature. (default: 20)<br />
**target_temp_step** (Optional): set target temperature step. (default: 1)<br />
**temp_sensor** (Optional): **entity_id** for a temperature sensor, **temp_sensor.state must be temperature.**<br />
**default_operation** (Optional): (default: 'off')<br />
**default_fan_mode** (Optional): (default: auto)<br />
**customize** (Optional): List of options to customize.<br />
  **- operations** (Optional*): List of operation modes (default: idle, heat, cool, auto)<br />
  **- fan_modes** (Optional*): List of fan modes (default: low, mid, high, auto)<br />
  
#### Example:
```
climate:
  - platform: broadlink
    name: Toyotomi Akira
    host: 192.168.1.85
    mac: 'BB:BB:BB:BB:BB:BB'
    ircodes_ini: 'broadlink_climate_codes/toyotomi_akira.ini'
    min_temp: 16
    max_temp: 30
    target_temp: 20
    target_temp_step: 1
    temp_sensor: sensor.living_room_temperature
    default_operation: 'off'
    default_fan_mode: mid
    customize:
      operations:
        - 'off'
        - cool
        - heat
      fan_modes:
        - low
        - mid
        - high
        - auto
```


## Broadlink IR Media Player

#### Configuration variables:
**name** (Optional): Name of climate component<br />
**host** (Required): The hostname/IP address of the broadlink rm device<br />
**mac** (Required): The MAC address of the broadlink rm device<br />
**timeout** (Optional): Timeout in seconds for the connection to the device<br />
**ircodes_ini** (Required): The path of ir codes ini file<br />
**ping_host** (Optional): The IP address of your TV box. If your TV box has a LAN connection, the component can detect your actual TV state.<br />
**power_consumption_entity** (Optional): **entity_id** for a power consumption sensor. If your TV box can provide the power consumption, the component can detect your actual TV state. If ping_host is set, the component ignores this value.<br />
**power_consumption_threshold** (Optional)<br />

#### Example:
```
media_player:
  - platform: broadlink
    name: Master Bedroom TV
    host: 192.168.1.85
    mac: 'BB:BB:BB:BB:BB:BB'
    ircodes_ini: 'broadlink_media_codes/philips.ini'
    ping_host: 192.168.1.70
```

#### How to make your INI Files:
The INI file must have a [general] section and optionally a [sources] section.
In the [general] section you must fill all keys and values. The keys are: 
```
[general]
turn_off = ...
turn_on = ...
previous_channel = ...
next_channel = ...
volume_down = ...
volume_up = ...
mute = ...
```
You are free to set any key name under [sources] section.
```
[sources]
My source 1 = ...
My source 2 = ...
.
.
.
```
You can combine 2 or more commands separated by a "|" character.
```
[sources]
My source 1 = ...|...
.
.
.
```


## Broadlink RF Fan

#### Configuration variables:
**name** (Optional): Name of fan component<br />
**host** (Required): The hostname/IP address of the broadlink rm device<br />
**mac** (Required): The MAC address of the broadlink rm device<br />
**timeout** (Optional): Timeout in seconds for the connection to the device<br />
**rfcodes_ini** (Required): The path of RF codes ini file<br />
**default_speed** (Optional): Default fan speed when fan is turned on<br />
**default_direction** (Optional): Default fan rotation direction when turned on. Possible values are right (clockwise) and left (anti-clockwise). (default: left)<br />
**customize** (Optional): List of options to customize.<br />
  **- speeds** (Optional*): List of supported speeds (default: low, medium, high)<br />

#### Example:
```
fan:
  - platform: broadlink
    name: Living Room Fan
    host: 192.168.1.85
    mac: 'BB:BB:BB:BB:BB:BB'
    rfcodes_ini: 'broadlink_fan_codes/living_room_fan.ini'
    default_speed: low
    defaut_direction: left
    customize:
        speeds:
            - low
            - medium
            - high
            - highest
```
