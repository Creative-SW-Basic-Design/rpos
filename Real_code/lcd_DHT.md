```c
#include <DHT.h>
#include <DHT_U.h>
#include <Wire.h>
#include <LiquidCrystal_I2C.h>
#define DHTTYPE DHT11
int DHTPIN = 2;

DHT dht(DHTPIN, DHTTYPE);

LiquidCrystal_I2C lcd(0x27, 16, 2); // I2C 주소가 0x27인 16x2 LCD 디스플레이

void setup() {
  dht.begin();
  lcd.init();
  lcd.backlight(); 
  lcd.setCursor(0, 0); 
  Serial.begin(9600);
}

void loop() {
  delay(500);

  float humidity = dht.readHumidity();
  float temperature = dht.readTemperature();

  lcd.setCursor(0,0);
  lcd.print("Humidity : ");
  lcd.print(humidity);
  lcd.setCursor(0,1);
  lcd.print("Temperature : ");
  lcd.print(temperature);
  lcd.print(" °C");

  Serial.print("Humidity : ");
  Serial.println(humidity);
  Serial.print("Temperature : ");
  Serial.print(temperature);
  Serial.println(" °C");
}
```
