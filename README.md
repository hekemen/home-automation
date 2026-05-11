# Smart Home Automation Setup

An open-source, community-driven smart home ecosystem focused on reliability, privacy, and extensibility.

## Core Principles

* **No Vendor Lock-in:** Every solution must be community-driven and open-source.
* **DIY Friendly:** Architecture designed for easy future expansion.
* **Local Control:** Zero cloud subscriptions; all IoT sensors remain local.
* **Reliability:** High-uptime internal services.
* **Seamless Integration:** Native compatibility with Home Assistant and frameworks like ESPHome.

---

## Hardware Architecture

### Central Hub & Connectivity

* **Main Switch:** [MikroTik RB5009 PoE](https://mikrotik.com/product/rb5009ug_s_in) (Handles routing, NAT, and power delivery).
* **Compute:** [Raspberry Pi 5 (8GB)](https://www.raspberrypi.com/products/raspberry-pi-5/) equipped with a [Waveshare PoE M.2 HAT+](https://www.waveshare.com/poe-m.2-hat-plus.htm) and a **512GB NVMe SSD**.
* **Zigbee Coordinator:** [SMLIGHT SLZB-06](https://smlight.tech/product/slzb-06) (Ethernet-based Zigbee dongle).
* **Wireless Access:** * [TP-Link Omada EAP650](https://www.tp-link.com/nl/business-networking/omada-wifi-ceiling-mount/eap650/v1/) (Primary AP).
* ZYXEL WiFi AP (ISP-provided secondary).



### Energy & Infrastructure

* **Solar:** Growatt Inverter (3kW Grid-coupled).
* **Metering:** P1 Cable for direct smart meter data acquisition.
* **Wiring:** Existing PSTN and TV conduits repurposed for **CAT6 Ethernet** backhaul.

---

## Networking & Protocols

| Protocol | Usage | Details |
| --- | --- | --- |
| **WiFi** | General Connectivity | High-speed data for laptops/phones. |
| **IoT-WiFi** | 2.4GHz Dedicated | Isolated network for ESPHome and WiFi-based smart devices. |
| **Zigbee** | Sensor Network | 30+ devices (IKEA, Sonoff, DIY ESP32-C6) via Zigbee2MQTT. |

### Internal Services

* **Network:** IP Routing/NAT, VPN (Remote Access), DDNS, and DNS Filtering.
* **Communication:** MQTT (Mosquitto) as the central message bus.
* **Storage:** FTP/SMB for local file sharing and backups.

---

## Sensor & Device Inventory

* **Climate:** Zigbee floor heating thermostats, Temperature & Humidity sensors.
* **Lighting & Power:** IKEA TRÅDFRI bulbs and smart plugs.
* **Security:** [Reolink PoE Doorbell](https://reolink.com/product/reolink-video-doorbell-poe/), Smart Door Relays.
* **Control:** Sonoff [Smart Termostat](https://www.sonoff.nl/a-85269479/zigbee-producten/sonoff-radiator-thermostaat-zigbee-smart-home/#description) and [Relays](https://sonoff.tech/en-nl/products/sonoff-zbmini-extreme-zigbee-smart-switch-zbminir2?variant=46908230500593&country=NL&currency=EUR&utm_medium=product_sync&utm_source=google&utm_content=sag_organic&utm_campaign=sag_organic).

---

## Software Stack

* **Home Assistant:** The "brain" of the operation.
* **Zigbee2MQTT:** Bridging Zigbee devices to the MQTT broker.
* **Mosquitto:** Lightweight MQTT broker.
* **DSMR/P1 Integration:** For real-time energy monitoring.

---

## Future Roadmap (Planning Phase)

* [ ] **Fiber Upgrade:** Install [Zaram XGS-PON ONU SFP+](https://www.routershop.nl/p/zaram-xgs-pon-onu-sfp-module-84384) for direct fiber termination.
* [ ] **Energy Storage System (ESS):**
* [ ] [Victron MultiPlus-II 48/5000/70](https://www.victronenergy.com/inverters-chargers/multiplus-ii) Inverter/Charger.
* [ ] [Gobel Power 15kWh DIY Battery Kit](https://www.gobelpower.com/eu-stock-gobel-power-512v-lifepo4-battery-case-diy-kit-with-eve-314ah-cells_p262.html) (EVE 314Ah cells).
* [ ] Dedicated Raspberry Pi 4 (PoE) running Venus OS for ESS management.


* [ ] **HVAC:** [Vaillant aroTHERM plus](https://www.vaillant.com/home/products/air-to-water-heat-pump-system-arotherm-plus-12096.html) Air-to-Water Heat Pump.