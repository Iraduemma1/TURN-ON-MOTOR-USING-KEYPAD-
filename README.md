# TURN-ON-MOTOR-USING-KEYPAD-
# ABSTRACT:
 Nowadays, technology development encourages people to think creatively, not only to explore new discoveries, but also to maximize existing technological performance. Turn on motor using keypad is needed with the increasing activity of each individual community with various erratic activities and times. As a result, many activities in the industry are delayed, such as turning on motor. Turn on motor using keypads one solution that suits the needs of the current automatic controllers. Turning on motor using keypad is system building is equipped with an integrated technology with the help of the tools which can be a keypad or other device, for example a smart phone to provide all the comfort, safety, security. To turn on motor using keypad can be used to control almost all equipment and turning on system which can be done only by using motor. In this study, to turn on motor using keypad was created for industry workshops applications using Arduino Uno. With this Application the user can control the machine using password by turning on the motor when we inter the password motor will turn on and when we want to stop we crick to another password. Thus the efficiency of electricity use becomes maintained Keyword. 

# PROBLEME STARTMENT
About this project for turning on motor using keypad is the system we do when we are going to solving some issues caused by luck of security in motor turn on, it means the security of motor will increase because no other people can know the password which can turn on our motor except password make to use keypad. The keypad will decrease the disorder in installation of motor, wireless, well appearance. the turn on motor using keypad it will have good appearance and for looking it will smartness when the password is wrong the motor will not on. also to turn on motor use keypad will decrease same accident can caused by luck of security because when motor use another system every one can turn on but when we use keypad no one can turn on if they don’t know the password. 

# BROCK DIAGRAM OFTURN ON MOTOR USING KEYPAD
![image](https://user-images.githubusercontent.com/104431994/166160767-d2f373de-486c-4def-9028-a3d3c6c4bf23.png)

# Description

This block diagram of turning on motor using keypad it composed by three main part: Arduino Uno, keypad, motor, the motor (DC or AC) First of all, we use keypad for controlling the motor to turn off or turn on motor. So This 4x4 matrix keypad has 16 built-in pushbutton contacts connected to row and column lines in the keypad library, the Propeller sets all the column lines to input, and all the row lines to input.  Then, it picks a row and sets it high.  After that, it checks the column lines one at a time.  If the column connection stays low, the button on the row has not been pressed. If it goes high, the microcontroller knows which row (the one it set high).
The electric motor is machine that convert electrical energy into mechanical energy most of electrical motor operate through the interaction between the motor is magnetic field and electric current in a wire winding to generate force in the form of torque applied on the motor shaft. 
Arduino has endless applications as it has been used extensively for creating projects by hobbyist, amateurs and professional in various fields of engineering. Also there are some of those amazing projects that have been developed on an Arduino platform.  Arduino uses a hardware known as the Arduino development board and software for developing the code known as the Arduino IDE (Integrated Development Environment) 
# Circuit diagrams
![image](https://user-images.githubusercontent.com/104431994/166160743-40c07298-741d-49a6-b212-27787ef88317.png)

 # Simulation in 	Proteus
![image](https://user-images.githubusercontent.com/104431994/166160710-ccca763e-3e4e-4b42-a59e-e3984b4fb3f7.png)

# Source Code

#include <Keypad.h>

char* password = "789";  // change the password here, just pick any 3 numbers

int position = 0;

const byte ROWS = 4;

const byte COLS = 3;

char keys[ROWS][COLS] = {

{'#','0','*'},

{'9','8','7'},

{'6','5','5'},

{'3','2','1'},

}


byte rowPins[ROWS] = {5, 6,7,8 };//Pin may change according to sutability

byte colPins[COLS] = { 2,3,4};

Keypad keypad = Keypad( makeKeymap(keys), rowPins, colPins, ROWS, COLS );

int RedpinLock = 12;

int GreenpinUnlock = 13;

int motor=11;

void setup()

{

pinMode(RedpinLock, OUTPUT);

pinMode(GreenpinUnlock, OUTPUT);

pinMode(motor, OUTPUT);

setLocked(true);

}

void loop()

{

char key = keypad.getKey();

if (key == '*' || key == '#')

{

position = 0;

setLocked(true);

}

if (key == password[position])

{

position ++;

}

if (position == 3)

{

setLocked(false);

}

delay(100);

}

void setLocked(int locked)

{

if (locked)  

{
digitalWrite(GreenpinUnlock,  LOW);

digitalWrite(RedpinLock ,HIGH);

digitalWrite(11,  LOW);

}

else

{
digitalWrite(GreenpinUnlock, HIGH);

digitalWrite(RedpinLock , LOW);

digitalWrite(11,HIGH);

}

}

Done by:

-IRADUKUNDA EMMAUEL

-IGIHOZO YVETTE

