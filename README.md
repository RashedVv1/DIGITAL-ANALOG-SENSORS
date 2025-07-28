Digital and Analog Sensor Simulation using Arduino

✅ Task 1: Digital Sensor
📋 Description
Simulated a digital sensor using a pushbutton.
When the button is pressed, the LED turns on.
When released, the LED turns off.
🧰 Components Used
Arduino Uno
Pushbutton
10kΩ resistor
LED
Breadboard
Jumper wires
💻 Arduino Code
const int buttonPin = 5;
const int ledPin = 9;

void setup() {
  pinMode(buttonPin, INPUT);
  pinMode(ledPin, OUTPUT);
}

void loop() {
  int buttonState = digitalRead(buttonPin);
  digitalWrite(ledPin, buttonState);
}

🧪 Task 2: Analog Sensor
📋 Description
Simulated an analog sensor using a potentiometer.
The analog value controls the brightness of an LED using PWM.
🧰 Components Used
Arduino Uno
Potentiometer
LED
220Ω resistor
Breadboard
Jumper wires
⚙️ Circuit Connections
Potentiometer: One side → 5V Other side → GND Middle (wiper) → A0

LED: Anode (+) → Resistor → Pin 9 Cathode (−) → GND

💻 Arduino Code
int analogPin = A0;    // Potentiometer connected to A0
int ledPin = 9;        // LED connected to PWM pin 9
int sensorValue = 0;   // Variable to store analog value

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  sensorValue = analogRead(analogPin);                // Read analog value (0–1023)
  int brightness = map(sensorValue, 0, 1023, 0, 255); // Map to PWM range
  analogWrite(ledPin, brightness);                    // Set LED brightness
}
