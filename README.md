# Push-button-in-circuit-

Link Tinkercad : https://www.tinkercad.com/things/f8AZV9u9wmI

A circuit to control the on and off of the LED by pushbutton

# Code Arduino 

int ledPin = 13;
int butPin = 2;

bool pressed = false;
bool wasPressed = false;

bool lightToggle = false;


void setup()
{
  pinMode(ledPin, OUTPUT);
  pinMode(butPin, INPUT);
  
  Serial.begin(9600);
}

void loop()
{
  wasPressed = pressed;
  pressed = digitalRead(butPin);
  Serial.println(pressed, wasPressed);
  
  if (pressed && !wasPressed){ //Button just pressed
   lightToggle = !lightToggle;
      
  } 
  
  digitalWrite(ledPin, lightToggle);
}
