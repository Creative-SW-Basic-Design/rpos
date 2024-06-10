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

## 임계값 조절 코드 by gpt
```c
const int flameSensorPin = 2; // 불꽃 감지 센서 연결 핀
const int ledPin = 13; // 내장 LED 핀 (옵션)
int threshold = 500; // 민감도 임계값 (값을 조정하여 민감도 설정)

void setup() {
  pinMode(flameSensorPin, INPUT);
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int sensorValue = analogRead(flameSensorPin); // 아날로그 값 읽기

  if (sensorValue < threshold) {
    Serial.println("Flame detected!");
    digitalWrite(ledPin, HIGH); // 불꽃 감지 시 LED 켜짐
  } else {
    Serial.println("No flame detected.");
    digitalWrite(ledPin, LOW); // 불꽃 감지 안 될 시 LED 꺼짐
  }

  delay(500); // 0.5초 간격으로 체크
}
```

```c
int AA = 10; //AA를 연결한 디지털 핀
int AB = 6;  //AB를 연결한 디지털 핀

void setup()
{
  pinMode(AA, OUTPUT); //AA를 출력 핀으로 설정
  pinMode(AB, OUTPUT); //AB를 출력 핀으로 설정
}

void loop()
{
  digitalWrite(AA, HIGH); //정방향으로 모터 회전
  digitalWrite(AB, LOW);
  delay(5000); //5초동안 상태 유지(1000ms = 1s)
}

digitalWrite(AA, LOW); //모터 정지
digitalWrite(AB, LOW);
delay(5000); //5초동안 상태 유지
```
