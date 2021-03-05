## Using Power Automate & Home Assistant to trigger a mailbox indicator
2021-03-05 [#Blog](/index) | [#PowerAutomate](/posts/mailboxindicator) | [#MailboxIndicator](/posts/mailboxindicator)

A while back I created a [Mailbox indicator](https://www.instagram.com/p/CKtN3ThL1hd). This blog post will describe you the necessary steps to trigger the mailbox indicator whenever a mail arrives in your M365 Outlook using [#HomeAssistant](https://www.home-assistant.io/) and [#PowerAutomate] (https://flow.microsoft.com) to talk to your mail indicator device.

### What hardware do you need?
* ESP8266 or ESP32 based board (ideally in the form factor of a WEMOS or TTGO mini)
* SG 90 Servo
* 3D Printed mailbox from [Thingiverse](https://www.thingiverse.com/thing:3067957)

### Hardware - Put the stuff together
* Solder the VCC cable to the 3.3V pin of the MCU, the GND cable to the ground of the MUC and the data cable with the GPIO pin of your choice (e.g. D5)
* Print the parts and follow the assembly instructions from [Thingiverse](https://www.thingiverse.com/thing:3067957)

### Platform - Home Assistant
In order to run the whole thing, you need to have a running Home Assistant instance including MQTT broker. You can find several guides and howto's like [this one](https://scienceprog.com/how-to-set-up-home-assistant-mqtt-sensor-on-raspberry-pi/) in the net.

### Software - flash the controller
Side note: This will give you a rough overview about the software steps. In case you have not yet programmed in Arduino Studio and no experience there are several tutorials out there like e.g. [randomnerdtutorial](https://randomnerdtutorials.com/getting-started-with-esp32/).

* Download the sample sketch from [github](https://github.com/achildrenmile/smarthomestuff/blob/main/maiboxservo/mailboxservo.ino).
* Open the sketch with Arduino Studio
* Add your wifi credentials and mqtt connection details
* Select the correct hardware board (e.g. WEMOS D1 Mini ESP32) 
* Connect the board with your PC
* Select the correct serial port
* Upload the firmware
* Test it: Try if the defined mqtt channel receives signal, when there is no contact and when there is contact. To do this, you just need to run a MQTT software like [MQTT.fx](https://mqttfx.jensd.de/), connect to the broker and subscribe to the corresponding channel. If everything is configured properly then you'll receive the JSON messages. In case you don't receive messages, you have to check the wiring as well as the configuration parameters in your secrets.h. Furthermore, you can connect to the controller via putty and check the serial print for more information, add debug information to the software, etc.

### Home Assistant configuration
If all works well and you receive messages in the defined channel, you can do the last steps in order to add the sensor to your smart home platform. 

Open the scripts.yaml of your Home Assistant instance and add following sensor to the sensor configuration:

```
  maibox_indicator_1_trigger:
  alias: Mailbox Indicator 1 Trigger
  sequence:
  - service: mqtt.publish
    data:
      topic: homeassistant/mailbox1/set
      payload: ha_toogle
  mode: single
```
Then add the sensor to your Dashboard and you'll see something like this:
<br><br>
![MaibloxtriggerHassio](/assets/mailboxtriggerhassiio.jpg "Mailbox Trigger")
<br><br>

You can then test the trigger manually and the Mailbox indicator flag should move up and down after each execution.

### Power Automate configuration
* Open the browser and enter the address www.office.com
![Step01](/assets/powerautomate01.jpg "Open office.com")
* If you have no office account create one and login
* Click "Power Automate"
![Step02](/assets/powerautomate02.jpg "Open Power Automate")
* Click "Office 365 Outlook" under "Popular Services"
![Step03](/assets/powerautomate03.jpg "Choose Office 365 Outlook")
* Click "When new mail arrives"
![Step04](/assets/powerautomate04.jpg "Click When new mail arrives")
* Choose Folder "inbox" and click next
![Step05](/assets/powerautomate05.jpg "Choose folder inbox and click next")
* Search for "http" operation and choose this (Note: This is a premium service and after a trail period this will charges will be there. More info on pricing here [Power Automate pricing](https://flow.microsoft.com/en-us/pricing/))
* Enter the REST API configuration:
 * Choose Method POST
 * Enter the url https://<yourhomeassistantpublicdns>/api/services/script/turn_on and change <yourhomeassistantpublicdns> with your real dns name
 * Add header Authorization and copy your long lived access token there (be careful to not expose this information!)
 * Add Body 
 ```{
  "entity_id": "script.maibox_indicator_1_trigger"
 ```
 ![Step06](/assets/powerautomate06.jpg "Fill out http request information")
* Test it manually by sending a mail to your mailbox
* The flow should be in state success and the mailbox trigger fired

<br><br>
![MailboxTriggerFired](/assets/mailboxtriggerfired.jpg "Mailbox Trigger fired")
<br><br><br><br>

Congratulations, you have successfully created and configured your mailbox indicator :)

