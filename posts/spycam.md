## Spycam 
2021-02-28 [#Blog](/index) | [#Spycam](/posts/spycam)

Today I found the time to investigate a Chinese manufactured spycam pruchased months ago on AliExpress (for around 15€). The cam is hidden in a digital alarm clock and barely recognizable. 

![Spycam](/assets/spycam.jpg "Spycam")

After powering the device with the mini USB cable, the clock shows no time. So, in order to wake the whole system up, one has to grab the smartphone and install the V380 pro app for configuring the spy. After installing the app, one has to connect to the camera directly via WIFI and add the local WIFI credentials. Once this was done, the alarm clock display shows the current time and also you can connect to the camera. Next, I installed [BlueStacks](https://www.bluestacks.com/), [WireShark](https://www.wireshark.org/) and V380 pro in BlueStacks to prepare all the tools to find how the app connects to camera. To investigate WireShark and V380 pro were started in parallel to check the network traffic. Bam, surprise (or not)! 

![Spycam](/assets/spycam02.jpg "Spycam")

Although, I did not create a cloud user and gave no consensus to explicitly use cloud services the app is using a direct connection to Tencent to play show the video and play the sound. In order to break the connection, I completely blocked the discovered Tencent IP from out and inbound. Guess what, this thing is using a fallback then :-)
However, I did not find a way to use a direct WIFI connection to this camera. With this configuration and the direct streaming from picture and voice from home to China and back, I cannot recommend to anyone to use this. However, will further discover, maybe there is a native way, or one can flash the cam with other firmware. The update might follow.