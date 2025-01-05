# **PowerHue**
**Home Assistant Automation Blueprint for Dynamic Light Color Changes**

PowerHue is a versatile Home Assistant automation blueprint that lets you easily change the color of your lights based on sensor values such as power usage, solar production, temperature, or other variables. Whether you're looking to **change LED colour based on sensor value**, **change light color based on temperature**, or define **color values for lights using variables**, this blueprint makes it simple and effective.  

**Set RGB light colors based on sensor value** and automatically transition between colors, starting with **green** for low values, **blue** for moderate levels, and **red** for high values. This is perfect for visually tracking data such as power consumption from a [**Smart Meter Gateway**](https://smartgateways.nl/en) from [**Smart Gateways**](https://smartgateways.nl/en/), energy production from solar panels, or temperature readings.  

While PowerHue is primarily designed for use with power usage data, it can be connected to virtually any sensor in Home Assistant, offering endless customization possibilities. Whether you're trying to **automate changing light color**, **help with RGB LED color based on temperature**, or explore **changing lamp color based on a variable**, PowerHue offers a flexible and intuitive solution for your smart lighting needs in Home Assistant.

<p align="center">
  <a href="https://smartgateways.nl/en/" target="_blank">
    <img src="https://smartgateways.nl/wp-content/uploads/2025/01/PowerHue-logo.png" alt="PowerHue Logo" height="200">
  </a>
</p>

### Features:
- **Dynamic color changes** based on power values (green to blue to red).
- **Configurable power thresholds** and color settings.
- **Adjustable update frequency** for smooth transitions.
- **Rest state configuration** for ambient lighting when power values are low.
- Separate **brightness settings** for active and rest states.

<p align="center">
  <a href="https://smartgateways.nl/en/" target="_blank">
    <img src="https://smartgateways.nl/wp-content/uploads/2025/01/PowerHue-settings-by-Smart-Gateways.jpg" alt="PowerHue Settings" height="600" style="border-radius: 10px;">
  </a>
</p>

### Requirements:
- Home Assistant (version 2024 or higher).
- Compatible light entities that can change color (e.g., RGB lights, Philips HUE, or WLED).
- A sensor providing real-time power values (e.g., [**Smart Meter**](https://smartgateways.nl/en/read-out-smart-meter-p1-dsmr/) from [**Smart Gateways**](https://smartgateways.nl/en/), solar panel sensor that measures real-time production).

### Configuration:
- **Power Sensor**: The sensor that monitors power values (e.g., a **Smart Meter** or solar panel sensor).
- **Energy Lights**: The lights that will change color based on power values.
- **Power Thresholds**: Set the minimum and maximum power levels that the sensor can report. The automation will only work when the sensor values are within this range.
  - **Minimum Power Level**: Minimum power level for the automation to activate.
  - **Maximum Power Level**: Maximum power level for the automation to activate.
- **Rest Power Levels**: Configure the power levels that correspond to the rest state (when power is low or there's no activity). The light will show a static color (ambient lighting) during this period.
  - **Rest Color**: Color used for ambient lighting during low power periods.
  - **Rest Brightness**: Brightness used for ambient lighting.
- **Active Mode**: Configure the brightness and update frequency when the light is actively changing based on power consumption.
  - **Active Brightness**: Brightness when the light is actively changing color based on power values.
  - **Update Interval**: Frequency at which the light color will update (in seconds).

### Tips for Configuration:
- It is recommended to adjust the transition time for your lights or LEDs in the configuration for a smooth color transition. 
  For **WLED**, for example, you can configure it via:
  - **Configuration** → **LED & Hardware setup** → **Transitions** → **Default transition time**: 4500 ms (set just below the configured update_interval in the settings of the automation).
- For other types of lights, the transition time can sometimes be set directly in the light entity settings within Home Assistant. Alternatively, it may require adjusting a parameter in Zigbee2MQTT. This varies depending on the type of light.

### Recommended Gateway for your Smart Meter:
<p align="center">
  <a href="https://smartgateways.nl/en/" target="_blank">
    <img src="https://smartgateways.nl/wp-content/uploads/2024/04/Smart-Meter-P1-Gateway-with-google-hub.png" alt="Smart Meter P1 Gateway" height="300" style="border-radius: 10px;">
  </a>
</p>

---

### 💡 Support My Work for the Home Assistant Community

What started as a personal hobby—creating smart sensors and gateways for my own use—has grown over the years into something much bigger. Through word of mouth, these solutions gained popularity among smart home enthusiasts, eventually leading to the creation of SmartGateways.nl.

This Home Assistant integration, which changes light colors based on energy levels, is another project born from that same passion and hobby. I love developing and sharing smart solutions with like-minded enthusiasts. While these projects take significant time and effort, it’s incredibly rewarding to see others enjoy and benefit from them.

If you find this integration useful and would like to support me in creating more innovative projects, you can sponsor me by purchasing sensors through SmartGateways.nl or by making a donation via PayPal.

Your support helps me to:

• Develop new features and improvements  
• Keep the integration updated for the latest Home Assistant versions  
• Continue sharing fun and practical solutions with the community  

👉 Buy sensors and support my work via [**SmartGateways.nl**](https://smartgateways.nl/)


| [![Smart Meter Gateway](https://github.com/rwanrooy/PowerHue/raw/main/photos/smart%20meter%20p1%20dsmr%20home%20assistant.jpg)](https://smartgateways.nl/en/read-out-smart-meter-p1-dsmr/) | [![Watermeter Gateway](https://github.com/rwanrooy/PowerHue/raw/main/photos/watermeter%20kit%20home%20assistant.jpg)](https://smartgateways.nl/en/make-your-water-meter-smart/) | [![Gasmeter Gateway](https://github.com/rwanrooy/PowerHue/raw/main/photos/gasmeter%20gateway%20home%20assistant.jpg)](https://smartgateways.nl/en/make-your-gas-meter-smart/) | [![S0 Gateway](https://github.com/rwanrooy/PowerHue/raw/main/photos/s0%20gateway%20home%20assistant.jpg)](https://smartgateways.nl/en/make-your-s0-meter-smart/) |
|----------------------------------------------------|----------------------------------------------------|----------------------------------------------------|----------------------------------------------------|
| **[Smart Meter Gateway](https://smartgateways.nl/en/read-out-smart-meter-p1-dsmr/)**: Connect your Smart Meter to Home Assistant. | **[Watermeter Gateway](https://smartgateways.nl/en/make-your-water-meter-smart/)**: Track water usage with Home Assistant. | **[Gasmeter Gateway](https://smartgateways.nl/en/make-your-gas-meter-smart/)**: Track gas usage with Home Assistant. | **[S0 Gateway](https://smartgateways.nl/en/make-your-s0-meter-smart/)**: Track energy usage from s0 meters with Home Assistant. |
| It reads data from your smart meter and makes it available via a user-friendly online dashboard or integrates directly with your home automation system. This way, you can identify where to save energy, from electricity and gas to the consumption of your charging station. The gateway works with almost all smart meters in Europe that are equipped with a P1 port and follow the D(SMR) E(SMR) standard, including in the Netherlands, Belgium, Sweden, Denmark, Finland, Hungary, Ireland, Lithuania, and Switzerland. | You can track how much water you're using during activities like showering, filling a bathtub, washing hands, or watering your garden. The gateway is compatible with most analog water meters and supports popular home automation platforms like Home Assistant, Domoticz, and Homey, giving you exclusive access to the Smart Gateways Water Meter Dashboard for Home Assistant. The device uses open standards like REST-API and MQTT, allowing it to integrate with virtually any software and cloud system. | Whether you're heating your home, showering, or taking a bath, you can monitor exactly how much gas you're using. The gateway is compatible with most analog gas meters from brands such as Itron, Actaris, Elster, Gallus, and Honeywell. It works with popular home automation platforms like Home Assistant, Domoticz, and Homey, and offers exclusive access to the Smart Gateways Gas Meter Dashboard for Home Assistant. | It is compatible with most intermediate meters that feature an S0 pulse output, such as Siemens, ABB, Landis+Gyr, Iskraemeco, Kamstrup, EMH Metering, and Schneider Electric. The gateway integrates with popular home automation software like Home Assistant, Domoticz, and Homey, and gives you exclusive access to the Smart Gateways S0 Gateway Dashboard for Home Assistant. Using open standards such as REST-API and MQTT, it connects to almost any software and cloud platform. |

| [![Waterlevel Gateway](https://github.com/rwanrooy/PowerHue/raw/main/photos/waterlevel%20gateway%20home%20assistant.png)](https://smartgateways.nl/en/product/water-level-gateway/) | [![Distancemeter Gateway](https://github.com/rwanrooy/PowerHue/raw/main/photos/distancemeter%20gateway%20home%20assistant.jpg)](https://smartgateways.nl/en/product/distancemeter-wifi-gateway/) | [![Kamstrup Gateway](https://github.com/rwanrooy/PowerHue/raw/main/photos/kamstrup%20gateway%20home%20assistant.jpg)](https://smartgateways.nl/en/make-your-kamstrup-multical-and-flowiq-meter-smart/) | [![WarmteLink Gateway](https://github.com/rwanrooy/PowerHue/raw/main/photos/warmtelink%20gateway%20home%20assistant.jpg)](https://smartgateways.nl/en/make-your-district-heating-from-vattenfall-smart-with-warmtelink-gateway/) |
|----------------------------------------------------|----------------------------------------------------|----------------------------------------------------|----------------------------------------------------|
| **[Waterlevel Gateway](https://smartgateways.nl/en/product/water-level-gateway/)**: Monitor water levels in Home Assistant with Laser. | **[Distancemeter Gateway](https://smartgateways.nl/en/product/distancemeter-wifi-gateway/)**: Measure water levels in Home Assistant with sonar technology. | **[Kamstrup Gateway](https://smartgateways.nl/en/make-your-kamstrup-multical-and-flowiq-meter-smart/)**: Integrate your Kamstrup Water and Warmth meter with Home Assistant. | **[WarmteLink Gateway](https://smartgateways.nl/en/make-your-district-heating-from-vattenfall-smart-with-warmtelink-gateway/)**: Integrate Vattenfall WarmteLink into Home Assistant. |
| With a measuring range from 5 cm to 400 cm and an accuracy of 1 cm, it integrates seamlessly with Home Assistant, Domoticz, and Homey, or can be used independently via an internal web server. It supports MQTT and REST-API for easy cloud integration and offers energy-efficient operation. The gateway is perfect for automating water management tasks, including tank or pond refilling, and includes automatic firmware updates for continuous improvements. | It uses sonar technology to measure water levels in tanks, rain barrels, and ponds, with a range of 20 to 450 cm and a precision of 1 cm. It offers the same features as the Waterlevel Gateway, including compatibility with Home Assistant, Domoticz, Homey, and other automation software. Supporting MQTT and REST-API, it provides real-time data monitoring via an internal web server, making it ideal for water management and automation. | The Kamst-IR Gateway provides real-time insights into energy and water consumption from Kamstrup Multical heat and water meters, including FlowIQ water meters. It offers seamless integration with popular home automation software like Home Assistant, Domoticz, and Homey, and supports open standards like MQTT and REST-API for broad compatibility. The gateway is easy to install, and it can monitor your consumption continuously, even without automation software, through an online energy dashboard. | The WarmteLink Gateway for Vattenfall brings smart monitoring to your district heating system by providing real-time insights into energy consumption. Easily connected to Vattenfall's WarmteLink P1 smart meters, this gateway allows you to track energy use for heating, showering, and more. It integrates seamlessly with home automation platforms like Home Assistant, Domoticz, and Homey, and supports open standards such as MQTT and REST-API. The gateway also offers exclusive access to the Smart Gateways Energy Dashboard for additional data visualization. |



👉 [Donate via **PayPal**](https://www.paypal.me/roelvanwanrooy)


Thank you for supporting my passion for smart home automation and helping me bring these ideas to life for everyone to enjoy!

---

### Installation:
[![Open Your Home Assistant Instance](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://raw.githubusercontent.com/rwanrooy/PowerHue/refs/heads/main/ha-blueprints/powerhue_by_smart_gateways.yaml)

### License Terms:
1. This blueprint is free for personal and commercial use.
2. Modification of the blueprint code is **not allowed**.
3. Redistribution, republishing, or selling of this blueprint is **strictly prohibited**.
4. All copyright and license notices must be retained.
5. The blueprint may only be obtained through official **Smart Gateways** channels.

---

<table align="center" style="border-collapse: collapse; width: 100%; text-align: center;">
  <tr>
    <td style="vertical-align: middle; text-align: left; padding: 10px;">
      <strong>Created by Roel van Wanrooy</strong><br>
      Smart Gateways B.V. (<a href="https://smartgateways.nl" target="_blank">https://smartgateways.nl</a>)<br>
      Copyright (c) 2025 Smart Gateways B.V.<br>
      All rights reserved.
    </td>
    <td style="vertical-align: middle; padding: 10px;">
      <a href="https://smartgateways.nl/en/" target="_blank">
        <img src="https://smartgateways.nl/wp-content/uploads/2020/11/smart-gateways-logo-240x133-1.jpg" alt="Smart Gateways Logo" height="100">
      </a>
    </td>
  </tr>
</table>

---
