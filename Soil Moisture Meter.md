# Digitech-Versions-control-
Digitech Versions control 

Version 1 test code
#include <SPI.h>
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>
#define OLED_RESET 4
#define sensor A0
Adafruit_SSD1306 display(OLED_RESET);
void setup()
{
  display.begin(SSD1306_SWITCHCAPVCC, 0x3C); // change the adddress(0x3C) as per need
  display.clearDisplay();
}
void loop() 
{
  int value = analogRead(sensor);
  int percent = map(value, 1024, 0, 0, 100);
  display.setTextSize(2);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.println("MOISTURE");
  display.print(percent);
  display.print("%");
  display.display();
  display.clearDisplay();
}
