# Node-RED Flows for Ultrasonic Sensor Monitoring

This project contains Node-RED flows for monitoring an ultrasonic sensor connected to an Arduino. The flows include functionalities for displaying sensor data on a dashboard, logging the data to a CSV file, and handling notifications and errors.

## Overview

The project consists of the following main components:
1. **Arduino Input**: Reads data from the ultrasonic sensor connected to the Arduino.
2. **Dashboard**: Displays the sensor data in real-time.
3. **Logging**: Logs the sensor data to a CSV file.
4. **Notifications**: Handles notifications for device connection and disconnection.
5. **Error Handling**: Catches and displays errors.
6. **Reset Functionality**: Allows resetting the data plot and log file.

![image](https://github.com/Falcons-25/Samyak-Task2/assets/71555137/d927b5a4-ed70-4dff-9172-084103f67520)

## Flows

### Arduino Input
- **Serial In Node**: Reads data from the Arduino connected via serial port.
- **Function Nodes**: Processes the sensor data, including parsing and formatting.
- **UI Nodes**: Displays the sensor data on the Node-RED dashboard.

### Dashboard
- **UI Base and Group Nodes**: Define the structure and appearance of the dashboard.
- **UI Text Node**: Displays the distance measured by the ultrasonic sensor.
- **UI Chart Node**: Plots the sensor data over time.

### Logging
- **Function Node**: Formats the sensor data with a timestamp.
- **File Node**: Logs the formatted data to a CSV file.

### Notifications
- **Status Node**: Monitors the connection status of the Arduino.
- **Function Node**: Checks the connection status and formats the notification message.
- **UI Notification Nodes**: Displays notifications for device connection and disconnection.

### Error Handling
- **Catch Node**: Catches errors in the flow.
- **UI Notification Node**: Displays error messages on the dashboard.

### Reset Functionality
- **UI Button Node**: Provides a button on the dashboard to reset the plot and log file.
- **Function Nodes**: Clears the plot data and resets the log file.
- **File Node**: Resets the log file by overwriting it.

## Requirements

- Node-RED
- Arduino with an ultrasonic sensor
- Serial communication between Arduino and Node-RED

## Setup

1. **Install Node-RED**: Follow the installation instructions on the [Node-RED website](https://nodered.org/docs/getting-started/).
2. **Connect the Arduino**: Ensure your Arduino is connected to your computer and is communicating via a serial port (e.g., COM13).
3. **Import the Flows**:
   - Open Node-RED in your browser.
   - Go to the menu and select "Import".
   - Copy and paste the contents of `final.json` into the import dialog.
   - Deploy the flows.
4. **Configure Serial Port**:
   - Double-click the `serial in` node.
   - Set the serial port to match your Arduino's connection (e.g., COM13).

## Arduino Setup

To complete the setup, you need to program the Arduino to read the distance from the ultrasonic sensor and output this data to the serial port.

1. **Arduino Code**:
   - Upload the reference code [(here)](ultrasonic_out.ino) to your Arduino

2. **Connect the Ultrasonic Sensor**:
   - Connect the VCC and GND pins of the ultrasonic sensor to the 5V and GND pins on the Arduino.
   - Connect the Trig pin of the ultrasonic sensor to digital pin 9 on the Arduino.
   - Connect the Echo pin of the ultrasonic sensor to digital pin 10 on the Arduino.

## Usage

- Open the Node-RED dashboard in your browser.
- The dashboard will display the current distance measured by the ultrasonic sensor.
- Notifications will alert you to the connection status of the Arduino.
- The data will be logged to `D:\log.csv`.
- Use the "Reset" button to clear the plot and reset the log file.

## Notes

- Ensure the serial port settings (baud rate, data bits, etc.) match the configuration of your Arduino.
- The project assumes the log file is located at `D:\log.csv`. Adjust the file path as needed in the file nodes.
