# Detailed Setup Guide

## Hardware Assembly

### Components List
1. ESP32 Development Board
2. TM1637 6-digit LED Display
3. 3x Push Buttons
4. Jumper Wires
5. Breadboard (optional)
6. 5V Power Supply
7. USB Cable for Programming

### Wiring Instructions

1. **LED Display Connection**
   * VCC to ESP32 5V
   * GND to ESP32 GND
   * CLK to GPIO15
   * DIO to GPIO2

2. **Button Connections**
   * Blue Button:
     * One terminal to GPIO23
     * Other terminal to GND
   * Red Button:
     * One terminal to GPIO21
     * Other terminal to GND
   * Green Button:
     * One terminal to GPIO19
     * Other terminal to GND

## Software Setup

### Development Environment

1. **Install Arduino IDE**
   * Download from [Arduino's official website](https://www.arduino.cc/en/software)
   * Install for your operating system

2. **Add ESP32 Board Support**
   * Open Arduino IDE
   * Go to File > Preferences
   * Add to Additional Board Manager URLs:
     ```
     https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
     ```
   * Go to Tools > Board > Boards Manager
   * Search for "esp32"
   * Install "ESP32 by Espressif Systems"

3. **Install Required Libraries**
   * Go to Tools > Manage Libraries
   * Install the following:
     * TM1637TinyDisplay6
     * Bounce2
     * Chrono
     * Arduino_JSON

### Configuration

1. **OpenWeatherMap Setup**
   * Create account at [OpenWeatherMap](https://openweathermap.org/)
   * Get API key from your account dashboard
   * Note your location's latitude and longitude

2. **WiFi Configuration**
   * Prepare your WiFi network name and password
   * Make sure your network is 2.4GHz (ESP32 doesn't support 5GHz)

## First Time Setup

1. **Upload Code**
   * Open Arduino IDE
   * Select your ESP32 board from Tools > Board menu
   * Select the correct port from Tools > Port
   * Click Upload button

2. **Initial Configuration**
   * Power up ESP32 while holding green button
   * Connect to "ClockConfig" WiFi network
   * Password is "password"
   * Open http://192.168.4.1
   * Enter your settings:
     * WiFi credentials
     * OpenWeatherMap API key
     * Location coordinates
   * Click Save
   * Wait for device to restart

## Testing

1. **Check Basic Functions**
   * Device should show current time
   * Red button should show weather
   * Green button should show date
   * Blue button should activate stopwatch

2. **Verify Network Functions**
   * Time should be accurate (NTP sync)
   * Weather data should update
   * DST should adjust automatically

## Troubleshooting

### Common Issues

1. **Display Shows "NO CFG"**
   * Configuration not saved
   * Enter config mode and save settings

2. **Display Shows "Sync."**
   * NTP sync failed
   * Check internet connection
   * Verify WiFi settings

3. **Weather Not Updating**
   * Verify API key
   * Check internet connection
   * Confirm location coordinates

### LED Display Issues

* Check connections
* Verify power supply
* Confirm pin assignments

### Button Issues

* Check wiring
* Verify pin assignments
* Test button continuity
