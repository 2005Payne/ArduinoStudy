# 아두이노 코드 정리...
아두이노는 c언어랑 비슷합니다
   
## 시리얼(Serial)
```
Serial.begin(9600);   
Serial.println();   
Serial.available()
Serial.readString()
```
## 아날로그(analog)
```
analogRead() //아날로그 핀을 읽음
analogWrite() 
```
   
## 디지털(digital)
```
pinMode()
digitalWrite()   
digitalRead()   
```
   
## 서보모터(Servo)
```
#include <Servo.h>   
Servo.write(핀번호)
Servo.attach()
Servo.detach()
```
   
## 그 외
```
delay(); //딜레이를 주는 함수(1초 == 1000)
```
## 파이썬 시리얼통신
시리얼 통신 읽어오기
```
import serial
ser=serial.Serial("COM6",9600)

while True:
    a=str(ser.readline())
    a=a[2:].strip("\\r\\n\'")
    print(a)
```
# 아두이노 연습용 프로젝트
아두이노를 가지고 놀며 만들어진 작은 프로젝트입니다.
## 밝기를 서보모터로 표시해주는 기계
```
#include <Servo.h>
byte servopin=3;
Servo servo;
void setup() {
  Serial.begin(9600);
  servo.attach(servopin);
}

void loop() {
  // put your main code here, to run repeatedly:
  int a0=analogRead(A0);
  a0/=5.7f;
  Serial.println(a0);
  servo.write(a0);
  delay(2000);
}
```

https://user-images.githubusercontent.com/88232976/189147589-cbeeff4a-4a44-44df-9ce3-879b66c3e255.mp4
## 시리얼 통신을 이용하여 서보모터 조작
```
#include <Servo.h>
Servo servo;
int servoPin=3;
void setup() {
  Serial.begin(9600);
}

void loop() {
  if(Serial.available()){
    String a=Serial.readString();
    Serial.println("a:"+a);
    int b=a.toInt();
    servo.attach(servoPin);
    servo.write(b);
  }
  delay(1000);
  servo.detach();
}
```

https://user-images.githubusercontent.com/88232976/189273480-b40a157e-1c2d-4c42-9927-bc3aa808dfb4.mp4


