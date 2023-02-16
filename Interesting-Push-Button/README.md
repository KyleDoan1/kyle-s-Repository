# Interesting Push Button
## Project Description
push button using a pen and copper tape

## Project Code
```
int buttonPin = 2;
int buttonState = 0;

void setup() {
  Serial.begin(9600);
  pinMode(buttonPin, INPUT);
  }

void loop() {
  delay(100);
  buttonState = digitalRead(buttonPin);
  if(buttonState == HIGH){
  Serial.println("Button Pressed");
  } else{
    Serial.println("Waiting");
  }
  }
```
## Project Visuals
![Pen touching copper tape](15EFA1F0-B9AC-40B4-9EF9-B18CDA517628.jpeg)
![Pen not touching copper tape](77D9A48A-7875-433F-A296-5AE52374DF94.jpeg)
![Code Waiting for Pen to touch](31007290-34BE-4018-82E3-A610DED7D9B2.jpeg)
![Code showing Pen touched tape](960E4D79-D2BD-4440-B3F9-B5824D8ADF71.jpeg)




