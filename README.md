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



# 7.11
#define LED 2
// stavová proměnná pro řízení LED diody
bool stav = LOW;

void setup() {
  Serial.begin(115200);
  // nastavení výstupu pro LED diodu
  pinMode(LED, OUTPUT);
}

void loop() {
  // blikání LED diodou za pomoci negace stavu
  digitalWrite(LED, stav);
  stav = !stav;
  delay(500);
}


// připojení potřebné knihovny
#include "WiFi.h"

void setup() {
  // nastavení komunikace po sériové lince
  Serial.begin(9600);
  // nastavení WiFI do módu stanice pro skenování
  WiFi.mode(WIFI_STA);
  // odpojení od sítí pro povolení skenování
  WiFi.disconnect();
  delay(100);
}
void loop() {
  // zahájení skenování
  Serial.println("scan start");
  // načtení počtu viditelných sítí do proměnné
  int n = WiFi.scanNetworks();
  Serial.println("scan done");
  // pokud nebyly načteny žádné sítě, vypiš informaci
  // po sériové lince
  if (n == 0) {
    Serial.println("no networks found");
  } 
  // v opačném případě vypiš všechny dostupné informace
  // o všech sítích v okolí
  else {
    Serial.print(n);
    Serial.println(" networks found");
    for (int i = 0; i < n; ++i) {
      // vytiskni název (SSID) a sílu signálu (RSSI)
      Serial.print(i + 1);
      Serial.print(": ");
      Serial.print(WiFi.SSID(i));
      Serial.print(" (");
      Serial.print(WiFi.RSSI(i));
      Serial.print(")");
      Serial.println((WiFi.encryptionType(i) == WIFI_AUTH_OPEN) ? " " : "*");
      delay(10);
    }
  }
  Serial.println("");
  // pauza před novým skenováním
  delay(5000);
}
 
 https://esp8266.cz/programovani/esp8266-a-arduino/
 https://github.com/whitecatboard/Lua-RTOS-ESP32
 https://github.com/wilda17/ESP8266-Google-Calendar-Arduino
