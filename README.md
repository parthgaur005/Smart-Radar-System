
✨ Features

●	180° Scan: The system sweeps the sensor across a full 180-degree field of view.
●	Real-time Visualization: Distance and angle data are plotted instantaneously on the radar display.
●	Low-Cost Components: Utilizes standard, inexpensive microcontroller and sensor modules.
●	Two-Part System: Separation of data collection (Arduino) and data visualization (Processing).
________________________________________
🛠️ Components Required

Component	Quantity	Description
Arduino Uno	1	The main microcontroller.
HC-SR04 Ultrasonic Sensor	1	Used for distance measurement (SONAR principle).
SG90 Micro Servo Motor	1	Used to sweep the sensor across the area.
Jumper Wires	~10	For connections.
Breadboard (Optional)	1	For cleaner wiring.
Computer	1	To run the Processing IDE for visualization.
________________________________________
🔌 Wiring Diagram

Connect the components as follows:
Component Pin	Connects to Arduino Pin	Notes
HC-SR04 VCC	5V	Power supply.
HC-SR04 GND	GND	Ground.
HC-SR04 Trig	Digital Pin 10	Triggers the ultrasonic pulse.
HC-SR04 Echo	Digital Pin 11	Receives the echo pulse.
Servo Power (Red)	5V	Power supply for the servo.
Servo Ground (Brown/Black)	GND	Ground for the servo.
Servo Signal (Yellow/Orange)	Digital Pin 9	Controls the servo angle.
Important Note: The HC-SR04 sensor must be physically mounted on the servo motor to allow it to sweep.


 
Shutterstock
Explore

________________________________________
💻 Software Setup

This project requires two separate code environments:

1. Arduino IDE (Data Collection Code)

1.	Install the Arduino IDE.
2.	Install the Servo Library: This is usually pre-installed, but if not, install it via the Library Manager.
3.	Upload the provided Arduino sketch (e.g., radar_sensor_code.ino).
4.	Ensure the Baud Rate in the code is set to 9600 (or matching your Processing sketch).
The Arduino code handles:
●	Sweeping the servo from $0^\circ$ to $180^\circ$.
●	Reading the distance.
●	Sending the data in the format "Angle,Distance\n" over the serial port.

2. Processing IDE (Visualization Code)

1.	Download and Install the Processing IDE.
2.	Open the provided Processing sketch (e.g., radar_display.pde).
3.	Crucially: You must identify and modify the correct Serial Port connected to your Arduino in the Processing sketch's setup function (e.g., myPort = new Serial(this, Serial.list()[0], 9600);).
4.	Run the Processing sketch.
The Processing code handles:
●	Reading and parsing the "Angle,Distance" data from the serial port.
●	Drawing the static radar background and plotting the object markers.
________________________________________
▶️ Running the System

1.	Assemble the hardware and upload the Arduino code.
2.	Plug the Arduino into your computer via USB.
3.	Verify the serial port in the Processing code is correct.
4.	Run the Processing sketch.
The servo motor should immediately begin sweeping, and a graphical radar window should appear, visualizing any objects detected within range.
