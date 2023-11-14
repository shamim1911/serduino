#include <Servo.h>

int pos = 0;
Servo servo_9;

void setup()
{
  servo_9.attach(9);
  Serial.begin(9600);
}

void loop()
{
  if (Serial.available() > 0) {
    int val = Serial.read();
    if (val >= 0 && val <= 180) {
      pos = val;
      servo_9.write(pos);
      delay(15);
    }
  }
}
