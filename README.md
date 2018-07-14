# My Home Assistant Configuration

## Link https://www.home-assistant.io

Used devices:

- Xiaomi Aqara GW and BLE
 - https://www.youtube.com/watch?v=4Eot6Nt8USc
 - https://xiaomi-mi.com/sockets-and-sensors/xiaomi-mi-smart-home-kit/
 - https://xiaomi-mi.com/sockets-and-sensors/xiaomi-aqara-smart-light-control-set/
 - https://xiaomi-mi.com/sockets-and-sensors/xiaomi-mijia-aqara-water-sensor/
 - https://www.youtube.com/watch?v=q-VYxZtR-Dg
 - https://www.gearbest.com/robot-vacuum-accessories/pp_1306883.html


- Sonoff devices running Tasmota firmware
  - https://github.com/arendst/Sonoff-Tasmota
  - http://sonoff.itead.cc/en/products/residential/s20-socket
  - http://sonoff.itead.cc/en/products/sonoff/sonoff-basic


- Philips HUE (via discovery)
  - https://www2.meethue.com/


- Tellduslive (via discovery)
  - https://www.karkkainen.com/verkkokauppa/proove-smart-home-large-aloituspakkaus


- Miflora sensor
  - https://www.gearbest.com/other-garden-supplies/pp_373947.html

- Bluetooth device tracker

- Custom component
  - media player ps4
    - https://github.com/hmn/home-assistant-config/wiki/media_player_ps4

- HomeKit
  - https://www.home-assistant.io/components/homekit/

- Coming soon: Broadlink RM mini 3 and new Aquara switches
  - http://www.ibroadlink.com/rmMini3/
  - https://www.home-assistant.io/components/switch.broadlink/

- Working with Embelin (Webasto ThermoConnect) to find out if they can open their API to control GSM/GPRS car heating systems via homeassistant.

# Memo for todo-branch
For Broadlink:

https://github.com/vpnmaster/homeassistant-custom-components

How to switch off the AC unit using this component? There is no “off” control. Do I need to add “off” to one of the custom mode?:
  Yes. If you are using HomeKit is better to add idle in customize->operations.
Yes. idle and off is the same command. Home kit sends idle instead of off command

  Hi,
  Please make a folder with name “custom_components” into your .homeassistant folder.
  Make another folder with name “climate” into custom_components folder.
  Put broadlink.py 43 inside “climate” folder and restart Home Assistant.

climate:
  - platform: broadlink
    name: LG
    host: 192.168.x.x
    mac: 'BB:BB:BB:BB:BB:BB’
    ircodes_ini: 'broadlink_climate_codes/lg_all.ini’
    min_temp: 18
    max_temp: 30
    target_temp: 26
    temp_sensor: sensor.living_room_temperature
    default_operation: idle
    default_fan_mode: low
    customize:
    operations:
    - idle
    - cool
    - heat
    - auto
    fan_modes:
    - low
    - mid
    - high
    - auto



  # Battery level alerts and status monitor
    https://community.home-assistant.io/t/howto-create-battery-alert-without-creating-a-template-for-every-device/30576/6
    https://github.com/notoriousbdg/Home-AssistantConfig/blob/master/packages/battery_alert.yaml
