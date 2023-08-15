# Digital-Thermometer-using-Arduino
#include <DHT.h>
#include <LiquidCrystal.h>

#define DHTPIN 2
#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

void setup() {
    dht.begin();
    lcd.begin(16, 2);
}

void loop() {
    float temperature = dht.readTemperature();
    lcd.setCursor(0, 0);
    lcd.print("Temp: ");
    lcd.print(temperature);
    lcd.print("C");
    delay(1000);
}
