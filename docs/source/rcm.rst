Checking RCM
===================================

This section of the guide will teach you how to access RCM, determine if your Switch is vulnerable to fusee, and run a payload.

RCM is the best way to run CFW as it supports all firmwares. Even if you plan to use a software-based exploit, you should always know if your Switch has an exploitable RCM and how to push payloads.

Step 0: What You Will Need
--------------------------

* A way to ground pin 10 on the right joycon rail

    * To access RCM, you must hold down volume up, power and the home button. **The home button described here is not the home button on the joycon,** but instead a hardware home button (think of the physical home button found on smartphones). The Nintendo Switch doesn't have this button, but you can simulate pressing it down by grounding pin 10 of the right joycon rail.
    * There are many ways to do this. You can see a `list of methods here. <https://gbatemp.net/threads/the-ultimate-list-of-mods-to-enter-rcm.502145/>`_ Some of these options are permanent hardmods, others are temporary. For now, you should pick a method that does not require teardown or soldering, in case your console is not vulnerable. 
    * Later in the guide, if your Switch is unpatched, you will learn of a way to have the Switch automatically enter RCM on every boot through a software mod.

* A device to send a payload

    * This guide will cover options for Windows, macOS, Linux and Android, though note that options exist for Chromebooks and jailbroken iOS devices.
    * You can also use a dedicated payload sending device (a "dongle" or modchip) if you have one. Intructions will not be provided on how to use these as each device is different. Check the manufacturers website.

* A USB Type C to A/Micro USB/USB Type C cable/adapter

    * Some kind of cable to connect your Switch to your payload sender of choice.
    * You can usually chain cables and adapters if necessary.
    * This is not needed if you are using a dedicated payload sending device.
    
* A payload sending application **(Download and install one now)**

    * For Windows, you can use `TegraRcmGUI by eliboa and rajkosto. <https://github.com/eliboa/TegraRcmGUI/releases>`_
    * For macOS and Linux, `you can use fusee-launcher by ReSwitched. <https://github.com/Cease-and-DeSwitch/fusee-launcher>`_
    * For Android, you can use `Rekado by MenosGrante. <https://github.com/MenosGrante/Rekado/releases>`_
    * If you don't already have one, after determining if your Switch is vulnerable to fusee, you can also choose to purchase any number of dedicated payload sending dongles, or purchase and install a modchip.

* A Micro SD Card

    * You should have an SD card at least 4GB in size, however 64GB or higher is recommended. A small SD card is enough to get CFW running, but larger ones are preferred for installing games, performing NAND backups efficiently, and creating emuMMCs.

* This `test payload <https://github.com/noahc3/Homebrew-Guide/files/3890384/fusee-test.zip>`_ downloaded to your payload sender device to verify if your Switch is vulnerable to fusee.


........

Step 1: Accessing RCM:
----------------------

It's time to get into recovery mode.

1. Completely power off your Switch

    * Hold the power button on your Switch for 3 seconds and choose to power down in the menu
    
2. Ground pin 10 of your right Joycon rail

    * Using a method from the guide linked above, ground pin 10. **Be very careful, bridging the wrong pins can fry your Switch!**
    
3. Press **Volume Up + Power**

    * While you're grounding pin 10, hold down Volume Up and then tap Power. You can release all buttons after tapping power.
    
        * You will know you are successful if the Switch **seemingly does not turn on.**
        * If your Switch turns on, try again. **This does not mean fusee-gelee is patched** as RCM is still available on patched Switches.
        
.. warning::
    This can be an extemely frustrating and tedious process without a jig. Keep trying, you'll get it eventually.

Did it work? Pat yourself on the back, you just finished the hardest part!

........

Step 2: Determining if Your Switch is Vulnerable to fusee
---------------------------------------------------------------

Time to find out if any of this prep was worth it.

**Only follow the part related to the payload sender you chose.** If you are using a payload sender not listed here, you'll need to determine how to use it by yourself.

........

**If you are using TegraRcmGUI, follow these instructions:**

1. Open TegraRCMGUI
2. Navigate to the Settings tab.
3. Click on Install Driver (this will install the driver required to communicate with your Switch).
4. After the driver is installed, navigate to the Payload tab.
5. Plug your Switch into your PC using your USB cable

    * Your PC should play the device connected sound and your Switch **should not turn on.** If your Switch turns on, repeat Step 1 to enter RCM.
    
6. Once your Switch is plugged in, you should see a green icon with the message "RCM OK".
7. Select the **fusee-test.bin** test payload you downloaded earlier
8. Select **"Inject Payload"** if the payload has not already been injected.
    * If you get the error "RC=-50", restart the application and try again.
    
.. important::

    A success message should now be displayed on your Switch. If so, celebrate! Your Switch is vulnerable and you can now push payloads!
    
.. error::

    If the application says the payload launch was successful, but nothing appears on your screen, unfortunately your Nintendo Switch is likely patched.  **You should try a few more times to be certain, and consider trying another USB cable.**
    If your Switch is patched and running firmware 4.1.0, you can still access CFW.
    If your Switch is patched and running a higher firmware version, unfortunately your Switch cannot be hacked right now.

.. error::

    TegraRcmGUI reporting the line "Smashed the stack with a 0x0000 byte SETUP request!" (specifically 0x0000 instead of some other number) is a reliable indicator that your Switch is patched. **You should try a few more times to be certain, and consider trying another USB cable.**


.. toctree::
   :maxdepth: 2
   :caption: Contents: