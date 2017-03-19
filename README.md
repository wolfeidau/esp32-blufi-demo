# ESP-IDF Blufi demo

This is the demo of bluetooth onboarding for the ESP32 boards. It uses bluetooth to delivery the wifi configuration to the device. On top of the existing blufi example in [esp-idf](https://github.com/espressif/esp-idf/tree/master/examples/bluetooth/blufi) it uses Non-Volatile Storage (NVS) to save the credentials and disables the onboarding interface after rebooting, which means it is "closer" to a real demonstration and can be used "as is" in prototypes.

This uses some interesting methods to protect the data in transit between the Android application and the ESP32 and removes the need to HARD CODE the damn wifi credentials in your project code!!

As I understand it it uses Diffie–Hellman key exchange (DH) in conjunction with AES to exchange the wifi information over a GATT connection.

# Getting Started

In my case I setup the Android development environment and built an APK using the Android project listed below.

I then built this [esp-idf](https://github.com/espressif/esp-idf) project using `make`.

```
make flash
```

**Note:** You will need to follow the setup guide on the esp-idf site to get up and running.

# TODO

* At the moment this example app will NOT expose the bluetooth onboarding once it is setup, this needs to be resettable by HOLDING the EN button for a few seconds, aka Factory reset.
* Once configured the device should be rebooted to disable onboarding, or bluetooth turned off.
* Provide a Arduino example.

# Links 

This demo uses the recently somewhat opensourced [EspBlufi](https://github.com/EspressifApp/EspBlufi) Android application. This seems to also share code with [BleLiteLib4android](https://github.com/afunx/BleLiteLib4android).

# License 

This code is Copyright 2015-2016 Espressif Systems (Shanghai) PTE LTD and Mark Wolfe and is released under Apache 2.0 license.

