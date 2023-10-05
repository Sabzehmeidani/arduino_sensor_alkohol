# Arduino sensor alkohol

This arduino code is for alcohol detection sensor using arduino nano by MQ3 sensor.
[Youtube:Alcohol Detection With Arduino Nano Using MQ3 Sensor](https://www.youtube.com/watch?v=eyoqmBoXVio)

```cpp
//Detector MQ3
const int MQ3=0;
const int Buzzer=8;
const int LED=9;
const int LED2=10;
int value;

void setup() {
  Serial.begin(9600);
  pinMode(MQ3,INPUT);
  pinMode(Buzzer,OUTPUT);
  pinMode(LED,OUTPUT);
  pinMode(LED2,OUTPUT);
  digitalWrite(Buzzer,LOW);
  digitalWrite(LED,LOW);
  digitalWrite(LED2,LOW);
  Serial.println("MQ3 warming up!");
  delay(10000); //allow the MQ3 to warm up

}

void loop() 
{
 value=analogRead(MQ3);
 Serial.println(value);

  if(value>440)
  {
    digitalWrite(Buzzer,HIGH);
    digitalWrite(LED,HIGH);
    digitalWrite(LED2,LOW);
  }else{
    digitalWrite(Buzzer,LOW);
    digitalWrite(LED,LOW);
    digitalWrite(LED2,HIGH);
  }
delay(500);
}
```
