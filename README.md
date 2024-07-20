Energy Monitoring and GPS Tracking with Blynk

This project integrates energy monitoring for DC circuits with GPS tracking using an ESP32. It sends real-time data to the Blynk app, including energy consumption, GPS coordinates, and distance traveled. The data is also visualized on Google Maps within the Blynk app.
Features

    Energy Monitoring: Measures voltage (Vrms), current (Irms), power, and energy consumption (kWh) using the EmonLib library.
    GPS Tracking: Tracks location (latitude and longitude) and calculates the distance traveled using the TinyGPS++ library.
    Blynk Integration: Sends real-time data to the Blynk app for monitoring and visualization, including Google Maps.

Components

    ESP32 microcontroller
    Voltage and current sensors (DC)
    GPS module
    WiFi network

Libraries

    EmonLib: For energy monitoring.
    TinyGPS++: For GPS data handling.
    SoftwareSerial: For serial communication with GPS.
    BlynkSimpleEsp32: For Blynk integration with ESP32.


Install Required Libraries

Open the Arduino IDE and navigate to Sketch > Include Library > Manage Libraries. Search for and install the following libraries:

    EmonLib
    TinyGPS++
    Blynk
    SoftwareSerial (usually included by default)

Configure the Code

Open the main.ino file in the Arduino IDE. Replace the following placeholders with your actual information:

    YOUR_BLYNK_AUTH_TOKEN with your Blynk authentication token.
    YOUR_WIFI_SSID with your WiFi network's SSID.
    YOUR_WIFI_PASSWORD with your WiFi network's password.

cpp

    char auth[] = "YOUR_BLYNK_AUTH_TOKEN";
    char ssid[] = "YOUR_WIFI_SSID";
    char pass[] = "YOUR_WIFI_PASSWORD";

    Connect Hardware
        Voltage and Current Sensors: Connect to ESP32 GPIO pins 35 (voltage) and 34 (current).
        GPS Module: Connect to ESP32 GPIO pins 16 (RX) and 17 (TX).

    Upload the Code

    Select the appropriate board and port in the Arduino IDE. Upload the main.ino file to your ESP32.

Configuration
Blynk App

    Create a New Project in the Blynk app and select ESP32 as the device.

    Add Widgets:
        Value Display widgets for voltage (V0), current (V1), power (V2), and energy consumption (V3).
        Value Display widgets for latitude (V4), longitude (V5), and distance traveled (V6).
        Map widget for displaying location (V7).

    Assign Virtual Pins: Ensure that each widget is linked to the corresponding virtual pin defined in the code.

Usage

Once the code is uploaded and running, open the Blynk app to monitor:

    Voltage (V0): Displays the voltage measured by the sensor.
    Current (V1): Displays the current measured by the sensor.
    Power (V2): Displays the power calculated from voltage and current.
    Energy Consumption (kWh) (V3): Displays the accumulated energy consumption in kilowatt-hours.
    Latitude (V4): Shows the current latitude from the GPS module.
    Longitude (V5): Shows the current longitude from the GPS module.
    Distance Traveled (V6): Displays the total distance traveled based on GPS coordinates.
    Map (V7): Visualizes the current location on Google Maps.

Troubleshooting

    No GPS Signal: Ensure that the GPS module has a clear view of the sky. Verify connections and serial communication settings.
    Blynk Connection Issues: Check WiFi credentials and Blynk authentication token. Ensure the ESP32 is connected to the internet.
    Incorrect Readings: Verify sensor calibration values and hardware connections.

