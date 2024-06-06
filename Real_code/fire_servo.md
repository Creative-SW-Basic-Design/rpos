```c
#include <Servo.h>
Servo servo;
int servoPin = 7;

const int flameSensorPin = 2; // 디지털 핀 D2에 연결
const int ledPin = 13; // 내장 LED 핀 (옵션)

void setup() {
  pinMode(servoPin, OUTPUT);
  servo.attach(7);
  pinMode(flameSensorPin, INPUT);
  pinMode(ledPin, OUTPUT);
  
  Serial.begin(9600);
}

void loop() {
  int flameState = digitalRead(flameSensorPin);
  
  if (flameState == HIGH) {
    Serial.println("Flame detected!");
    digitalWrite(ledPin, HIGH); // 불꽃 감지 시 LED 켜짐
    servo.write(90);
  } else {
    Serial.println("No flame detected.");
    digitalWrite(ledPin, LOW); // 불꽃 감지 안 될 시 LED 꺼짐
    servo.write(-90);
  }
  
  delay(1000); // 0.5초 간격으로 체크
}
```
