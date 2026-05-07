### My Home automation setup 

 - Mikrotik RB5009 POE Switch
 - Zigbee Dongole SM06
 - Rasberry PI 5 - 8GB with POE hat + SSD Disk (512 GB)
 - Reolink POE doorbell
 - TPlink Access Point
 - ZYXEL wifi AP (from operator)
 - Growatt Invetor (Cheap 3Kw) Grid coupled
 
  My approach is;
 - Every solution must be community driven (no vendor locking)
 - must be DIY firendly to future extend.
 - No cloud subscription with IOT sensors etc.
 - Relable internal services 
 - Perfect integration with Home Asistant.
 
#### Cabling
  I used existing old PSTN and TV cable lines to connect my devices with CAT6 cables. 


#### Internal Services;
   - MQTT
   - DNS filtering
   - FTP/SMB
   - IP routing/NAT
   - VPN
   - DDNS 

#### Protocols
   - WIFI: For end device connectivity
   - IOT-WIFI: iot device wifi with 2.4GHZ radio only. ESP-HOME firendly.
   - Zigbee: My main protocol for sensors (around 30+). Cheap relaible and easy to extend (thanks to esp32-c6 xioa board or old ikea parts etc.)

#### Software Stack
   - mosquito mqtt
   - zigbe2mqtt
   - P1 smart meter connectity
   - home asistant.
   
## Planning
 
  - SFP+ upgrade for fiber.
  - Victron Multiplus 2 6K
  - Gobel 15KW DIY battery kit
  - Rasberry PI 4 with POE hat (For ESS)
  - Valiant Heat Pump 