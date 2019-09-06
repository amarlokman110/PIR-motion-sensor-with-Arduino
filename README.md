# PIR-motion-sensor-with-Arduino

In this project you’re going to create a simple circuit with an Arduino and PIR motion sensor that can detect movement. An LED will light up when movement is detected.

## Introducing the PIR Motion Sensor

The PIR motion sensor is ideal to detect movement. PIR stand for “Passive Infrared”. Basically, the PIR motion sensor measures infrared light from objects in its field of view. So, it can detect motion based on changes in infrared light in the environment. It is ideal to detect if a human has moved in or out of the sensor range.

<img src="https://user-images.githubusercontent.com/54172575/64396638-d5106400-d090-11e9-83f3-8fdc1910e2d1.jpg" width="300" />

The sensor in the figure above has two built-in potentiometers to adjust the delay time (the potentiometer at the left) and the sensitivity (the potentiometer at the right).

## Pinout

* GND – connect to ground
* OUT – connect to an Arduino digital pin
* 5V – connect to 5V

## Source Code

```void loop(){
  val = digitalRead(sensor);   // read sensor value
  if (val == HIGH) {           // check if the sensor is HIGH
    digitalWrite(led, HIGH);   // turn LED ON
    delay(100);                // delay 100 milliseconds 
    
    if (state == LOW) {
      Serial.println("Motion detected!"); 
      state = HIGH;       // update variable state to HIGH
    }
  } 
  else {
      digitalWrite(led, LOW); // turn LED OFF
      delay(200);             // delay 200 milliseconds 
      
      if (state == HIGH){
        Serial.println("Motion stopped!");
        state = LOW;       // update variable state to LOW
    }
  }
}```
