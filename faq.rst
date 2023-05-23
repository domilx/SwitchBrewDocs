Frequently Asked Questions
==========================

What actions can get me banned?
-------------------------------

Instant ban:

* Piracy
* Installing homebrew NSP files
* Changing your user icon with homebrew
* Sketchy eShop behavior, including chargebacks
* Using homebrew or PC tools with your console unique certificate to query or download from Nintendo's CDN.

Likely ban, typically delayed:

* Modding online games
* Cheating in online games
* Clearing system logs using homebrew
* Using multiple NANDs online (sysMMC and emuMMC) without using a DNS like 90DNS or PegaScape on all or all but one of them.

Not a ban, so far:

* Atmosphere CFW
* Homebrew
* Custom themes
* Custom sysmodules
* Mods/cheating in offline games with no multiplayer or online component
* Overclocking
* emuMMC
* Simply running Fusee payloads
* Running other operating systems such as Android or Linux

   
Should I disable WiFi?
----------------------

This is an extreme that you don't necessarily need to take, though it will basically 100% guarantee you won't get banned (since you are basically banning yourself).

Using 90DNS (163.172.141.219 or 207.246.121.77) or enabling GDPR protections is usually enough to keep from being banned as long as you don't care about NSP files.

........

Can't load Homebrew Launcher?
-----------------------------

When trying to access Album, or any game, hold the R button and this will launch Homebrew Launcher.

........

What are sigpatches?
--------------------

Sigpatches allow your Switch to install and run unofficial NSP files (digital titles that appear on the home menu). Note that you must use CFW to launch these applications even after installation as sigpatches are always required to do so.

.. important:: 

    Using ES or FS patches are not supported by Atmosphere and never will be. Please use Google to answer any questions regarding this.

........

Is it safe to update to the latest firmware version?
----------------------------------------------------

When a new firmware update is released, you should always wait for SDSetup to add support for it, or if a trusted source says it is safe. New firmware versions can also bring unwanted telemetry. Ultimately, whether or not you update is up to you.

**As of writing, the latest firmware version is 14.1.0. It is currently completely safe to update as long as you are using Atmosphere v1.3.1+ or a bundle from SDSetup downloaded after May 3rd 2022.**

........
    
What does 'burning fuses' mean? / Can I downgrade my Nintendo Switch?
----------------------------------------------------------------------

The Switch uses a common anti-downgrade technique that utilizes microscopic (ie. cannot be replaced) fuses built into the CPU. When you turn on your Switch through regular means, the firmware performs a fuse check:

* The firmware will first check for how many fuses are burnt
* If there are less fuses burnt than the firmware version expects, it will burn up fuses up to as many as it expects and reboot.
* If there are exactly enough fuses burnt as the firmware expects, it will allow the Switch to load
* If there are too many fuses burnt, your Switch will shutdown, not allowing the firmware to boot.

The fusee-gelee exploit happens before any of these checks occur, meaning these checks can be bypassed. **Hekate, ReiNX, and SX OS all block fuses from being burnt and bypass the fuse check**, meaning you can keep your Switch in a downgradable state if you update your firmware manually.

........

.. tip::
    If this page doesn't answer your question, feel free to ask on the `Team Neptune's discord: <https://discord.gg/Qs5c68dAEG>`_.

.. toctree::
   :maxdepth: 2
   :caption: Contents: