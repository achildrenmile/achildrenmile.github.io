## Lora MQTT Gateway
2021-03-06 [#Blog](/index) | [#LoRa](/posts/loragateway) | [#LoRaGateway](/posts/loragateway)

LoRa (Long Range) is a proprietary low-power wide-area network modulation technique based on spread spectrum modulation techniques derived from chirp spread spectrum (CSS) technology. More information on that can be found in [Wikipedia](https://en.wikipedia.org/wiki/LoRa). This protocol can be utilized to create small private LoRa networks or one can use the [TTS (=The Think Stack)](https://thethingsindustries.com/docs/) to utilize LoRaWan. In this post, I would like to show you how one can made a LoRa Client (=Sender) and a LoRa Gateway which will publish the incoming messages into a defined #MQTT channel using a local WiFi connection. The solution is using AES-128 encryption on top LoRa and uses a defined message format.

### What hardware do you need?
* 2 ESP32 based TTGO LoRa32 V2.1 _ 1,6 version 433/868/915 Mhz ESP32 LoRa OLED 0,96 Inch SD Karte Bluetooth WIFI wireless Modul ESP-32 SMA

### Architecture overview
Before we come to the implementation of the client and the gateway, let's check what we would like to build.

![Architecture Overview](/assets/loraarchitecture.svg "Architecture Overview")