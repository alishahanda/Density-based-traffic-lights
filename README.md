# Density-based-traffic-lights
Working 
 Each of the four lanes of the crossroad has an IR sensor (key for obstacle detection) planted at a considerable distance from the centre of the crossroad .The vehicles stopping at the lights on a particular lane , simultaneously stack up lengthwise. When this length crosses the level till which the IR sensor has been mounted , the sensor gives an analog input to the microcontroller . According to the code if this value is above 500, the density for that particular lane is detected as high. 
In this manner , the density condition for all the four lanes is given to the microcontroller and  the combination of all the four traffic lights is regulated in accordance with the code uploaded onto the Arduino.
Each lane may either have a high or a low density of traffic . There are four lanes in total . That gives us 24  = 16 cases of how the traffic might turn up at these four lanes. The code has instructions for the LEDs in each of these 16 cases . 
Taking a snippet from the code as an example :
//L L H H 
else if(IR1<500&&IR2<500&&IR3>500&&IR4>500)     ( The case where there is high density only on the 3rd and 4th lane)
 { digitalWrite(R1,HIGH);//G3 high    ( Green light on lane 3 for 5seconds)
digitalWrite(Y1,LOW);
  digitalWrite(G1,LOW);
  
  digitalWrite(R2,HIGH);
digitalWrite(Y2,LOW);
  digitalWrite(G2,LOW);
  
  digitalWrite(R3,LOW);
  digitalWrite(Y3,LOW);
  digitalWrite(G3,HIGH);
 
  digitalWrite(R4,HIGH);
 digitalWrite(Y4,LOW);
  digitalWrite(G4,LOW);
  delay(5000);

  digitalWrite(R1,HIGH);//y3 and y4 high     ( yellow on lane 3 and 4 for 1second)
digitalWrite(Y1,LOW);
  digitalWrite(G1,LOW);

  digitalWrite(R2,HIGH);
 digitalWrite(Y2,LOW);
  digitalWrite(G2,LOW);
 
  digitalWrite(R3,LOW);
    digitalWrite(Y3,HIGH);
 digitalWrite(G3,LOW);
 
  digitalWrite(Y4,HIGH);
 digitalWrite(R4,LOW);
  digitalWrite(G4,LOW);
delay(1000);
 
  digitalWrite(R1,HIGH);//g4 high      ( Green on lane 4 for 5 secom
  digitalWrite(Y1,LOW);
  digitalWrite(G1,LOW);
  
  digitalWrite(R2,HIGH);
  digitalWrite(Y2,LOW);
  digitalWrite(G2,LOW);

  digitalWrite(R3,HIGH);
  digitalWrite(Y3,LOW);
  digitalWrite(G3,LOW);
  
  digitalWrite(R4,LOW);
  digitalWrite(Y4,LOW);
  digitalWrite(G4,HIGH);
  delay(5000);}

