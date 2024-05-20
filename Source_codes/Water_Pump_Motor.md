```C
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

`void loop();`
AA를 HIGH, AB를 LOW로 설정하면 **모터가 정방향으로 회전한다.**
반대로 AA를 LOW, AB를 HIGH로 설정하면 **모터가 역방향으로 회전한다.**
AA와 AB가 모두 LOW이면 정지한다.

참고 자료 : [아두이노 워터펌프 모터 3~5V / Arduino Water Pump](https://m.blog.naver.com/eduino/222063604561)
