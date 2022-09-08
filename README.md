# 아두이노 코드 정리...
아두이노는 c언어랑 비슷해서 편합니다.
   
## 시리얼(Serial)
```
Serial.begin(9600); //시리얼통신 9600  
Serial.println(); //시리얼 모니터에 출력을 해줌
```
## 아날로그(analog)
```
analogRead() //아날로그 핀을 읽음   
```
   
## 디지털(digital)
```
digitalWrite()   
digitalRead()   
```
   
## 서보모터(Servo)
```
#include <Servo.h> //서보모터를 쓰기위해 함수들을 담은 Servo.h 파일을 불러옴   
servo.write(핀번호) //서보모터를 움직이는 함수
```
   
## 그 외
```
delay(); //딜레이를 주는 함수(1초 == 1000)
```
   
# 아두이노 프로젝트
