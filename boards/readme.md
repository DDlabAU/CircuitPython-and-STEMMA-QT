# Board Oversigt
Naviger til:

- [QT Py S3](#qt-py-s3)
- [Feather S3](#feather-s3)
- [Adalogger RP2040 Feather](#adalogger-rp2040-feather)
- [Raspberry Pi Pico RP2040](#raspberry-pi-pico-rp2040)

---
# Vær opmærksom på
For nylig skiftede circuitpython fra version 9.x.x til 10.x.x. Det kan gøre det lidt sværere at hente ned på nogle af vores boards, da man skal følge [denne guide](https://learn.adafruit.com/adafruit-esp32-s3-feather/update-tinyuf2-bootloader-for-circuitpython-10-and-later 
)


Hvis i ikke magter kan man altid klikke på "Previous Versions of CircuitPython" og downloade version 9.2.9, så virker det perfekt.


## QT Py S3

*ID: b1*

Den vilde ESP32-S3 chip på et meget lille board:
- WiFi
- Bluetooth
- 4MB Flash
- 512KB SRAM
- 2MB PSRAM
- Meget meget lille
- Arduino / CircuitPython Kompatibel
- STEMMA QT forbindelse

<img src="https://cdn-learn.adafruit.com/assets/assets/000/123/012/large1024/adafruit_products_5426-05.jpg?1690380299" alt="QT Py S3" width="300"/>


- [Officiel Guide](https://learn.adafruit.com/adafruit-qt-py-esp32-s3)

- [Download nyeste version af CircuitPython til dette board](https://circuitpython.org/board/adafruit_qtpy_esp32s3_4mbflash_2mbpsram/)


## Feather S3
*ID: b2*

ESP32-S3 chippen i "feather" format:
- Wifi
- Bluetooth
- Nemt at tilslutte batteri!
- 4MB Flash / 8MB Flash
- 2MB PSRAM / 0MB PSRAM
- Arduino / CircuitPython Kompatibel
- STEMMA QT forbindelse
- Mange indgange

**OBS: vi har den i 2 versioner der ligner hinanden rigtigt meget. Læs på undersiden af boarded om det er 2MBPSRAM eller No PSRAM, og vælge den tilsvarende version af CircuitPython**

Vælg den med PSRAM hvis dit projekt kræver mere hukommelse til store datasæt, billeder eller lydbehandling.

<img src="https://cdn-learn.adafruit.com/assets/assets/000/118/373/large1024/adafruit_products_FESPS3_top.jpg?1675965407" alt="Feather S3" width="300"/>

- [Officiel Guide](https://learn.adafruit.com/adafruit-esp32-s3-feather)

- [CircuitPython 2MB PSRAM](https://circuitpython.org/board/adafruit_feather_esp32s3_4mbflash_2mbpsram/)

- [CircuitPython No PSRAM](https://circuitpython.org/board/adafruit_feather_esp32s3_nopsram/)





## Adalogger RP2040 Feather

*ID: b3*

RP2040 chip med **microSD** slot

- MicroSD slot til data logging
- Nemt at tilslutte batteri
- Ikke helt ligeså "avanceret" chip som esp32
- men stadig en god chip der er MANGE GANGE hurtigere end arduino uno's chip
- 8 MB Flash
- Arduino / CircuitPython Kompatibel
- STEMMA QT forbindelse
- Mange indgange
- Lavt strømforbrug
- Ingen bluetooth eller wifi




<img src="https://cdn-shop.adafruit.com/970x728/5980-00.jpg" alt="Adalogger RP2040" width="300"/>  

- [Officiel Guide](https://learn.adafruit.com/adafruit-feather-rp2040-adalogger)  
- [Download nyeste version af CircuitPython til dette board](https://circuitpython.org/board/adafruit_feather_rp2040_adalogger/)
- [Eksempelkode: Gem på SD](https://learn.adafruit.com/adafruit-feather-rp2040-adalogger/sd-card#sd-card-write-test-3153417)


## Raspberry Pi Pico RP2040
 
*ID: b4*

Ingen fordele over de andre, på nær prisen

Basically samme board som ovenstående adalogger ud over:
- den har ikke stemma-qt indgang
- den har ikke sd læser
- den bruger ikke usb c
- den har ikke batteri indgang

men den koster under 50 kroner!

Så kun brug den hvis i har et simpelt projekt, eller hvis i vil have et billigt board så i billigt kan købe jeres projekt når i er færdige, eller hvis i vil lave en mere permanent prototype med lodning direkte på boarded.



<img src="https://assets.raspberrypi.com/static/74679d6c81ffc5503a20b64feae2ed4f/2b8d7/pico-rp2040.webp" alt="Adalogger RP2040" width="300"/>  

- [Officiel Guide](https://www.raspberrypi.com/documentation/microcontrollers/pico-series.html#pico-1-familyr)  
- [Download nyeste version af CircuitPython til dette board](https://circuitpython.org/board/raspberry_pi_pico/)
