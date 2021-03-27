# Logging to a MQTT server with the same print() interface as Serial

This library provides an object that can be used just like Serial for printing logs, 
however the text sent with print() is published on a MQTT broker instead of printing over
the Serial console. This comes in handy when working with devices like the popular 
ESP8266/ESP32 that are connected over Wifi or Ethernet. I use it for debugging my robots
that are based on ESP32.

The library uses [https://github.com/knolleary/pubsubclient](PubSubClient) for sending
the MQTT messages.

## Examples

See directory `examples`. I'll add more stuff here in the future.

## Compatible Hardware

All devices that work with the PubSubClient should work with this libary, including:

 - Arduino Ethernet
 - Arduino Ethernet Shield
 - Arduino YUN – use the included `YunClient` in place of `EthernetClient`, and
   be sure to do a `Bridge.begin()` first
 - Arduino WiFi Shield - if you want to send packets > 90 bytes with this shield,
   enable the `MQTT_MAX_TRANSFER_SIZE` define in `PubSubClient.h`.
 - Sparkfun WiFly Shield – [library](https://github.com/dpslwk/WiFly)
 - TI CC3000 WiFi - [library](https://github.com/sparkfun/SFE_CC3000_Library)
 - Intel Galileo/Edison
 - ESP8266
 - ESP32

## License

This code is released under the MIT License.