# DigiKeyboard Example Code

This code snippet demonstrates how to use the `DigiKeyboard` library to simulate keyboard input on an Arduino microcontroller. It sets up the device, sends specific key strokes, and controls an LED.

```cpp
#include "DigiKeyboard.h"

void setup() {
  // Setting Pins
  pinMode(1, OUTPUT); // LED
  
  // Initialize DigiKeyboard
  DigiKeyboard.update();
  DigiKeyboard.delay(1000);
  
  // Goes to Home
  DigiKeyboard.sendKeyStroke(KEY_ENTER, MOD_GUI_LEFT); // Home button
  DigiKeyboard.delay(1000);

  // Open Browser
  DigiKeyboard.sendKeyStroke(KEY_B, MOD_GUI_LEFT); // Windows Key + B
  DigiKeyboard.delay(3000);
  
  // Search in Browser
  DigiKeyboard.sendKeyStroke(KEY_L, MOD_CONTROL_LEFT); // Focus the address bar (Control + L)
  DigiKeyboard.delay(1000);
  
  // Print GitHub URL
  DigiKeyboard.print("https://github.com/dileep-kumar-koppula?tab=repositories\n");
      
  // Turn the LED ON
  digitalWrite(1, HIGH); // LED ON
}

void loop() {
  // No need for loop
}
