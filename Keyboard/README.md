# Keyboard (WASD)
## Project Description
Push Buttons on Leonardo Arduino to imitate a keyboard of WASD
Problem: Can't get the letters to stay inputted while holding it down and stop when not pressed down. We want it to imitate an actual keyboard where if you press down, it'll input but also if you hold it down it'll stay input but stop when you let go.

## Project Code
```
#include "Keyboard.h"

const int WPin = 3;         
const int APin = 4;
const int SPin = 5;         
const int DPin = 6;
int WpreviousButtonState = 0; 
int ApreviousButtonState = 0;
int SpreviousButtonState = 0; 
int DpreviousButtonState = 0;

void setup() {
  // make the pushButton pin an input:
  pinMode(WPin, INPUT);
  pinMode(APin, INPUT);
  pinMode(SPin, INPUT);
  pinMode(DPin, INPUT);
  // initialize control over the keyboard:
  Keyboard.begin();
}

void loop() {
  // read the pushbutton:
  int WbuttonState = digitalRead(WPin);
  int AbuttonState = digitalRead(APin);
   int SbuttonState = digitalRead(SPin);
  int DbuttonState = digitalRead(DPin);
  // if the button state has changed,

// W command
  
  if (WbuttonState == HIGH){
    WpreviousButtonState = 1;
  }
   if (WpreviousButtonState == 1){
    Keyboard.print("w");
  }
  if(WbuttonState == LOW){
    Keyboard.end();
    WpreviousButtonState = 0;
  }

// A command 
  
    if (AbuttonState == HIGH){
    ApreviousButtonState = 1;
  }
   if (ApreviousButtonState == 1){
    Keyboard.print("a");
  }
  if(AbuttonState == LOW){
    Keyboard.end();
    ApreviousButtonState = 0;
  }

  // S Command 

   if (SbuttonState == HIGH){
    SpreviousButtonState = 1;
  }
   if (SpreviousButtonState == 1){
    Keyboard.print("s");
  }
  if(SbuttonState == LOW){
    Keyboard.end();
    SpreviousButtonState = 0;
  }

// D Command

if (DbuttonState == HIGH){
    DpreviousButtonState = 1;
  }
   if (DbuttonState == HIGH && DpreviousButtonState == 1){
    Keyboard.print("d");
  }
  if(DbuttonState == LOW){
    Keyboard.end();
    DpreviousButtonState = 0;
  }

  // save the current button state for comparison next time:
  WpreviousButtonState = WbuttonState;
  ApreviousButtonState = AbuttonState;
   SpreviousButtonState = SbuttonState;
  DpreviousButtonState = DbuttonState;
}
```
