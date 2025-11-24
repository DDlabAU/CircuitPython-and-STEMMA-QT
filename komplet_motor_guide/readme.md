# Servo 180°
#### Key feature:
Kan indstilles til vinkler f.eks. 30° eller 80°. Det gør at den kan bruges til at pege specifikke steder hen. kan også bruges til at skubbe, åbne, låse eller til robotter. En meget alsidig og billig motor. Søg på nettet og se hvad andre har brugt den til før.

Ulempen er at den kun har et range of motion på 180° og kan ikke gå over 180° uden at gå i stykker.

- 5V
- Kan fungere uden ekstern strøm, men hvis der er mere end én tilsluttet, skal der ekstern strømforsyning til
- 3 ledninger: rød til 5V strøm, sort til GND, hvid til signal fx "A1"

(hvis du bruger ekstern strømforsyning er det vigtigt at motorens sorte ledning går BÅDE til ekstern GND og board GND)

# Servo continous
#### Key feature:
Virker lidt som en 180° servo, og larmer ligeså meget, men den kan IKKE indstilles til vinkler, derfor er den ikke så præcis. Den skal indstilles til tid+retning. "drej til højre i 2 sekunder" fx.
Fordelen er at den kan dreje uendige

Ikke ligeså alsidig, men nem at bruge og kan dreje 360 grader.

- 5V
- Kan fungere uden ekstern strøm, men hvis der er mere end én tilsluttet, skal der ekstern strømforsyning til
- 3 ledninger: rød til 5V strøm, sort til GND, hvid til signal fx "A1"

(hvis du bruger ekstern strømforsyning er det vigtigt at motorens sorte ledning går BÅDE til ekstern GND og board GND)

# Simple dc motor
#### Key feature:
Meget hurtigt-drejende, meget svag motor. God til f.eks. en blæser. Lydlød. Der er kun 2 ledninger så den ene skal i gnd, og den anden i signal. Man kan enten bare tænde/slukke for den, men hvis man gerne vil kontrollere hastigheden kan man bruge PWM (pulse width modulation).

- 5V
- Benyt en mosfet driver: http://adafru.it/5648
- indsæt motorens 2 ledninger i den.
- driveren har 3 ledninger. den hvide skal i board signal, f.eks. a1.
- den røde skal til ekstern strøm IND
- den sorte skal BÅDE til ekstern strøm GND og board GND

# Geared dc motor
#### Key feature:
I princippet samme type motor som dc motoren, men der sidder en gearbox der ændrer den 1:48. Den nye rotation der kommer er altså 48 gange langsommere men har 48 gange mere moment (power). Det giver mening hvis man skal bruge den til at trække en lille radiobil fx eller drive et bælte.

 Benyt en mosfet driver: http://adafru.it/5648
- indsæt motorens 2 ledninger i den.
- driveren har 3 ledninger. den hvide skal i board signal, f.eks. a1.
- den røde skal til ekstern strøm IND
- den sorte skal BÅDE til ekstern strøm GND og board GND

# Large Solenoid
#### Key feature:
Push/pull solenoid. Når den får strøm skubber den med en solid kraft 2-3 cm fremad. Når strømmen stopper falder den tilbage på plads. I denne form skal man være lidt kreativ for at finde ud af hvad man kan bruge den til. f.eks. kan man tag en xylofon og sætte en solenoid over hver knap, og så kan man skrive kode der får den til at spille sange automatisk. For mere seriøst projekter har vi en solenoid den sidder i et vandrør, som kan åbne og lukke for vandet. eller en lock-style solenoid som kan sættes i døre og skuffer så de er låst indtil du aktiverer den.

12v, vær forsigtig. 12v ekstern strøm er nok til at kortslutte sensorer og boards hvis du sætter ledningerne forkert. fejl kan ske, men det er bedre at spørge en gang for meget end en gang for lidt :D

 Benyt en mosfet driver: http://adafru.it/5648
- indsæt motorens 2 ledninger i den.
- driveren har 3 ledninger. den hvide skal i board signal, f.eks. a1.
- den røde skal til ekstern strøm IND
- den sorte skal BÅDE til ekstern strøm GND og board GND

# Vibration motor
#### Key feature:
Perfekt hvis du vil inkorporere haptisk feedback i et projekt. har over 100 forskellige vibrationsmønstre. Meget nem at bruge.

Bruger denne driver:
https://www.adafruit.com/product/2305
Det eneste du skal er at plugge det ind i boarded med et stemma qt kabel og skrive kode. mega nemt

# Stepper motor
#### Key feature:
Den mest præcise, alsidige, stærke, hurtige motor vi har. Men også den dyreste og sværeste at bruge. Giver kun mening at bruge den hvis man ved at man skal bruge dens egenskaber. ellers koster en servomotor180° 100x mindre og er 20x nemmere at opsætte. Denne motor sidder i cnc maskiner såsom vores lasercuttere og 3d printere og driver x-y-z akserne, det er den præcision vi snakker! Og de stepppermoterer vi har pt. er modellen nema17 som vi faktisk har pillet ud af vores gamle 3d printere.

Hvad du skal bruge
- stepper motor driver
- lod 4 ledninger fra motoren på driveren
- ekstern 12v strømforsyning
- lod strømforsyningen fast på driver boarded de korrekt steder
- tilslut board til driver, og også lod en ledninger mellem board og driverens "EN" (enable) pin, da det er vigtigt at kontrollere hvornår motoren er tænd og slukket, da den ellers bliver varmere end solens kerne og brænder dit projekt ned.

bruge denne guide til wiring:

https://learn.adafruit.com/adafruit-tmc2209-stepper-motor-driver-breakout-board/circuitpython-and-python 

# Linear actuator
#### Key feature:
Der sidder en i den hemmelige skuffe under bordet. det er den eneste vi har da de er meget gamle og skrøbelige og der ikke har været efterspørgsel i MANGE år. Men hvis i skal bruge en, så sig til, så kan vi måske indkøbe nogle nye. 

Det er meget vigtigt ikke kun at tilslutte motorens strøm ind ud ledninger, for motoren kan ikke stopper af sig selv, så hvis man prøver at trække armen ind, mens den allerede er inde, så knækker motoren. Derfor har den et potentiometer indbygget som kan tilsluttet til boarded og så kan man observere om morteren er inde eller ude.

Vi skriver en mere præcis guide, hvis vi køber flere.




