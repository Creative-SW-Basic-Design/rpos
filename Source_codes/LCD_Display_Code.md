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
<img width="1440" alt="image" src="https://github.com/Creative-SW-Basic-Design/rpos/assets/128452894/f39aa3eb-5b39-4058-81b5-c906a5742c0b">


참고자료 : [아두이노 예제 12. LCD에 글자 표시하기](https://codingrun.com/112)

<img width="1100" alt="image" src="https://github.com/Creative-SW-Basic-Design/rpos/assets/128452894/70240811-28d2-49b4-8123-bdcd89474f36">

참고자료 : [틴커캐드](https://www.tinkercad.com/things/eJMz7BQtwtf-copy-of-lcd/editel?tenant=circuits)
