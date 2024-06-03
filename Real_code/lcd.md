```c
#include <Adafruit_BusIO_Register.h>
#include <Adafruit_I2CDevice.h>
#include <Adafruit_I2CRegister.h>
#include <Adafruit_SPIDevice.h>

#include <RTClib.h>
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

RTC_DS1307 rtc;

LiquidCrystal_I2C lcd(0x27, 16, 2);

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Wire.begin();
  rtc.begin();
  rtc.adjust(DateTime(2024, 6, 3, 14, 9, 0));
  lcd.init();
  lcd.backlight();
  
}

void loop() {
  // put your main code here, to run repeatedly:
  DateTime now = rtc.now();

  lcd.setCursor(0, 0);
  lcd.print("Date: ");
  lcd.print(now.year(), DEC);
  lcd.print('/');
  lcd.print(now.month(), DEC);
  lcd.print('/');
  lcd.print(now.day(), DEC);
  
  lcd.setCursor(0,1);
  lcd.print("Time: ");
  if (now.hour() < 10) 
    lcd.print('0');
  lcd.print(now.hour(), DEC);
  lcd.print(':');
  if(now.minute() < 10)
    lcd.print('0');
  lcd.print(now.minute(), DEC);
  lcd.print(':');
  if(now.second() < 10) 
    lcd.print('0');
  lcd.print(now.second(), DEC);

  delay(1000);
}
```
