---
layout: work
title: "Anti-tribulation"
description: "IoT-based natural disaster early warning system, inspired by natural mechanisms"
image: "/assets/Anti_tribulation/Anti_tribulation.jpg"
image_subtitle:
year: "2019-21"
role: 
emoji: "🌊"
month_season:
for: 
team: "Supakorn Panya, Ratchanon Insuphan, Weerawit Sanumit"
advisors: "Chaiwut Mamuangkon, Narin lntarajak, Pran Makarkard"
tool: IoT, Arduino IDE, ESP32, LoRa, Google Firebase
order: "0"
---

**Anti-Tribulation** is an experimental Internet of Things (IoT) disaster early-warning system designed to detect environmental hazards such as **wildfires and flooding** in remote areas. The project explores how distributed sensing, low-power communication, and simple physical detection mechanisms can be combined to provide fast and reliable alerts for communities at risk.

The system was inspired by the structure of **spider webs**: multiple sensing nodes distributed across an area form a resilient network capable of detecting events quickly and transmitting information back to a central hub.

The prototype relies on inexpensive materials, simple mechanical sensing mechanisms, and commonly available microcontrollers. This approach allows the system to remain economically accessible, while still providing reliable disaster detection capabilities.

---

### LoRa

**LoRa (Long Range)** is a low-power wide-area networking modulation technique based on Chirp Spread Spectrum (CSS) technology. It allows data transmission over distances of up to approximately 10 kilometers while consuming very little power. This is important because remote sensor nodes rely on battery power and solar panels.

<figure>
	<img src="/assets/Anti_tribulation/LoRa Diagram.png" alt="Diagram comparing wireless technologies with two overlapping ovals labeled “Wi-Fi / BLE” and “Cellular 4G/5G” above a larger oval labeled “LoRa” with radio signal icons, showing LoRa alongside other connectivity options.">
	<figcaption class="image-subtitle">Conceptual diagram illustrating LoRa in relation to Wi-Fi, BLE, and cellular networks.</figcaption>
</figure>

---

### Spider-Web Protocol

This project serves as a proof-of-concept implementation of what is call the *Spider-Web Protocol*.

The idea is inspired by the structure of a spider web, with multiple sensing points distributed across an area work together to detect disturbances. Each node acts as part of a larger sensing network, where signals from different sensors collectively inform the decision to trigger alerts.

This architecture improves reliability by allowing the system to cross-reference signals from multiple sensors, reducing false positives and enabling faster detection of environmental hazards.

The Anti-Tribulation prototype demonstrates how this concept can be implemented using low-cost IoT hardware and long-range communication technologies.

<figure>
	<img src="/assets/Anti_tribulation/spider_web.JPG" alt="A circular spider web stretched between a tree trunk and thin branches, with a blurred green forest background.">
	<figcaption class="image-subtitle">A delicate spider web attached to a tree and twigs. Credit: TGoeller (Public Domain) form <a href="https://commons.wikimedia.org/wiki/File:Spider_web_with_dew_and_trunk.JPG">Wikimedia Commons</a></figcaption>
</figure>

---

### System Architecture

The system consists of two main components:

#### 1. Remote Sensor Node (Outdoor Unit)
Installed in remote or hazardous areas, this unit continuously monitors environmental conditions and disaster sensors.

#### 2. Central Monitoring Unit (Indoor Hub)
Located inside a building, this unit receives data from remote nodes, triggers alarms, and forwards data to the cloud. The two units communicate via LoRa radio transmission, allowing long-range, low-power communication. In practice, LoRa communication behaves similarly to long-range digital walkie-talkies.

---

### Hardware and Software

Both the remote and central units use: **TTGO ESP32 LoRa (SX1278)** development boards. Using firmwares written using Arduino IDE. The system uses **Firebase** as the cloud backend. Firebase allows the microcontroller, server, and mobile applications to exchange data seamlessly.

---

### System Operation

Remote nodes continuously collect sensor data, including:

- wildfire detection signals
- temperature
- humidity
- water level measurements

This information is transmitted via LoRa to the central unit. When potential hazards are detected, the central unit activates a **warning protocol**, which includes:

- visual alerts via indicator lights
- a loud audible alarm
- uploading sensor data to a cloud server (Firebase) via Wi-Fi

Once the data reaches the server, it is pushed to mobile applications, allowing users and nearby residents to receive real-time alerts.

<div style="padding:56.08% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/657706078?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write; encrypted-media; web-share" referrerpolicy="strict-origin-when-cross-origin" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="Anti-Tribulation data flow"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script><br>

---

### Custom-design sensors
#### 1. Wildfire Detection Sensor

One of the unique aspects of the system is a custom-designed wildfire sensor that relies on simple physical principles; Gravity, the low melting point of nylon rope and magnetic pendulum mechanism.

The nylon rope is tied to a magnetic weight and suspended from a metal pole outside the sensor enclosure. The weight hangs inside a vertical tube that contains a magnetic sensor at the bottom. Most of the sensor structure is buried underground and protected with a concrete layer, leaving only the pole and nylon rope exposed above the ground. And when a wildfire occurs and the surrounding temperature rises sufficiently—or when flames reach the rope—the nylon rope melts or burns, causing it to snap. The magnetic weight then falls due to gravity and triggers the magnetic sensor below. This signal is sent to the remote node, which evaluates the event together with temperature and humidity data to determine whether a wildfire is likely occurring. Or just a case of sensor malfuntioning form detached rope. Also, multiple wildfire sensors can be connected to a single node, allowing them to form a distributed “web-like” detection network for improved reliability and faster detection.

<div style="padding:56.08% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/659599795?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write; encrypted-media; web-share" referrerpolicy="strict-origin-when-cross-origin" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="Fire Sensor"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script><br>

#### 2. Water Level Sensor

I got inspired by the **ultrasonic echolocation** used by bats, which emit high-frequency sound waves and measure the time it takes for the echoes to return in order to determine the distance to nearby objects.

<figure style="max-width: 560px; width: 50%; margin: 0 auto 20px auto;">
	<img src="https://upload.wikimedia.org/wikipedia/commons/e/e1/Animal_echolocation.svg" alt="A depiction of a bat, its ultrasound call and echo from an object.">
	<figcaption class="image-subtitle">A depiction of a bat, its ultrasound call and echo from an object. Credit: Petteri Aimonen (Public Domain) form <a href="https://commons.wikimedia.org/wiki/File:Animal_echolocation.svg">Wikimedia Commons</a></figcaption>
</figure>

The flood detection system uses an ultrasonic distance sensor to measure water levels. The sensor is housed inside a vertical pipe with holes at the bottom that allow water to enter. Inside the pipe, a floating plastic ball sits on the water surface. The ultrasonic transducer measures the distance to the floating ball rather than the water surface directly. This improves measurement reliability because plastic reflects ultrasonic waves more effectively than water alone. The remote node continuously monitors the water level and transmits measurements to the central unit. If the water rises above a predefined threshold, the system triggers the disaster alert protocol.

<div style="padding:56.08% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/659599866?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write; encrypted-media; web-share" referrerpolicy="strict-origin-when-cross-origin" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="Water Lv Sensor"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script><br>

---

### Why Detect Wildfires and Floods?

The system was originally designed with northern Thailand’s environment in mind.

The region contains extensive forested mountain areas where:

- wildfires frequently occur during the dry winter season** due to low humidity
- flash floods occur during the rainy season** due to mountainous terrain

By monitoring both hazards, the system can provide year-round disaster monitoring.

The water level sensor can also be used to monitor reservoirs or natural water sources.

---

### Results

The system was tested using simulated scenarios for both wildfire and flood conditions. In these tests, the prototype successfully detected events and triggered alerts within the expected time window. During testing, a remote node was placed 4 kilometers away from the central hub.

Measured latency was:

- **3–5 seconds** from remote node detection to central alarm activation  
- **7–10 seconds** for cloud upload and mobile notification delivery

---
## Summary

All in all, this device demonstrates how a low-cost, distributed IoT sensing network can be used to provide effective early warnings for natural disasters in remote or resource-limited environments. By combining simple physical sensing mechanisms, long-range LoRa communication, and cloud connectivity, the system is able to detect potential hazards and rapidly relay alerts to nearby users.

More importantly, the project explores the **Spider-Web Protocol** concept: a scalable sensing architecture where many inexpensive nodes work together to monitor large areas. Because each node can support multiple sensors and additional nodes can easily be added to the network, the system can be extended to support other environmental monitoring tasks such as air quality monitoring, landslide detection, or forest ecosystem observation.

While this prototype serves primarily as a proof-of-concept, it demonstrates that disaster monitoring infrastructure does not necessarily require expensive equipment. With thoughtful design and distributed sensing strategies, reliable early warning systems can be built using affordable materials and open IoT technologies.

---