# arduinos
Mým závěrečným projektem bude vytvořeni teploměru pomocí arduino uno r3 a následné zapsaní na výpis internetu do kalendáře, kde bude možnost vyhlédávání určitého data a grafu.


Na můj teploměr budu potřebovat: Arduiono uno r3, tlačítko, displej.........

Září:Problematika arduina(čerpání informací).
Říjen:Schéma
Listopad:Pracování.
Prosinec: Dokončení a vytváření prezentace s dokumentací.


# 20.9 a 21.9
Seznámení s arduinem. Instalace Arduino IDE,GIT

void setup() {
   Serial.begin(115200);
}

void loop() {
  Serial.println("Hello World");
 delay(2000);
 //2sekundy
}

# 22.9 a 24.9
https://www.arduinotech.cz/inpage/nodemcu-wifi-modul-s-esp8266-496/#

tutorial https://github.com/espressif/arduino-esp32/blob/master/docs/arduino-ide/windows.md
http://navody.arduino-shop.cz/navody-k-produktum/vyvojova-deska-esp32.html




Zdroje: http://www.ebay.com/itm/ESP32-ESP32S-CP2102-Development-Board-2-4GHz-Dual-Mode-WiFi-Bluetooth-Antenna-/201853283621?hash=item2eff64ad25:g:OTMAAOSwXk5ZbzPV

https://home-assistant.io/blog/2015/10/11/measure-temperature-with-esp8266-and-report-to-mqtt/



# 10.10
int led = 13; // definování proměnné pro LED diodu
void setup() {
 // nastavení led jako výstup
 pinMode(led, OUTPUT);
 }
void blikani() // funkce pro blikání
 {
 digitalWrite(13, HIGH); // zapne LED
 delay(2000); // vyčká 2 sekundy
 digitalWrite(13, LOW); // vypne LED
 delay(1000); // vyčká 1 sekundu
 }
void loop() {
 blikani(); // zavolání funkce blikání
 delay(500); // vyčká 0,5 sekundy
 blikani(); // znovuzavolání funkce blikání
 delay(1000); // vyčká 1 sekundu
 }
 
 https://esp8266.cz/programovani/esp8266-a-arduino/
