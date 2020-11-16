# Foundations_Lab
#include "SR04.h"
//Sonic sensor library 
#define TRIG_PIN 12
#define ECHO_PIN 11 
// defines the pins for the sonic sensor.
SR04 sr04 = SR04(ECHO_PIN,TRIG_PIN);
// defines which pins the library should use
long a;
// defines the value given by the library as a long value.
void setup() {
  digitalWrite(5,HIGH);
  digitalWrite(6,HIGH);
  // These pins define the speed of the motors. If we want a different speed we would apply a pwm signal on these pins
}

void loop() {
   a=sr04.Distance();
   //sets a as the value of the sonic sensor
   digitalWrite(1,HIGH);
   digitalWrite(2,LOW);
   digitalWrite(3,HIGH);
   // these pins in this configuration makes the robot go fowards
   if (a<20) {
    // if the sensor detects and object within 20cm this code runs
   digitalWrite(1,LOW);
   digitalWrite(4,HIGH);
   digitalWrite(3,LOW);
   // this pin configuration makes the robot turn on the spot
   delay(500);
   //this is how long the robot turns when it sees an object
   }
   digitalWrite(4,LOW);
   // this is so it returns to going fowards
   delay(5);
   // the delay prevents the arduino from doing too many instructions and waste power
}
