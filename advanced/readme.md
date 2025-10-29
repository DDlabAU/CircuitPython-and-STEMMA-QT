# WiFi

Adafruit.io gør det nemt at integrere WiFi-projekter med dit CircuitPython-board. Du kan fjernstyre dit board, sende data fra board til din computer, eller lade to boards kommunikere. Se vores links til tutorials og projekteksempler for at komme i gang!

### Snyde WiFi-projekt (Ingen kode nødvendig) :D
Dette er den nemmeste måde at lave et simpelt WiFi-projekt på, selvom det har mange begrænsninger og ikke kræver kodning:
- [Videotutorial](https://www.youtube.com/watch?v=beFuT_hG_LE)
- [Trin-for-trin-guide](https://learn.adafruit.com/quickstart-adafruit-io-wippersnapper?view=all#installing-wippersnapper)

### Send data/kommando **til** dit board
Lær hvordan du styrer output via WiFi:
- [Opsætning og simpel tænd/sluk](https://www.youtube.com/watch?v=iFwvvEJ_UwA&list=PLBJJ76R_ry5QY9BU5gqxrvtODWFkkTjYa&index=35&t=1449s)

- [Fortsættelse af ovenstående video med mere avanceret funktionalitet](https://www.youtube.com/watch?v=fjysAa3N2OI&list=PLBJJ76R_ry5QY9BU5gqxrvtODWFkkTjYa&index=36)


<details>
<summary>Kodeeksempel: Styring af NeoPixel-strip med Adafruit IO</summary>

```python
import board, time, neopixel
import os, ssl, socketpool, wifi
import adafruit_minimqtt.adafruit_minimqtt as MQTT

# Opsætning af NeoPixel-strip
strip = neopixel.NeoPixel(board.A1, 30)
RED = (255, 0, 0)
BLACK = (0, 0, 0)
strip.fill(BLACK)

# Hent Adafruit IO-brugernavn og nøgle fra settings.toml
aio_username = os.getenv("AIO_USERNAME")
aio_key = os.getenv("AIO_KEY")

# Opsæt en feed til at abonnere på
strip_on_off_feed = aio_username + "/feeds/Strip_on_off"
strip_colour_change = aio_username + "/feeds/Strip_colour_change"

# Opsæt funktioner til at reagere på MQTT-hændelser

def connected(client, userdate, flags, rc):
    # Forbundet til broker Adafruit IO
    print("Forbundet til Adafruit IO! Lytter....")

    # Abonner på alle ændringer på feeds nedenfor
    client.subscribe(strip_on_off_feed)
    client.subscribe(strip_colour_change)

def disconnected(client, userdata, rc):
    # Afbrudt forbindelse
    print("Afbrudt fra broker")

def message(client, topic, message):
    # Hoveddelen af din kode til at reagere på MQTT

    print(f"Emne: {topic}, Besked: {message}")
    if message == "ON":
        strip.fill(RED)
        print("ON modtaget")

    elif message == "OFF":
        strip.fill(BLACK)

    elif message.isdigit():
        brightness_level = int(message)
        strip.brightness = brightness_level / 10.0
        print(f"Modtaget lysstyrkeniveau: {brightness_level}")

# Forbind til WiFi
print("Forbinder til WiFi")
wifi.radio.connect(os.getenv("WIFI_SSID"), os.getenv("WIFI_PASSWORD"))
print("Forbundet!")

# Opret en socket-pool
pool = socketpool.SocketPool(wifi.radio)

# Opsæt en MiniMQTT-klient
mqtt_client = MQTT.MQTT(
    broker=os.getenv("BROKER"),
    port=os.getenv("PORT"),
    username=aio_username,
    password=aio_key,
    socket_pool=pool,
    ssl_context=ssl.create_default_context()
)

# Opsæt "callback"-metoderne til MQTT oprettet ovenfor
mqtt_client.on_connect = connected
mqtt_client.on_disconnect = disconnected
mqtt_client.on_message = message

# Forbind til MQTT-broker
print("Forbinder til Adafruit IO....")
mqtt_client.connect()

while True:
    mqtt_client.loop()
```

</details>


<details>
<summary>settings.toml</summary>

```toml
# settings.toml

WIFI_SSID = "wifinavn"
WIFI_PASSWORD = "wifikode"
AIO_USERNAME = "dit adafruit io brugernavn"
AIO_KEY = "din aio nøgle"
BROKER = "io.adafruit.com"
PORT = 1883
```
</details>


### Send data/kommando **fra** dit board til din computer/andre boards:
- [video 1](https://www.youtube.com/watch?v=565lpAIWjJM&list=PL9VJ9OpT-IPSsQUWqQcNrVJqy4LhBjPX2&index=115&t)

- [video 2](https://www.youtube.com/watch?v=UxhCPdK7W38&t)


