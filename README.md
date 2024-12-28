# IoT-Based Light and Infrared Sensor System

This project integrates **Arduino IoT Cloud** with **Light Dependent Resistor (LDR)** and **Infrared (IR)** sensors. It allows real-time monitoring and control of an LED light based on input from the LDR and IR sensors. The system uses **Arduino IoT Cloud** to control and monitor the connected devices remotely.

### Features:
- **LDR Control**: The LDR sensor controls an LED based on the ambient light level.
- **Infrared Sensor Monitoring**: Monitors the state of an infrared sensor, toggling an LED when an object is detected.
- **Arduino IoT Cloud Integration**: Connects to the Arduino IoT Cloud to control devices remotely and monitor real-time data.

### Components Used:
- **LDR (Light Dependent Resistor)**: Measures light intensity and controls an LED based on ambient light.
- **Infrared Sensor**: Detects objects and controls an LED when an object is detected.
- **Arduino Board (e.g., NodeMCU or ESP8266)**: Connects to the Arduino IoT Cloud for remote monitoring and control.
- **LEDs**: Used to indicate the state of the sensors (LDR and IR).
- **Arduino IoT Cloud**: Provides remote control and monitoring capabilities via a web dashboard.

### Circuit Connections:
- **LDR** connected to pin **D1**.
- **LDR LED** connected to pin **D5**.
- **IR Sensor** connected to pin **D3** (input).
- **IR LED** connected to pin **D2** (output).
- **LED Light** connected to pin **D0** (output).

### Code Overview:
- **LDR Control**: The LDR sensor detects the light intensity and controls an LED. If the light level is low (i.e., it's dark), the LED is turned on.
- **Infrared Sensor Monitoring**: The infrared sensor detects the presence of objects and controls an LED. When an object is detected (IR sensor reads LOW), the LED is turned on.
- **Arduino IoT Cloud**: The system integrates with Arduino IoT Cloud, enabling remote control of the LED light and monitoring sensor values.

### Setup Instructions:
1. **Hardware Setup**: 
   - Connect the **LDR** to pin **D1** and the **LDR LED** to pin **D5**.
   - Connect the **IR sensor** to pin **D3** and the **IR LED** to pin **D2**.
   - Connect the **LED light** to pin **D0**.
   
2. **Install Arduino IDE**: 
   - Download and install the **Arduino IDE** if you haven't already.
   
3. **Set Up Arduino IoT Cloud**:
   - Create an account on [Arduino IoT Cloud](https://create.arduino.cc/iot).
   - Create a new Thing (device) in Arduino IoT Cloud and link it to your Arduino board.
   - Define the variables (`led`, `light`) and set them up in the IoT Cloud.
   
4. **Upload Code**: 
   - Open the Arduino IDE, paste the provided code, and upload it to the Arduino board.
   - Ensure the board is connected to the internet.

5. **Monitor and Control**:
   - After uploading, open the Arduino IoT Cloud dashboard and monitor the LDR and IR sensor values.
   - Control the LED light remotely from the dashboard.

### Code Functionality:
- **IR Sensor**: 
   - The infrared sensor detects the presence of objects. When the sensor reads **LOW** (object detected), it turns on an LED.
   - When the sensor reads **HIGH** (no object), the LED is turned off.

- **LDR Sensor**: 
   - The LDR sensor reads the ambient light level. When the light is low (dark), the connected LED turns on.
   - The system uses **digitalRead(D1)** to check the light level.

- **Arduino IoT Cloud Integration**: 
   - The `led` variable in the IoT Cloud is used to control the LED light. When the value of `led` is changed via the dashboard, the `onLedChange` function is triggered, turning the LED light on or off.
   - The `light` variable tracks the light sensor's state and is printed to the serial monitor for real-time debugging.

### Example Output:
- **Serial Monitor**:
