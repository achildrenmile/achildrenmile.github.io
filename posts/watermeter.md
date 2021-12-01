## Smart Watermeter reader aka AI-on-the-edge-device (by jomjol)
2021-01-12 [#Blog](/index) | [#AI](/posts/watermeter) | [#Watermeter](/posts/watercounter)

Every once a year our local village water department sends us a snail mail to read the measure of our water counter and send them back. And every year, I think, why the hell is this necessary, if there are technical solutions out there which can handle this, ...but that's another story, however.

Next time, we can do this a little bit easier directly in our Home Assistant.

Thanks to the great effort of @jomjol there is an open source solution in order to read out our digital and even anolog meters (even reading out old energy meters should be possible)!

### What hardware do you need?
* ESP32 AI Thinker CAM

### Platform
You need one running MQTT broker. You can find a guide [here](http://www.steves-internet-guide.com/install-mosquitto-broker/).

### Architecture overview
Before we come to the implementation of the client and the gateway, let's check what we would like to build.

![Architecture Overview](/assets/watermeterarch.svg "Architecture Overview")

### How does it work?

The ESP32 cam in the 3d printed housing is mounted on top of the watermeter.The device is using a [trained neural network](https://github.com/jomjol/neural-network-digital-counter-readoutAll) in order to interpret the numbers. After setup and calibration of the firmware the cam will push the data through the MQTT channel in a defined interval. All you need in order to setup and configure can be found [here](https://github.com/jomjol/AI-on-the-edge-device). 

### How does it look like?

![Configuration](/assets/watermeter_configuration.jpg "Configuration")

![Watermeter moutned](/assets/watermeter_mounted.jpg "Watermeter mounted")

![HomeAssistant](/assets/watercounterha.jpg "Result")





