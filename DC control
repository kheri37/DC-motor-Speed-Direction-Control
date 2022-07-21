int speedPin = 11; //enable pin
int dir1 = 10; //Output 1
int dir2 = 9; //Output 2
int BP1 = 5; //push button 1
int BP2 = 6; //push button 2
int B1Va1;
int B2Va1;
int mSpeed =0;
int dt = 500;
int GreenLED = 7;
int YellowLED = 8;
void setup() {
  Serial.begin(9600);
  pinMode(speedPin, OUTPUT);
  pinMode(dir1, OUTPUT);
  pinMode(dir2, OUTPUT);
  pinMode(BP1, INPUT);
  pinMode(BP2, INPUT);
  pinMode(YellowLED, OUTPUT);
  pinMode(GreenLED, OUTPUT);
  digitalWrite(BP1, HIGH);
  digitalWrite(BP2, HIGH);

}

void loop() {
  B1Va1= digitalRead(BP1);
  B2Va1= digitalRead(BP2);
  Serial.print("Motor Speed");
  Serial.print(mSpeed);

  if(B1Va1 == 0){
    mSpeed=mSpeed-5;
    delay(dt);
    
  }
  if(B2Va1 == 0){
    mSpeed=mSpeed+5;
    delay(dt);
  }
  if(mSpeed>255){
    mSpeed=255;
  }
  if(mSpeed<-255){
    mSpeed=-255;
  }
  if(mSpeed==10){
    mSpeed=10;
  }
  if(mSpeed == -10){
    mSpeed=-10;
  }
  if(mSpeed==9 || mSpeed == 14){
    mSpeed=0;
  }
  if(mSpeed==-9 || mSpeed ==-14){
    mSpeed=0;
  }
  if(mSpeed==0){
    analogWrite(speedPin, 0);
    digitalWrite(YellowLED, LOW);
    digitalWrite(GreenLED, LOW);
  }
  if(mSpeed>0){
    digitalWrite(dir1,LOW);
    digitalWrite(dir2, HIGH);
    analogWrite(speedPin, mSpeed);
    digitalWrite(YellowLED, HIGH);
    digitalWrite(GreenLED, LOW);
  }
  if(mSpeed<0){
    digitalWrite(dir1, HIGH);
    digitalWrite(dir2, LOW);
    analogWrite(speedPin, abs(mSpeed));
    digitalWrite(YellowLED,LOW);
    digitalWrite(GreenLED, HIGH);
  }

}
