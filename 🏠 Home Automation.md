Home Automation is a bit of a hobby of mine. Which is why I've [documented my setup](https://sixtymeters.com) and [Home Assistant configuration](https://github.com/aerobless/home-assistant-configuration). :)

# Other HA related pages in this wiki

* [How to query data using Flux in Grafana](🪅%20Flux.md)

# Other sources

* [Home Assistant](https://www.home-assistant.io)
* [Home Assistant Architecture Discussion](https://github.com/home-assistant/architecture/issues)
* [Home Assistant Beta Releases](https://www.home-assistant.io/faq/release/): A new version of HA is released on the first Wednesday of every month.
* [Frenck's Home Assistant configuration](https://github.com/frenck/home-assistant-config)
* [Unofficial Google Home REST API](https://rithvikvibhu.github.io/GHLocalApi/#header-getting-started)
* [Zigbee Device Compatibility Repository ](https://zigbee.blakadder.com/)(ZHA vs DECONZ vs zigbee2mqtt)

# Addons

* [Tailscale Zeroconf VPN](https://github.com/hassio-addons/addon-tailscale): A zeroconf VPN solution based on WireGuard. The HA addon can be used a gateway into the local network. Works very well. See also [[☁️ SaaS & Web#VPN | Tailscale]].

# Connectivity

## Bluetooth

* [ESPHome Bluetooth Proxy Installer](https://esphome.github.io/bluetooth-proxies/): ESP32 chips can act as range extenders for Home Assistant bluetooth connections. This allows Home Assistant to pick up all kinds of bluetooth devices that you may already have in your home. I use this for my Oral-B toothbrush and Xiaomi FlowerCare plant sensors.

# Notes

* **Grafana**
  * [Enable Flux for Home Assistant Influx Addon](https://community.home-assistant.io/t/flux-in-grafana/197155/33)
    * [Aggregate data by month or year with Flux](https://www.influxdata.com/blog/aggregating-by-months-or-years-in-flux/) (can't be done with Influx QL)
* **Plants in Home Assistant**
  * [Custom plant component (manual install via HACs)](https://github.com/Olen/homeassistant-plant)
    * [OpenPlantbook (open API to fetch plant data) (manual install via HACs)](https://github.com/Olen/home-assistant-openplantbook)
  * [Lovelace flower card (manual install via HACs)](https://github.com/Olen/lovelace-flower-card/tree/new\_plant)
