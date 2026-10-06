🚗 Smart Parking System using Arduino

An Arduino-based smart parking system that detects the availability of parking spaces using ultrasonic sensors and provides visual status indicators using red and green LEDs.

📌 Project Overview

The system is designed to monitor parking spaces automatically.

HC-SR04 ultrasonic sensors measure the distance between the sensor and an object/vehicle. The Arduino Nano processes the measured distance and determines whether each parking slot is available or occupied.

- 🟢 Green LED → Slot Available
- 🔴 Red LED → Slot Occupied

The current prototype supports 2 parking slots.

✨ Features

- Real-time parking slot detection
- Two independent parking slots
- Ultrasonic distance measurement
- Automatic available-slot counting
- LED-based parking status indication
- Serial Monitor output
- Low-cost hardware
- Easy to expand to additional parking slots

🛠️ Hardware

Component| Quantity
Arduino Nano| 1
HC-SR04 Ultrasonic Sensor| 2
Green LED| 2
Red LED| 2
220Ω Resistor| 4
Breadboard| 1
Jumper Wires| ~20
USB Cable| 1

🔌 Pin Configuration

Arduino Nano Pin| Component
D2| HC-SR04 #1 TRIG
D3| HC-SR04 #1 ECHO
D4| HC-SR04 #2 TRIG
D5| HC-SR04 #2 ECHO
D6| Slot 1 Green LED
D7| Slot 1 Red LED
D8| Slot 2 Green LED
D9| Slot 2 Red LED
5V| HC-SR04 VCC
GND| Common Ground

Each LED is connected through a 220Ω current-limiting resistor.

⚙️ Working Principle

The HC-SR04 sensor sends an ultrasonic pulse and measures the time taken for the reflected signal to return.

The Arduino converts this time into distance.

The system uses a configurable distance threshold:

#define OCCUPIED_DISTANCE 20

If the measured distance is less than or equal to the threshold, the parking slot is considered occupied.

Otherwise, the slot is considered available.

Logic

Distance ≤ 20 cm
       ↓
   OCCUPIED
       ↓
   Red LED ON
   Green LED OFF

Distance > 20 cm
       ↓
   AVAILABLE
       ↓
   Green LED ON
   Red LED OFF

💻 Software

- Arduino IDE
- Embedded C/C++
- Arduino Nano
- HC-SR04 sensor library-free implementation

The project uses the Arduino "pulseIn()" function to measure the ultrasonic echo pulse.

🚀 Installation

1. Clone the repository

git clone https://github.com/YOUR-USERNAME/smart-parking-system-arduino.git

2. Open the Arduino project

Open:

Smart_Parking_System/Smart_Parking_System.ino

using Arduino IDE.

3. Select the board

Select:

Arduino Nano

4. Select the correct processor

For compatible Nano boards, use:

ATmega328P

If uploading fails, try:

ATmega328P (Old Bootloader)

5. Select the COM port

Select the port corresponding to the connected Arduino Nano.

6. Upload

Compile and upload the program.

🧪 Testing

The system was tested using the following conditions:

Test| Slot 1| Slot 2| Expected Available
Test 1| Empty| Empty| 2
Test 2| Occupied| Empty| 1
Test 3| Empty| Occupied| 1
Test 4| Occupied| Occupied| 0

The parking status can also be monitored through the Arduino Serial Monitor at:

9600 baud

📊 Example Output

--------------------------------
Slot 1: AVAILABLE | Distance: 35 cm
Slot 2: AVAILABLE | Distance: 42 cm
Available Slots: 2

--------------------------------
Slot 1: OCCUPIED | Distance: 12 cm
Slot 2: AVAILABLE | Distance: 42 cm
Available Slots: 1

🔮 Future Improvements

Possible future versions can include:

- 4 or more parking slots
- 16×2 I2C LCD display
- Automatic entrance gate using a servo motor
- Buzzer alerts
- ESP32-based Wi-Fi connectivity
- Web-based parking dashboard
- Mobile monitoring
- Cloud-based parking data
- Entry/exit vehicle counting

📷 Project Photos

Add your own photographs here after building the prototype.

Suggested images:

images/circuit.jpg
images/prototype.jpg
images/testing.jpg

👨‍💻 Author

Arman Sharma

B.Tech Electronics & Communication Engineering

Rajiv Gandhi Government Engineering College

Expected Graduation: 2027

📄 License

This project is intended for educational and portfolio purposes.
