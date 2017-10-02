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


exec: "C:\\Users\\Bezdek\\Documents\\Arduino\\hardware\\espressif\\esp32/tools/xtensa-esp32-elf/bin/xtensa-esp32-elf-g++": file does not exist
Nastala chyba při kompilaci u desky ESP32 Dev Module.


Zdroje: http://www.ebay.com/itm/ESP32-ESP32S-CP2102-Development-Board-2-4GHz-Dual-Mode-WiFi-Bluetooth-Antenna-/201853283621?hash=item2eff64ad25:g:OTMAAOSwXk5ZbzPV

https://home-assistant.io/blog/2015/10/11/measure-temperature-with-esp8266-and-report-to-mqtt/



#2.10

https://github.com/espressif/ESP31_RTOS_SDK
