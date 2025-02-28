# RFID-Based Attendance System with Google Sheets Integration

## Overview
This project implements an RFID-based attendance system using an ESP8266 microcontroller. The system reads RFID cards, extracts student details, and logs the data into a Google Sheet via Google Apps Script.

## Features
- Reads student ID from RFID cards using an MFRC522 module.
- Displays messages on an LCD (I2C) screen.
- Connects to a WiFi network for internet access.
- Sends attendance data to Google Sheets using an HTTPS request.
- Provides feedback on successful or failed data uploads.

## Hardware Requirements
- ESP8266 (NodeMCU or similar)
- MFRC522 RFID Reader
- RFID Cards/Tags
- LiquidCrystal I2C Display
- Buzzer (optional for feedback)
- Connecting wires

## Software Requirements
- Arduino IDE
- ESP8266WiFi Library
- MFRC522 Library
- LiquidCrystal_I2C Library
- HTTPSRedirect Library

## Circuit Diagram
![image](https://github.com/user-attachments/assets/0b8f46cb-d4c4-4ee9-92b3-c102c9744cba)

- **ESP8266** to **MFRC522 RFID Module**:
  - SS -> D4 (GPIO2)
  - RST -> D3 (GPIO0)
  - MOSI -> D7 (GPIO13)
  - MISO -> D6 (GPIO12)
  - SCK -> D5 (GPIO14)
  - GND -> GND
  - VCC -> 3.3V

- **ESP8266** to **I2C LCD Display**:
  - SDA -> D1 (GPIO5)
  - SCL -> D2 (GPIO4)
  - VCC -> 5V
  - GND -> GND

## Google Sheets Integration
1. Create a Google Apps Script:
   - Go to **Google Sheets** -> **Extensions** -> **Apps Script**.
   - Paste the provided script and deploy as a web app.
   - Copy the **Deployment ID** and update `GScriptId` in the code.

2. Modify `ssid` and `password` variables with your WiFi credentials.

## Installation & Setup
1. Install required libraries in the Arduino IDE.
2. Upload the sketch to the ESP8266.
3. Connect the hardware as per the circuit diagram.
4. Open the Serial Monitor (9600 baud rate) for debugging.
5. Scan an RFID card to test the system.

## Usage
- When powered on, the ESP8266 connects to WiFi and the Google Sheets server.
- The LCD prompts the user to scan an RFID tag.
- When an RFID tag is detected, student details are read and sent to Google Sheets.
- The LCD displays feedback (success or failure of data upload).

## Troubleshooting
- **WiFi Not Connecting:** Double-check SSID and password.
- **Data Not Uploading:** Ensure Google Sheets script is correctly deployed.
- **RFID Not Reading:** Verify wiring and check Serial Monitor for errors.

## Author
Surya Narayana Bhat

## License
This project is open-source under the MIT License.

