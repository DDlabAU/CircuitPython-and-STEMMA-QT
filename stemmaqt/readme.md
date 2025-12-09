### Hop til komponent (klik)
**INPUT**
- [i1 — Temperatur & luftfugtighed](#i1)
- [i2 — Temperatur & barometer/altimeter](#i2)
- [i3 — Luftkvalitet](#i3)
- [i4 — Lys + Afstand](#i4)
- [i5 — Accelerometer](#i5)
- [i6 — Rotary Encoder](#i6)
- [i7 — Gamepad](#i7)
- [i8 — Real Time Clock](#i8)
- [i9 — Svagstrøms-sensor](#i9)
- [i10 — Wii Nunchuck + adapter](#i10)


**OUTPUT**
- [o1 — LED Matrix](#o1)
- [o2 — Vibration Driver](#o2)
- [o3 — Servo Motor](#o3)
- [o4 — DC Motor](#o4)
- [o5 — Buzzer](#o5)
- [o6 — LCD-skærm](#o6)


# OUTPUT

<a id="o1"></a>
# LED Matrix 13*9 neopixels
*ID: o1*
##### Type: OUTPUT

Vis mønstre, ikoner, bogstaver, tal og animationer med en LED matrix.

<img src="https://cdn-learn.adafruit.com/assets/assets/000/104/458/large1024/adafruit_products_IS31_top_angle.jpg?1631304413" alt="LED Matrix" width="200"/>

- [Officiel Guide](https://learn.adafruit.com/adafruit-is31fl3741)

- [Eksempelkode](https://learn.adafruit.com/adafruit-is31fl3741/python-circuitpython#basic-example-code-3102692)

---

<a id="o2"></a>
# Haptic Motor Controller / Vibration Controller
*ID: o2*
##### Type: OUTPUT

styr en vibrationsmotor, tænd/sluk og vælg en af 123 indbyggede vibrationsmønstre

<img src="https://cdn-learn.adafruit.com/assets/assets/000/113/378/medium800thumb/adafruit_products_2305-05_1.jpg?1658412986" alt="OLED Display" width="200"/>

<img src="https://cdn-learn.adafruit.com/assets/assets/000/072/594/large1024/adafruit_products_DRV_Waveforms.png?1552347698" alt="patterns" height="400">

- [Officiel Guide](https://learn.adafruit.com/adafruit-drv2605-haptic-controller-breakout/overview)

- [Eksempelkode](https://learn.adafruit.com/adafruit-drv2605-haptic-controller-breakout/python-circuitpython#full-example-code-2998876)

---

<a id="o3"></a>
# Grayscale 1.5" OLED Skærm
*ID: o3*
##### Type: OUTPUT

Lille god skærm som dog kun kan vise sorte, hvide og grå nuancer.

Det kræver en lille effort at sætte sig ind i hvordan man laver GUI på skærmen, men guiden er god til at forklare, og det er ikke super svært!



<img src="https://cdn-shop.adafruit.com/970x728/4741-07.jpg" alt="Servo Motor" width="200"/>

- [Officiel Guide](https://learn.adafruit.com/adafruit-grayscale-1-5-128x128-oled-display)

- [Eksempelkode](https://learn.adafruit.com/adafruit-grayscale-1-5-128x128-oled-display/circuitpython-wiring-and-usage#example-code-3076925)

---

<a id="o4"></a>
# 7-segment-display
*ID: o4*
##### Type: OUTPUT

Simpel skærm med 4-tal eller bogstaver (bedst til tal)

<img src="https://cdn-shop.adafruit.com/970x728/880-05.jpg" alt="7-seg-display" width="200"/>

- [Officiel Guide](https://learn.adafruit.com/adafruit-led-backpack/0-dot-56-seven-segment-backpack)

- [Eksempelkode*](https://learn.adafruit.com/adafruit-led-backpack/0-dot-56-seven-segment-backpack-circuitpython-and-python-usage#initialization-3054480) 

*man skal selv sammensætte de dele af eksempelkoden man vil bruge

---

<a id="o5"></a>
# NFC link/text sender
*ID: o5*
##### Type: OUTPUT

Tilføj tekst eller et web-link, og når en telefon kommer tæt på chippen, vil den åbne websiden eller vise teksten.

Desværre findes der ikke et officielt CircuitPython-bibliotek til denne sensor, så det er mere kompliceret at bruge den. Du kan dog følge min step-by-step guide her, som viser, hvordan du får den til at fungere.

<img src="https://cdn-learn.adafruit.com/assets/assets/000/093/887/large1024/adafruit_products_ST25DV16_top_angle.jpg?1596751982" alt="NFC" width="200"/>

- [Officiel Guide](https://learn.adafruit.com/adafruit-st25dv16k-i2c-rfic-eeprom-breakout/overview)

<details>
<summary>Step-by-step: Brug af RFID-læser med CircuitPython</summary>

1. **Gå til GitHub**  
    Besøg følgende GitHub-repo: [Neradoc/circuitpython-st25dv](https://github.com/Neradoc/circuitpython-st25dv/tree/main)

2. **Download ZIP**  
    Klik på **Code** -> **Download ZIP**.

3. **Udpak ZIP-filen**  
    Udpak ZIP-filen et vilkårligt sted på din computer.

4. **Kopier nødvendige filer**  
    find filerne `rfid_payload.py` og `adafruit_st25dv16.py` og kopier dem til **lib**-mappen på dit CircuitPython-board.

5. **Tilføj biblioteker**  
    Sørg for at tilføje de nødvendige biblioteker, fx med **circup**. Husk også at importere `adafruit_24lc32`, da det bruges indirekte.

6. **Eksempelkode**  
    Brug følgende kode. Hvis du er forbundet med STEMMA QT, skal du ikke ændre opsætningen. Vælg enten linje X eller Y, og udkommenter den linje, du ikke bruger.

```python
# Importer de relevante libs
import board
import time
import adafruit_st25dv16
import rfid_payload
import adafruit_24lc32

# STEMMA QT forbindelse
i2c = board.STEMMA_I2C()
eeprom = adafruit_st25dv16.ST25DV16(i2c, 0x53)

# "Linje X" Vælg denne linje for LINK
data = rfid_payload.payload_url("https://www.youtube.com/watch?v=Kx-Mnm_FCI8")

# "Linje Y" Vælg denne linje for TEKST
# data = rfid_payload.payload_text("Dette er en besked \n dette er en ny linje")

# Udkommenter den linje, du ikke bruger

# Koden skriver indholdet til chippen (ændr ikke dette)
for i in range(len(data)):
     eeprom[i] = data[i]
     time.sleep(0.01)
```

7. **Arduino for avancerede funktioner**  
    Hvis du ønsker at udnytte flere funktioner på denne RFID-læser, skal du desværre bruge Arduino.
</details>
    








---

<a id="o6"></a>
# LCD-screen
*ID: o6*
##### Type: OUTPUT

LCD skærm med en såkald "backpack" på der gør den meget nemt at bruge - blot tilslut stemma kab

<img src="https://cdn-shop.adafruit.com/970x728/198-05.jpg" alt="Relay" width="200"/>

- [Officiel Guide](https://learn.adafruit.com/i2c-spi-lcd-backpack)

- [Eksempelkode](https://learn.adafruit.com/i2c-spi-lcd-backpack/python-circuitpython#full-example-code-3007416)

---

# INPUT

<a id="i1"></a>
# Temperatur- og luftfugtigheds sensor
*ID: i1*
##### Type: INPUT

Mål temperatur og luftfugtighed

<img src="https://cdn-learn.adafruit.com/assets/assets/000/139/087/large1024/temperature___humidity_a.png?1755549776" alt="QT Py S3" width="200"/>


- [Officiel Guide](https://learn.adafruit.com/adafruit-aht20)

- [Eksempelkode](https://learn.adafruit.com/adafruit-aht20/python-circuitpython#full-example-code-3064504)

---
<a id="i2"></a>
# Temperatur og barometer/altimeter
*ID: i2*
##### Type: INPUT

Mål temperatur og lufttryk/højde 

<img src="https://cdn-learn.adafruit.com/assets/assets/000/139/315/large1024/sensors_bmp581_top_down.jpg?1756832155" alt="QT Py S3" width="200"/>


- [Officiel Guide](https://learn.adafruit.com/adafruit-bmp580-bmp581-and-bmp585-temperature-and-pressure-sensor)

- [Eksempelkode](https://learn.adafruit.com/adafruit-bmp580-bmp581-and-bmp585-temperature-and-pressure-sensor/circuitpython-and-python#example-code-3206370)

---

<a id="i3"></a>
# Luftkvalitet
*ID: i3*
##### Type: INPUT

Mål luftkvaliteten i eco2 og voc
obs. sensoren skal varme op i nogle minutter fra den tændes. Det gør den af sig selv, men de målte værdier er upræcise indtil den er varm.

<img src="https://cdn-learn.adafruit.com/assets/assets/000/097/488/large1024/adafruit_products_SGP30_top_angle.jpg?1607373613" alt="QT Py S3" width="200"/>


- [Officiel Guide](https://learn.adafruit.com/adafruit-sgp30-gas-tvoc-eco2-mox-sensor)

- [Eksempelkode](https://learn.adafruit.com/adafruit-sgp30-gas-tvoc-eco2-mox-sensor/circuitpython-wiring-test#circuitpython-and-python-usage-2980170)

---

<a id="i4"></a>
# Lys + Afstand
*ID: i4*
##### Type: INPUT

Mål lysmængde og afstand til objekt foran senso.

<img src="https://cdn-learn.adafruit.com/assets/assets/000/133/283/large1024/adafruit_products_6064-04.jpg?1729786686" alt="QT Py S3" width="200"/>


- [Officiel Guide](https://learn.adafruit.com/adafruit-vcnl4200-long-distance-ir-proximity-and-light-sensor)

- [Eksempelkode](https://learn.adafruit.com/adafruit-vcnl4200-long-distance-ir-proximity-and-light-sensor/circuitpython-and-python#example-code-3186793)


---


<a id="i5"></a>
# Accelerometer
*ID: i5*
##### Type: INPUT

Mål bevægelse(acceleration), orientering, og taps

<img src="https://cdn-learn.adafruit.com/assets/assets/000/094/347/large1024/sensors_LIS3DH_top_angle.jpg?1598310242" alt="QT Py S3" width="200"/>


- [Officiel Guide](https://learn.adafruit.com/adafruit-lis3dh-triple-axis-accelerometer-breakout)

- [Eksempelkode](https://learn.adafruit.com/adafruit-lis3dh-triple-axis-accelerometer-breakout/python-circuitpython#full-example-code-2997974)


---

<a id="i6"></a>
# Rotary Encoder
*ID: i6*
##### Type: INPUT

Tilføj brugerinput i form af tryk og rotation på hjulet. Denne RE, har også en neopixel led

<img src="https://cdn-shop.adafruit.com/970x728/4991-09.jpg" alt="QT Py S3" width="200"/>


- [Officiel Guide](https://learn.adafruit.com/adafruit-i2c-qt-rotary-encoder)

- [Eksempelkode](https://learn.adafruit.com/adafruit-i2c-qt-rotary-encoder/python-circuitpython#neopixel-color-picker-example-3097696)


---

<a id="i7"></a>
# Gamepad
*ID: i7*
##### Type: INPUT

lille spil-kontroller med a,b,x,y,start,select-knapper og en gamepad. kan fx mappes til tastaturknapper og bruges til at styre spil på Y8

<img src="https://cdn-learn.adafruit.com/assets/assets/000/122/121/large1024/adafruit_products_GPQT_top.jpg?1687817547" alt="QT Py S3" width="200"/>


- [Officiel Guide](https://learn.adafruit.com/gamepad-qt/overview)

- [Eksempelkode](https://learn.adafruit.com/gamepad-qt/circuitpython-and-python#example-code-3148968)


---

<a id="i8"></a>
# Real Time Clock
*ID: i8*
##### Type: INPUT

Brug eksempelkoden til at indstille tiden. Med batteri i, kan denne rtc nu huske hvad klokken er, også selvom din dims ikke får strøm, og når du tænder den igen, kan du tilgå klokken! Mega smart<3

<img src="https://cdn-shop.adafruit.com/970x728/5189-00.jpg" alt="QT Py S3" width="200"/>


- [Officiel Guide](https://learn.adafruit.com/adafruit-pcf8523-real-time-clock)

- [Eksempelkode](https://learn.adafruit.com/adafruit-pcf8523-real-time-clock/rtc-with-circuitpython#usage-2933510)


---

<a id="i9"></a>
#
Strømmåler, måler spænding og strøm. Vigtigt: kun til svagstrøm: MAX 26V og max +/- 3.2A
Hvis du vil måle stærkstrøm fra stikkontakten kan du bruge en shellyplug og sende data over wifi.

<img src="https://cdn-shop.adafruit.com/970x728/904-09.jpg" alt="QT Py S3" width="200"/>


- [Officiel Guide](https://learn.adafruit.com/adafruit-ina219-current-sensor-breakout)

- [Eksempelkode](https://learn.adafruit.com/adafruit-ina219-current-sensor-breakout/python-circuitpython#full-example-code-2997919)


---

<a id="i10"></a>
# Wii Nunchuck + Adapter
*ID: i10*
##### Type: INPUT

Med dette kan du nemt styre din prototype. controlleren har 2 knappper, et joystick og et indbygget accelerometer, så du også kan fx ryste controlleren for at gøre noget. Meget nem og fed at bruge! 
 
<img src="https://cdn-learn.adafruit.com/assets/assets/000/098/517/medium800thumb/adafruit_products_4836-1.jpg?1610300614" alt="QT Py S3" width="200"/>


- [Officiel Guide](https://learn.adafruit.com/adafruit-wii-nunchuck-breakout-adapter)

- [Eksempelkode](https://learn.adafruit.com/adafruit-wii-nunchuck-breakout-adapter/python-circuitpython#full-example-code-3079120)

---
<a id="i+"></a>
# diverse input
*ID: i+*
##### Type: INPUT

### ANO roraty encoder
fed "controller" til userinput til et deisign

- [Officiel Guide](https://learn.adafruit.com/ano-rotary-encoder)

- [Eksempelkode](https://learn.adafruit.com/ano-rotary-encoder/python-circuitpython)

### Capacitive Touch sensors
tilslut op til 12 capacitive touch inputs med denne.

- [Officiel Guide](https://learn.adafruit.com/adafruit-mpr121-12-key-capacitive-touch-sensor-breakout-tutorial)

- [Eksempelkode](https://learn.adafruit.com/adafruit-mpr121-12-key-capacitive-touch-sensor-breakout-tutorial/python-circuitpython#full-example-code-2999017)

---