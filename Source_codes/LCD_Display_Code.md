```C
#include<LiquidCrystal.h> //LCD 라이브러리 추가
//LiquidCrystal lcd(4, 6, 10, 11, 12, 13);

void setup() {
  lcd.begin(16, 2); //16열 2행짜리 LCD를 사용하겠다
}

void loop() {
  lcd.setCursor(5, 0);
  lcd.print("Hello"); //(5, 0)부터 Hello를 찍어라
  lcd.setCursor(1,1)l //커서를 (1, 1)로 옮겨라
  lcd.print("World"); //(1, 1)부터 World를 찍어라
}


```
