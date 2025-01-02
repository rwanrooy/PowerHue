# **PowerHue - Power-Driven Light Color Change Automation**
This automation changes the color of lights based on power values from a sensor, such as the current power level from a [**Smart Meter**](https://smartgateways.nl/en/read-out-smart-meter-p1-dsmr/) from [**Smart Gateways**](https://smartgateways.nl/en/) or the real-time energy production of solar panels. The light color smoothly transitions between colors based on the power values, providing a visual indication of power consumption or generation. The color starts from **green** when power is low, gradually transitions to **blue**, and shifts to **red** as power consumption or generation reaches its maximum.

<p align="center">
  <img src="https://smartgateways.nl/wp-content/uploads/2025/01/PowerHue-logo.png" alt="PowerHue Logo" height="200">
  <img src="https://smartgateways.nl/wp-content/uploads/2020/11/smart-gateways-logo-240x133-1.jpg" alt="Smart Gateways Logo" height="200">
</p>







### Features:
- **Dynamic color changes** based on power values (green to blue to red).
- **Configurable power thresholds** and color settings.
- **Adjustable update frequency** for smooth transitions.
- **Rest state configuration** for ambient lighting when power values are low.
- Separate **brightness settings** for active and rest states.

### Requirements:
- Home Assistant (version 2024 or higher).
- Compatible light entities that can change color (e.g., RGB lights, Philips HUE, or WLED).
- A sensor providing real-time power values (e.g., [**Smart Meter**](https://smartgateways.nl/en/read-out-smart-meter-p1-dsmr/) from [**Smart Gateways**](https://smartgateways.nl/en/), solar panel sensor that measures real-time production).

### Installation:
1. Download the `energy_light_follow_colors.yaml` file and place it in your Home Assistant automations folder (usually `config/automations/`).
2. Add the blueprint to your Home Assistant configuration.
3. Customize the blueprint by setting the appropriate input values, such as your power sensor and the lights you want to control.
4. Reload automations in Home Assistant to apply the changes.

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
  - **Configuration** → **LED & Hardware setup** → **Transitions** → **Default transition time**: 4500 ms (set just below the configured `update_interval`).

### Recommended Gateway for your Smart Meter:
<center>
  <a href="https://smartgateways.nl/en/" target="_blank">
    <img src="https://smartgateways.nl/wp-content/uploads/2024/04/Smart-Meter-P1-Gateway-with-google-hub.png" alt="Smart Meter P1 Gateway" height="300" style="border-radius: 10px;">
  </a>
</center>

### License Terms:
1. This blueprint is free for personal and commercial use.
2. Modification of the blueprint code is **not allowed**.
3. Redistribution, republishing, or selling of this blueprint is **strictly prohibited**.
4. All copyright and license notices must be retained.
5. The blueprint may only be obtained through official **Smart Gateways** channels.

**Created by Roel van Wanrooy**  
Smart Gateways B.V. ([https://smartgateways.nl](https://smartgateways.nl/en))  
Copyright (c) 2025 Smart Gateways B.V.  
All rights reserved.
