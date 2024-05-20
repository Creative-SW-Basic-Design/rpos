```C
#include <MQ7.h>
MQ7 mq7(A0, 5.0);

void setup() {
  Serial.begin(115200);
}

void loop() {
  Serial.print("CO: ");
  Serial.print(mq7.getPPM());
  Serial.println("ppm");
}
```

참고자료 : [[UNO] MQ-7을 통한 CO(일산화탄소) 측정기 만들기](https://blog.naver.com/jyoun/221423420449)
