# **PowerHue - Power-Driven Light Color Change Automation**

PowerHue changes the color of lights based on power values from a sensor, such as the current power level from a [**Smart Meter Gateway**](https://smartgateways.nl/en/read-out-smart-meter-p1-dsmr/) from [**Smart Gateways**](https://smartgateways.nl/en/) or the real-time energy production of solar panels. The light color smoothly transitions between colors based on the power values, providing a visual indication of power consumption or generation. The color starts from **green** when power is low, gradually transitions to **blue**, and shifts to **red** as power consumption or generation reaches its maximum.

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

### Installation:
[![Open Your Home Assistant Instance](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://raw.githubusercontent.com/rwanrooy/PowerHue/refs/heads/main/ha-blueprints/powerhue_by_smart_gateways.yaml)

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

### License Terms:
1. This blueprint is free for personal and commercial use.
2. Modification of the blueprint code is **not allowed**.
3. Redistribution, republishing, or selling of this blueprint is **strictly prohibited**.
4. All copyright and license notices must be retained.
5. The blueprint may only be obtained through official **Smart Gateways** channels.

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

👉 [Donate via **PayPal**](https://www.paypal.me/roelvanwanrooy)


Thank you for supporting my passion for smart home automation and helping me bring these ideas to life for everyone to enjoy!

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
