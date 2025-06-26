📞 GSM Call Trigger with Button – SIM800L + Arduino
🛠 Description
This Arduino sketch enables a simple GSM-based call system using a SIM800L module. When a physical button is pressed, the system will automatically place a call to a predefined phone number for a fixed duration (~20 seconds), then hang up.

📷 Circuit Overview
SIM800L TX → Arduino D10

SIM800L RX → Arduino D11 (Use voltage divider: SIM800L RX is 3.3V tolerant)

Button → Arduino A1

SIM800L VCC → 4V (External power supply)

SIM800L GND → Common ground with Arduino

⚠️ Note: Do not power the SIM800L directly from the Arduino. Use an external 4V (2A) power supply.

📦 Components Required
Arduino Uno / Nano

SIM800L GSM Module

Push Button

Resistors (for voltage divider on TX line if needed)

External Power Supply (4V, 2A recommended)

Jumper Wires

Breadboard

🧾 How It Works
Initialization

Starts serial communication with both Serial Monitor and SIM800L.

Sends AT command and checks for OK response.

Sends AT+CPIN? to check SIM status (expects "READY").

Call Trigger

Monitors the button (connected to A1).

On button press (LOW logic), it:

Sends ATD+91xxxxxxxxxx; to SIM800L to make a call.

Waits 20 seconds.

Sends ATH to hang up the call
