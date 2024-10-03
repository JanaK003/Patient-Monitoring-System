# Patient-Monitoring-System

## Project Overview

This project is an IoT-based health monitoring system developed using the ESP32 microcontroller. The system measures various health parameters like heart rate (BPM), blood oxygen levels (SpO2), room temperature, humidity, and body temperature. These values are then displayed in real-time on a web server, accessible through any device connected to the same network.

## Components Used
1. **ESP32** - Microcontroller with WiFi capabilities
2. **MAX30100** - Pulse oximeter sensor for measuring heart rate and SpO2
3. **DHT11** - Temperature and humidity sensor
4. **DS18B20** - Temperature sensor for measuring body temperature
5. **Jumper wires** and **breadboard**

## Features
- **Real-Time Health Monitoring**: Monitors heart rate, SpO2, body temperature, room temperature, and humidity in real-time.
- **Web Interface**: Data is displayed on a user-friendly web interface accessible through the ESP32’s IP address.
- **Wi-Fi Connectivity**: Enables wireless monitoring of patient vitals through a local network.

## Getting Started

### Prerequisites
- ESP32 development board
- Arduino IDE installed on your computer
- Libraries:
  - `WiFi.h`: For ESP32 WiFi connectivity
  - `WebServer.h`: To create and handle a web server on ESP32
  - `MAX30100_PulseOximeter.h`: Library for the MAX30100 sensor
  - `OneWire.h` and `DallasTemperature.h`: Libraries for the DS18B20 sensor
  - `dht.h`: For DHT11 sensor

### Circuit Diagram
- **MAX30100**: Connect SDA to GPIO 21 and SCL to GPIO 22
- **DHT11**: Connect to GPIO 18
- **DS18B20**: Connect to GPIO 5

### Installation
1. Clone the repository or download the code file.
2. Open the project in Arduino IDE.
3. Connect your ESP32 to your computer using a USB cable.
4. Install the necessary libraries from the Arduino Library Manager:
   - MAX30100 PulseOximeter Library
   - DHT Library
   - Dallas Temperature Control Library
   - OneWire Library
5. Update the WiFi credentials in the code:
   ```cpp
   const char* ssid = "your-ssid";  
   const char* password = "your-password";
   ```
6. Upload the code to the ESP32.

### How It Works
1. After powering the ESP32, it connects to the WiFi network.
2. The ESP32 gathers data from the MAX30100, DHT11, and DS18B20 sensors.
3. This data is displayed on a web server hosted by the ESP32.
4. You can view the health metrics by accessing the ESP32's IP address on a web browser.

### Accessing the Web Interface
1. Once connected to WiFi, open the Serial Monitor in Arduino IDE to view the assigned IP address.
2. Enter the IP address into your browser’s address bar to view the real-time health metrics.

### Data Displayed
- **Room Temperature (°C)**
- **Room Humidity (%)**
- **Heart Rate (BPM)**
- **Blood Oxygen Level (SpO2)**
- **Body Temperature (°C)**

## Example Output

```
Room Temperature: 28°C
Room Humidity: 50%
Heart Rate: 75 BPM
SpO2: 98%
Body Temperature: 36.7°C
```

## Issues & Troubleshooting
1. **ESP32 not connecting to WiFi**: Double-check your SSID and password and ensure your WiFi network is functioning.
2. **Data not updating**: Ensure the sensors are connected properly and check their pin assignments in the code.
3. **Web server not accessible**: Confirm that the ESP32 is on the same network as the device you are trying to access the server from.


## Credits
This project is based on tutorials and resources from [How2Electronics](https://www.how2electronics.com).
