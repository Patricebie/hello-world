# RC CAR CONTROL USING INFRARED COMMUNICATION

#### Video Demo:   <https://www.youtube.com/watch?v=EkS5KnvPB8c&t=22s>

#### Description:

This project is about to  control a  RC CAR using an infrared communication.

All the electronics components and the library that we used come form https://learn.adafruit.com/  .

1)   RC CAR pictures 

Let first look  the RC CAR pictures:

![](./images/robot1.png)

![](./images/robot2.png)


2) Principle of infrared communication

The infrared receiver on the robot correspond to the A3 pin  form the hardware .

![](./images/hardwre.png)

![](./images/telecommande.png)



Infrared sending and receiving codes are divided into: guide code, user code, user reverse code, operation code(data code), operation reverse code(data reverse code).

More about infrared communication here: <https://learn.sparkfun.com/tutorials/ir-communication/all>


3) Tools used :

   1.c++ 

   2.Arduino IDE

   3.Adafruit librabry 

   4.MACOS


***Look the code in the source file !!!!!!!***


4) Code explained 

the IR_Control_Car.ino file  is written  using the Arduino IDE  <https://www.arduino.cc/en/software>

HOW THE CAR ADVANCE ?

Let explain :

The position of the motor on the robot car. As shown below


[](./images/motor1.png)

PCA9685 chip

![](./images/motor2.png)

THE PCA9685 chip and UNO board adopt I2C communication method and this fundamental function  allow the  the car to advance 

```cpp
void advance(int Speed)
{
	Speed = map(Speed, 0, 255, 0, 4095);
	pwm.setPWM(10, 0, Speed); //Right front wheel Forward 
	pwm.setPWM(11, 0, 0);
	pwm.setPWM(8, 0, Speed); //Right rear wheel Forward 
	pwm.setPWM(9, 0, 0);

	pwm.setPWM(13, 0, Speed); //Left front wheel Forward 
	pwm.setPWM(12, 0, 0);
	pwm.setPWM(15, 0, Speed); //Left rear wheel Forward 
	pwm.setPWM(14, 0, 0);
}

