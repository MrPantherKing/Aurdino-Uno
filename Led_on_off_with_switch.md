# How it works
it takes the pin 9 and output and 2 as input. when the switch is pressed the gnd and 2 connects sending a signal to the board which makes the light turn on and off

## code
const int ledPin = 9;
const int buttonPin = 2;
bool ledState = false;   // Track LED state
bool lastButtonState = HIGH;

void setup() {
pinMode(ledPin, OUTPUT);
pinMode(buttonPin, INPUT_PULLUP);
}

void loop() {
bool buttonState = digitalRead(buttonPin);

if (buttonState == LOW && lastButtonState==HIGH){
ledState = !ledState;
digitalWrite(ledPin,ledState ? HIGH:LOW);
}

lastButtonState = buttonState;  // Update button state
}