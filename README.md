# colortuya
local handling for Tuya RGB tunable white light bulbs via home assistant

## What is it for
Custome component of home assistant to locally control Color RGB light using Tuya firmware v3.3.
Tuya firmware less than v3.3 are recommended to flash using [tuyaconvert](https://github.com/grochon/tuyaconvert)

## Tested devices
* [Feit color bulbs from Costco for 5$ each](https://www.costco.com/feit-electric-wi-fi-smart-bulbs%2c-4-pack.product.100417461.html)

## Steps
* follow [tuyapi](https://github.com/codetheweb/tuyapi/blob/master/docs/SETUP.md#linking-a-tuya-device-with-smart-link) to obtain local_key and device_id.
* example configuration.yaml
```
light:
  - platform: mytuya
    host: 192.168.1.88
    local_key: 010a4054efd304343
    device_id: fcefa33211c89a54c8dbil
    name: ceiling
    protocol_version: 3.3
```

## Note
The following parameters might vary depending on your brand.
```
    DPS_INDEX_ON         = '1'
    DPS_INDEX_MODE       = '2'
    DPS_INDEX_BRIGHTNESS = '3'
    DPS_INDEX_COLOURTEMP = '4'
    DPS_INDEX_COLOUR     = '5'
```

## Todo
* Implement async. The device responds to each command instantly, you cannot place the next command until half a second later.  
* Implement custom scene. There are four different scenes. E.g., one corresponds to looping between up to about 6 colors. This could be mapped to a feature in home assistant. 
* Implement a service that sends a command to the bulb for easier debug.
* Add Circadian support.
Please see github for my current code.
## See also
[tuyaapi](https://github.com/codetheweb/tuyapi/blob/master/docs/SETUP.md)

[pytuya](https://github.com/clach04/python-tuya/wiki)

[localtuya-homeassistant](https://github.com/mileperhour/localtuya-homeassistant)

[Color rgb light reference](https://community.openhab.org/t/step-by-step-guide-for-adding-tuya-bulbs-wi-fi-smart-led-smart-life-app-to-oh2-using-tuya-mqtt-js-by-agentk/59371/220)
