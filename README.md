# -> Arduino-DHT11-Humidity-Sensor-Nem-ve-Sicaklik-
# -> İmport DHTLib.Zip

#include <dht.h>

#include <Wire.h>

#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x27, 16, 2);

dht DHT;

#define DHT11_PIN 7

void setup(){

lcd.begin();

lcd.backlight();

lcd.clear();

}

void loop()
{

  int chk = DHT.read11(DHT11_PIN);

  lcd.setCursor(0,0); 
  
  lcd.print("Temp: ");
  
  lcd.print(DHT.temperature);
  
  lcd.print((char)223);
  
  lcd.print("C");
  
  lcd.setCursor(0,1);
  
  lcd.print("Humidity: ");
  
  lcd.print(DHT.humidity);
  
  lcd.print("%");
  
}
