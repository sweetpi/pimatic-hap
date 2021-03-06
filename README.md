pimatic-hap
=======================

pimatic-hap is a [pimatic](https://github.com/pimatic/pimatic) plugin that starts a Homekit Accessory Server and automatically
publishes all devices configured in pimatic as Homekit Accessories using a single Accessory bridge.

Currently it supports most devices that pimatic comes with OOB. Some device types cannot be supported because the HomeKit protocol doesn't have similar types.

Since this plugin uses [HAP-NodeJS](https://github.com/KhaosT/HAP-NodeJS), libnss-mdns and libavahi-compat-libdnssd-dev must be installed on a raspberry pi:

    sudo apt-get install libnss-mdns libavahi-compat-libdnssd-dev

To install the plugin just add the plugin to the config.json of pimatic:

    {
      "plugin": "hap"   
    }

This will fetch the most recent version from npm-registry on the next pimatic start and install the plugin.

Please use 031-45-154 as pin, when pairing with the pimatic homekit bridge.

Every iOS app that works with homekit should work with this (like Elgato Eve), so no need for an Apple developer account.

Changelog:

0.2.0
* support for TemperatureSensor, ContactSensor, HeatingThermostat
* added change notification of iOS devices where possible

0.1.0
* fixed a bug where Homekit Characteristics were not returned correctly

0.0.2
* support for shutters
* implemented identify method for switches, will toggle twice

0.0.1
* initial release
* support for switches and dimmers
