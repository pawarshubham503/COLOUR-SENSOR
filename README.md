int redled=2;    //LED OF  SENSOR TO PIN 2 OF ARDUINO
int greenled=3;   //LED OF SENSOR   TO PIN 3 OF ARDUINO
int blueled=4;   //LED OF SENSOR  TO  PIN 4 OF ARDUINO

int value=A0;    // ANALOG OUTPUT  OF  SENSOR  PIN A0 OF ARDUINO
int red;
int blue;
int green;

int redvalue;
int greenvalue;
int bluevalue;

int redout=8;//    O/P TO RED LED
int greenout=9;//   O/P  TO BLUE LED
int blueout=10;  //  O/P TO GREEN LED



void setup() {
  // put your setup code here, to run once:
pinMode(redled,OUTPUT);
pinMode(greenled,OUTPUT);
pinMode(blueled,OUTPUT);

pinMode(value,INPUT);

pinMode(redout,OUTPUT);
pinMode(greenout,OUTPUT);
pinMode(blueout,OUTPUT);

Serial.begin(9600);


}

void loop() {
  // put your main code here, to run repeatedly:
digitalWrite(redled,HIGH);
delay(40);
red=analogRead(value);
delay(10);
Serial.print("R=");
Serial.println(red);
digitalWrite(redled,LOW);


digitalWrite(greenled,HIGH);
delay(40);
green=analogRead(value);
delay(10);
Serial.print("G=");
Serial.println(green);
digitalWrite(greenled,LOW);


digitalWrite(blueled,HIGH);
delay(40);
blue=analogRead(value);
delay(10);
Serial.print("B=");
Serial.println(blue);
digitalWrite(blueled,LOW);



if(red>green&&red>blue)
{
  redvalue=HIGH;
}
else
  redvalue=LOW;


if(green>red&&green>blue)
{
  greenvalue=HIGH;
}
else
  greenvalue=LOW;



if(blue>red&&blue>green)
{
  bluevalue=HIGH;
}
else
  bluevalue=LOW;

digitalWrite(redout,redvalue);
digitalWrite(greenout,greenvalue);
digitalWrite(blueout,bluevalue);

}
