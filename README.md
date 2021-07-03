# KeyPad_Example
![Key_Pad](https://user-images.githubusercontent.com/77006916/124345192-74153100-dc12-11eb-9128-10ab89d7bc2c.jpg)
> The Arduino Uno and 4x4 KeyPad modules were used.
## Description and Code
### Description
+ Controlling LEDs with 4x4 Keypad Modules
+ 4x4 키패드 모듈을 이용하여 LED 를 제어
### Code
+ Variable
```c++
const byte ROWS = 4;
const byte COLS = 4;
byte rowPins[ROWS] = {4,5,8,9};
byte colPins[COLS] = {10, 11, 12, 13};
char Keys[ROWS][COLS] = { // 배열 선언
  {'1','2','3','4'},
  {'5','6','7','8'},
  {'9','0','a','b'},
  {'c','d','e','f'}
};
char custom_Key; 
```
+ void setup() 
```c++
void setup() { 
  Serial.begin(9600); // 시리얼 통신 속도를 9600으로 설정
  pinMode(6, OUTPUT); // 6번 핀의 상태를 출력으로 설정
  pinMode(7, OUTPUT); // 7번 핀의 상태를 출력으로 설정
}
```
+ void KeyPress()
```c++
void KeyPress() { // 키 입력 함수
  custom_Key = customKeypad.getKey();
  if(custom_Key) { // 키 입력 신호가 있을때만 작동
    if(custom_Key == '7'){ // custom_Key 가 만약 '7' 이라면
      Serial.println("Number entered :"); // 시리얼 모니터에 출력
      Serial.println(custom_Key); // custom_Key 값 출력
      Serial.println("True"); 
      digitalWrite(7, HIGH); // LED 불 ON
      delay(100); // 딜레이 
      digitalWrite(7, LOW); // LED 불 OFF
      delay(100);
    } else {
      Serial.println("Number entered :");
      Serial.println(custom_Key);
      Serial.println("False");
      digitalWrite(6, HIGH);
      delay(100);         
      digitalWrite(6, LOW);
      delay(100);
    }
  }
}
```
+ void loop()
```c++
void loop() {
  KeyPress();
}
```
## Other Information
+ My Email : ( jeonsnaguk17@gmail.com )
+ My Site : ( www.sangukjeon.tech )
+ My Blog : ( www.sanguk.life )
