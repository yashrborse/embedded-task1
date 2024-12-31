# embedded-task1
// include the library code:
#include <LiquidCrystal.h> //library for LCD 

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(13, 12, 11, 10, 9, 8);

//Define Pins of Arduino
const int BUTTON_PIN  = 7;
const int LED_PIN = 6;

//Create a Variable
int Counts = 0;

void setup()
{
  pinMode(BUTTON_PIN, INPUT_PULLUP); //Use the BUTTON PIN as INPUT_PULLUP
  pinMode(LED_PIN, OUTPUT); //Use the LED PIN as OUTPUT

  lcd.begin(20, 4); // set up the LCD's number of columns and rows:
  lcd.setCursor(0, 0);
  lcd.print("  THE BRIGHT LIGHT ");
  lcd.setCursor(0, 1);
  lcd.print(" Push Button Counter");
  lcd.setCursor(0, 3);
  lcd.print(" Counts: ");
  lcd.print(Counts);
  lcd.print("  ");
}

void loop()
{
  if(digitalRead(BUTTON_PIN) == LOW)
  {
    Counts = Counts + 1;
    lcd.setCursor(0, 3);
    lcd.print(" Counts: ");
    lcd.print(Counts);
    lcd.print("  ");
    digitalWrite(LED_PIN,HIGH);
    delay(200);
    digitalWrite(LED_PIN,LOW);
  }
}
![embedded task1 Screenshot 2024-12-30 224949](https://github.com/user-attachments/assets/6f143254-8b46-466d-9250-bfd11b5f06e6)
