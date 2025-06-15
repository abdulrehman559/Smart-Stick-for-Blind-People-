
# Smart Stick for Blind People

This project is a simple, low-cost smart stick designed to help visually impaired individuals detect obstacles and move around safely and independently. It uses an Arduino UNO, ultrasonic sensor, buzzer, and LED to alert users of nearby obstacles in real-time.

## Features

- Obstacle detection using ultrasonic sensor
- Buzzer alert for nearby objects
- LED indication for better awareness
- Easy to use and portable

## Components Used

- Arduino UNO
- Ultrasonic Sensor (HC-SR04)
- Buzzer
- LED
- 9V Battery
- Jumper Wires
- Walking Stick

## Circuit Connections

- Ultrasonic Sensor: VCC → 5V, GND → GND, Trig → Pin 9, Echo → Pin 10  
- Buzzer: + → Pin 11, - → GND  
- LED: Anode → Pin 13, Cathode → GND

## Arduino Code


const int trigPin = 9;
const int echoPin = 10;
const int buzzer = 11;
const int ledPin = 13;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(buzzer, OUTPUT);
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  long duration = pulseIn(echoPin, HIGH);
  int distance = duration * 0.034 / 2;

  if (distance <= 5) {
    digitalWrite(buzzer, HIGH);
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(buzzer, LOW);
    digitalWrite(ledPin, LOW);
  }
}


## Developed By

**Name:** Abdul Rehman
**CMS ID:** 133-22-0031
**Department:** Computer System Engineering
**University:** Sukkur IBA University
**Semester:** Fall 2022

