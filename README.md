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


- HomeKit
  - https://www.home-assistant.io/components/homekit/


- Slack notifications


- Monitoring corridor movement with three Aqara motion sensors
  - in configuration.yaml -> corridor_movement and corridor_movement_night


- DLNA-internet radio with Chromecast audio
  - Automation to turn on the radio when casting starts to Chromecast audio


- Automation to check if AC:s water bucket is full
  - id: '1621680487465'
  - Uses Aqara water sensor with extended cables to the bucket


- Broadlink RM mini 3 in an other instance (TODO: own branch for other instance)
  - http://www.ibroadlink.com/rmMini3/
  - https://www.home-assistant.io/components/switch.broadlink/

