# Maincrafts-Embedded-Systems-Task1-
# Task 1: Introduction to Embedded Systems & IoT Device Design

## 📋 Student Details
* **Name:** K. DEEPARAJ
* **Platform/Company:** MAINCRAFTS TECHNOLOGY
* **Domain:** Embedded Systems & IoT Internship

---

## 🚀 Project Overview: Smart Lighting System
An automatic streetlight simulation project built using **Arduino UNO** and an **LDR (Light Dependent Resistor)** sensor. The system automatically triggers the LED 'ON' during dark ambient conditions and turns it 'OFF' when daylight is detected.

### 🛠️ Components Used
* Arduino UNO R3
* Breadboard
* Photoresistor (LDR)
* Red LED
* 220-ohm Resistor (for LED)
* 10k-ohm Resistor (for LDR Voltage Divider)

---

## 💻 Source Code (Arduino C++)

```cpp
const int ldrPin = A0;  // LDR connected to Analog pin A0
const int ledPin = 13;  // LED connected to Digital pin 13

void setup() {
  pinMode(ledPin, OUTPUT);   // Set LED pin as Output
  pinMode(ldrPin, INPUT);    // Set LDR pin as Input
  Serial.begin(9600);        // Initialize Serial Monitor
}

void loop() {
  int ldrValue = analogRead(ldrPin); // Read light intensity (0 to 1023)
  
  Serial.print("Light Level: ");
  Serial.println(ldrValue);          // Print value for debugging

  // If light level drops below threshold, turn ON LED
  if (ldrValue < 300) { 
    digitalWrite(ledPin, HIGH);      // Automatic Streetlight ON
  } 
  else {
    digitalWrite(ledPin, LOW);       // Automatic Streetlight OFF
  }
  delay(500); // Wait 500ms before next reading
}
