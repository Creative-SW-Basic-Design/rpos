```c
int AA = 10;
int AB = 6;

const int flameSensorPin = 2;
const int ledPin = 13;

void setup() {
    pinMode(flameSensorPin, INPUT);
    pinMode(ledPin, OUTPUT);
    pinMode(AA, OUTPUT);
    pinMode(AB, OUTPUT);
    Serial.begin(9600);
}

void loop() {
    int flameState = digitalRead(flameSensorPin);
    if (flameState == HIGH) {
        Serial.println("Flame detected");
        digitalWrite(ledPin, HIGH);
        digitalWrite(AA, LOW);
        digitalWrite(AB, LOW);
        delay(5000);
    }

    digitalWrite(AA, HIGH);
    digitalWrite(AB, LOW);

    delay(1000);
}


```
