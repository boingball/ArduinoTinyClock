# ESP32 IoT Clock 🕒

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform: ESP32](https://img.shields.io/badge/Platform-ESP32-blue.svg)](https://www.espressif.com/en/products/socs/esp32)

A smart clock project built with ESP32 that features WiFi connectivity, real-time weather updates, and a web configuration interface.

![IoT Clock](doc/images/clock.jpeg?raw=true)

## ✨ Features

* 📱 6-digit LED display showing time in 24-hour format
* 🌐 Automatic time synchronization via NTP
* 🌞 Automatic DST (Daylight Saving Time) adjustment for UK time
* 🌡️ Current weather display from OpenWeatherMap
* 🔧 Web-based configuration interface
* 🔘 Three-button interface for different functions
* 💾 Persistent settings storage using SPIFFS

## 🛠️ Hardware Requirements

### Components
* ESP32 development board
* TM1637 6-digit LED display
* 3 push buttons (Red, Green, Blue)
* USB cable for programming
* 5V power supply

### Pin Connections

| Component    | ESP32 GPIO |
|-------------|------------|
| Display CLK | GPIO15     |
| Display DIO | GPIO2      |
| Blue Button | GPIO23     |
| Red Button  | GPIO21     |
| Green Button| GPIO19     |

## 📚 Software Dependencies

### Required Libraries
* TM1637TinyDisplay6
* WiFi
* HTTPClient
* Arduino_JSON
* Bounce2
* Chrono
* WebServer
* SPIFFS
* FS

## 🚀 Getting Started

1. Install the [Arduino IDE](https://www.arduino.cc/en/software)
2. Add [ESP32 board support](https://docs.espressif.com/projects/arduino-esp32/en/latest/installing.html) to Arduino IDE
3. Install all required libraries through the Arduino Library Manager
4. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/esp32-iot-clock.git
   ```
5. Open the project in Arduino IDE
6. Upload the code to your ESP32

## ⚙️ Initial Setup

1. Power on the device while holding the green button
2. The display will show "CONFIG"
3. Connect to the WiFi network "ClockConfig" (password: "password")
4. Visit http://192.168.4.1 in your web browser
5. Fill in the configuration form:
   * WiFi network credentials
   * OpenWeatherMap API key
   * Your location's latitude and longitude
6. Save the configuration
7. The device will restart and connect to your WiFi network

## 📖 Usage

### Button Functions

#### 🔵 Blue Button: Stopwatch Mode
* First press: Enter stopwatch mode
* Second press: Start timing
* Third press: Stop timing
* Fourth press: Exit stopwatch mode

#### 🟢 Green Button: Date Display
* Press to show current date (DDMMYY)
* Press again to return to clock

#### 🔴 Red Button: Weather Display
* Press to show current temperature
* While in weather mode, press green button for wind speed
* Press red button again to return to clock

### Time Display
* Shows time in 24-hour format (HHMMSS)
* Automatically syncs with NTP server
* Handles DST transitions automatically for UK time

## 🔧 Configuration Mode

To enter configuration mode:
1. Hold the green button while powering on
2. Connect to "ClockConfig" WiFi network
3. Visit http://192.168.4.1

## ❗ Troubleshooting

| Display Message | Meaning | Solution |
|----------------|---------|----------|
| NO CFG | No configuration found | Enter config mode and set up device |
| Sync. | NTP sync failed | Check internet connection |
| Cannot Get Weather | Weather API error | Verify API key and connection |

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 🙏 Acknowledgments

* Uses [OpenWeatherMap](https://openweathermap.org/) for weather data
* Built with ESP32 and Arduino framework
* Special thanks to all library maintainers

## 📱 Contact

Your Name - [@yourtwitter](https://twitter.com/yourtwitter) - email@example.com

Project Link: [https://github.com/yourusername/esp32-iot-clock](https://github.com/yourusername/esp32-iot-clock)
