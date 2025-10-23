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
- [i10 — 9-axis orientation](#i10)

**OUTPUT**

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
# 9-axis orientation
*ID: i10*
##### Type: INPUT

*OBS: vi har ikke stemmaQT-udgaven, derfor skal du selv sætte 4 ledninger i 3v, gnd, sda, og scl.*

Et standard accelerometer er god til mange ting, særligt at registere ryst, orientering, taps og andre basisbevægelser.
Denne sensor kan meget mere, da den også har magnetometer og gyroskop, kan du bruge den som kompas, og altid få din præcise orientering. Til projekter der kræver lidt mere en blot et simpelt accelerometer.
 
<img src="https://cdn-learn.adafruit.com/assets/assets/000/024/585/large1024/sensors_2472_top_ORIG.jpg?1429638074" alt="QT Py S3" width="200"/>


- [Officiel Guide](https://learn.adafruit.com/adafruit-bno055-absolute-orientation-sensor)

- [Eksempelkode](https://learn.adafruit.com/adafruit-bno055-absolute-orientation-sensor/python-circuitpython#full-example-code-2998132)


---