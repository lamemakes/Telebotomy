# Telebotomy

What do you do when your Smart TV is a little _too_ smart - especially when you aren't using it? 

## Protect Your Privacy

Your Smart TV continues to report your data while it's turned "off". The Telebotomy aims to "lobotomize" your Smart TV while it's off by severing it's network connection. It does so by reading the remote control input and acting as a 2-port ethernet switch to allow/block network connections based on input recieved.

For more thorough data protection while using a Smart TV, it is recommended to utilize a [Pi-hole](https://pi-hole.net). There are still pitfalls with this and trackers that can't be blocked, though.

## Requirements

In order to use Telebotomy, a user needs to:

- Use ethernet as the Smart TV's network connection
- Have a compatible remote
    - Currently only IR remotes are supported, but there are plans to extend this.
- Access to a USB power source

## Installation

The installation of the Telebotomy is as follows:

1. Ensure the Smart TV is powered but turned off.
1. Plug in the ethernet to the Telebotomy's respective ports
    - _to TV_ should be the connection to the TV
    - _to Network_ should be the connection to the network source
1. Locate the _Remote Input_ connector on the Telebotomy and connect the appropriate sensor
    - _If using IR_ place the sensor so it's close to the TV's reciever.
1. Connect the Telebotomy's Micro-USB port to a USB power source.
1. [Test!](#testing-the-telebotomy)
1. Profit!

## Testing the Telebotomy

1. Ensure the Smart TV is powered but turned off.
1. Power cycle the Telebotomy or press the "Reset" button.
1. Turn on the Smart TV utilizing the remote
1. Confirm internet connectivity:
    - LINK & ACT LEDs on the Telebotomy are active
    - The Smart TV can connect to the internet
    - _If using Pi-Hole_ There is network activity coming from the IP of the TV.
1. Turn off the Smart TV utilizing the remote
1. Confirm there is no internet connectivity:
    - LINK & ACT LEDs on the Telebotomy are inactive
    - Turn the TV on via a physical button and ensure it is not connected to the internet
    - _If using Pi-Hole_ There is no network activity coming from the IP of the TV.


<!--

## Protect Your Privacy

Smart TVs are constantly reporting all sorts of data about their owners. While a Smart TV is "turned on", it is likely creating a profile around the user containing assumptions about things like attention span, content interests, ad engagement, and other categories that would be valuable from an ads/content standpoint. Sometimes this is added to existing profiles of the user as Google/Facebook/Amazon are some of the most prevelant ad services.

**But when the TV is off it stops this reporting, right?**

Wrong. While your Smart TV may look off, it's very chatty on the internet. It will continue to gain whatever information it can on a user, it just won't be able to watch viewing patterns. It still has the capability to:
 - Report local WiFi/Bluetooth devices
 - Process microphone audio
 - Determine routines of the user (ie. what time do the lights go out at night?)
 - Continue to report sensitive information like UIDs or a users location (sometimes unencrypted!)

This can be somewhat stopped using tools like [Pi-hole](https://pi-hole.net) but some requests still fall through the cracks. To ensure all unwanted data reporting is stopped, the only real solution is to manually toggle the WiFi or physically plug/unplug the Ethernet to TV every use. This is the issues Telebotomy is hoping to fix!

## How does it work?

Telebotomy acts as a two port network switch that will either allow or disallow the passage of all network packets bidirectionally between the target device and internet source. The Telebotomy works to read the input from your TVs remote, and toggle the internet based on the intended action.

For more info, check out [Watching You Watch: The Tracking Ecosystem of Over-the-Top
TV Streaming Devices](https://tv-watches-you.princeton.edu/tv-tracking-acm-ccs19.pdf).

-->