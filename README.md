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



# 3.12
https://gyazo.com/75c50facc3415511aeadd277a285b74f
 
 https://esp8266.cz/programovani/esp8266-a-arduino/
 https://github.com/whitecatboard/Lua-RTOS-ESP32
 https://github.com/wilda17/ESP8266-Google-Calendar-Arduino
 
 
# 11.12 
 // Teplotní čidlo DS18B20

// připojení knihoven
#include <OneWire.h>
#include <DallasTemperature.h>

// nastavení čísla vstupního pinu
const int pinCidlaDS = 4;
// vytvoření instance oneWireDS z knihovny OneWire
OneWire oneWireDS(pinCidlaDS);
// vytvoření instance senzoryDS z knihovny DallasTemperature
DallasTemperature senzoryDS(&oneWireDS);

void setup(void) {
  // komunikace přes sériovou linku rychlostí 9600 baud
  Serial.begin(9600);
  // zapnutí komunikace knihovny s teplotním čidlem
  senzoryDS.begin();
}

void loop(void) {
  // načtení informací ze všech připojených čidel na daném pinu
  senzoryDS.requestTemperatures();
  // výpis teploty na sériovou linku, při připojení více čidel
  // na jeden pin můžeme postupně načíst všechny teploty
  // pomocí změny čísla v závorce (0) - pořadí dle unikátní adresy čidel
  Serial.print("Teplota cidla DS18B20: ");
  Serial.print(senzoryDS.getTempCByIndex(0));
  Serial.println(" stupnu Celsia");
  // pauza pro přehlednější výpis
  delay(1000);
}
