## Getting Started with PSOC6 
2021-03-30 [#Blog](/index) | [#PSOC6](/posts/psoc6protoytpinggettingstarted)

In this post I'll let you know how to setup a development environment for [#PSOC6](https://www.cypress.com/products/psoc-6-microcontrollers-32-bit-arm-cortex-m4m0) from Infineon and execute the "Hello world" program.

![PSOC6PROTOKIT](/assets/cy01.jpg "PSOC6PROTOKIT")

### What is PSOC6? 
Before we start, let me quickly introduce you what PSOC6 is and what is used for.According to Infineon, the PSoC 6 family is built on an ultra-low-power architecture, and the MCUs feature low-power design techniques to extend battery life up to a full week for battery powered applications. The low power consumption makes the MCU interesting for gathering sensor data and many more applications. Normally in my projects I am using the Espressif MCUs. However, in the upcoming monthS, I'll build also some use cases with PSOC6 and compare the architectures. 
For more information about PSOC6, you can visit [this page](https://www.cypress.com/products/psoc-6-microcontrollers-32-bit-arm-cortex-m4m0).


### What hardware do you need?
* [PSOC 6 WiFi BT Protoyping Kit CY8CPROTO-062-4343W](https://www.cypress.com/documentation/development-kitsboards/psoc-6-wi-fi-bt-prototyping-kit-cy8cproto-062-4343w) for around 30 €. I bought this from RS components - [here](https://de.rs-online.com/web/p/entwicklungstools-microcontroller/1812206/)
* A notebook or PC to install the drivers and the Modus Toolbox for programming the MCUs

![PSOC6PROTOKITOPEN](/assets/cy02.jpg "PSOC6PROTOKITOPEN")

### Installation of Modus Toolbox
* open a browser and navigate to [www.cypress.com/CY8CPROTO-062-4343W](https://www.cypress.com/CY8CPROTO-062-4343W)
* download the Modus Toolbox software

![ModusToolboxDownload](/assets/cy_modustoolboxdownload.jpg "ModusToolboxDownload")

* Register of you do not have an account
* Start installation, follow the installation steps and then restart your PC

![ModusInstall01](/assets/cy_modustoolboxinstall.jpg "ModusInstall01")

![ModusInstall02](/assets/cy_modustoolboxinstall01.jpg "ModusInstall02")

![ModusInstall03](/assets/cy_modustoolboxinstall02.jpg "ModusInstall03")

### Connect the PSOC6 and start the "Hello World" programm
* Ensure that jumper J3 is at position 2-3 to select 3.3V

![Check Jumper](/assets/cj_jumper.jpg "Check Jumper")

* Connect the protoyping kit with the PC

![Connect to PC](/assets/cy_connect00.jpg "Connect to PC")

* Wait until the driver is installed

![Driver installation successful](/assets/cy_connect01.jpg "Driver installation successful")

* Check the COM port in the Device Manager

![Check COM port](/assets/cy_connect02.jpg "Check COM port")

* Open a terminal programm, like e.g. Putty
* Connect to the COM port with baud rate of 115200

![Connect to board](/assets/cy_connect03.jpg "Connect to board")

* Press Switch 1

![Connect to board](/assets/cyhelloworldbutton.jpg "Connect to board")

* Press Enter and see the port LED blinking

![Hello World blink](/assets/cy_helloworldblink.gif "Hello World blink")


Congratulations, you successfully finished the PSOC6 and IDE setup!
