# line_follower_code_with_3_IRs
Using Arduino Uno board, L239d motor driver, 3 IR sensors, jumper wires, and batteries
/*PROGRAM FOR LINE FOLLOWER*/

//parameter 1 is set to LOW and parameter 2 is set to HIGH for FORWARD ROTATION

//analog pins for motor driver - here L -left wheel, and R - right wheel
#define L1 5
#define L2 6
#define R1 9
#define R2 10

//analog pins for IR sensors
#define l  13
#define mid 12
#define r 11

//defining speed of rotation by allotting analog values
#define faster 255
#define fast 200
#define stop 0

void setup() {
  
  pinMode(L1, OUTPUT);
  pinMode(L2, OUTPUT);
  pinMode(R1, OUTPUT);
  pinMode(R2, OUTPUT); 
  
  pinMode(r, INPUT);
  pinMode(mid, INPUT);
  pinMode(l, INPUT);
}

void loop() {
  
               
    //WHITE FLOOR
    
    if (digitalRead(mid) && digitalRead(r) && digitalRead(l)){
     
     analogWrite(L1, 0);
     analogWrite(L2, stop);
      analogWrite(R1, 0);
      analogWrite(R2, stop);
    }
    
    //STRAIGHT TRACK
    
    else if (!digitalRead(mid) && digitalRead(r) && digitalRead(l)){
     
     analogWrite(L1, 0);
     analogWrite(L2, faster);
      analogWrite(R1, 0);
      analogWrite(R2, faster);
    }
    
    //SMOOTH LEFT
    
    else if (digitalRead(mid) && digitalRead(r) && !digitalRead(l)){
     
     analogWrite(L1, 0);
     analogWrite(L2, stop);
      analogWrite(R1, 0);
      analogWrite(R2, fast);
    }
    
    //SMOOTH RIGHT
    
    else if (digitalRead(mid) && !digitalRead(r) && digitalRead(l)){
     
     analogWrite(L1, 0);
     analogWrite(L2, fast);
      analogWrite(R1, 0);
      analogWrite(R2, stop);
    }
    
    //SHARP LEFT
    
    else  if (!digitalRead(mid) && !digitalRead(r) && digitalRead(l)){
     
     analogWrite(L1, 0);
     analogWrite(L2, faster);
     //reverse
      analogWrite(R1, fast);
      analogWrite(R2, 0);
    }
    
    //SHARP RIGHT
    
    else  if (!digitalRead(mid) && digitalRead(r) && !digitalRead(l)){
     //reverse
     analogWrite(L1, 0);
     analogWrite(L2, fast);
      analogWrite(R1, faster);
      analogWrite(R2, 0);
    }
        
    //FINISH
    
    else if (!digitalRead(mid) && !digitalRead(r) && !digitalRead(l)){
     
     analogWrite(L1, 0);
     analogWrite(L2, 0);
      analogWrite(R1, 0);
      analogWrite(R2, 0);
    }
//moving is a continuous process    
delay(0); 
}



    
