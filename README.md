![dht11](https://user-images.githubusercontent.com/29266933/44546786-aba0c680-a721-11e8-97c2-dd12b20be5f6.jpg)
![dth11](https://user-images.githubusercontent.com/29266933/44546785-ab083000-a721-11e8-9b87-1519c774bc74.gif)

# -> Arduino-DHT11-Humidity-Sensor-Nem-ve-Sicaklik-
# -> İmport DHTLib.Zip
# -> İmport <LiquidCrystal_I2C.h>

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
