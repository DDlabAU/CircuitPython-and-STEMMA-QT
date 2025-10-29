# WiFi

Adafruit.io makes it easy to integrate WiFi projects with your CircuitPython board. You can remotely control your board from the platform or send data, such as room temperature, to Adafruit.io and access it from anywhere in the world. Additionally, Adafruit.io enables communication between two boards, facilitating seamless data exchange for your projects.

Since the setup involves several steps, it doesn't make sense to create a guide here. Instead, we've linked to some excellent YouTube tutorials where each step is explained in detail and in an easy-to-understand manner!

We also provide links to project examples created by the lab, so you can borrow our code and adapt it to your project.

### Simplest WiFi Project (No Code Required)
This is the easiest way to create a simple WiFi project, though it has many limitations and requires no coding:
- [Video Tutorial](https://www.youtube.com/watch?v=beFuT_hG_LE)
- [Step-by-Step Guide](https://learn.adafruit.com/quickstart-adafruit-io-wippersnapper?view=all#installing-wippersnapper)

### Control Output Over WiFi
Learn how to control outputs over WiFi:
- [setup og simpel tænd/sluk](https://www.youtube.com/watch?v=iFwvvEJ_UwA&list=PLBJJ76R_ry5QY9BU5gqxrvtODWFkkTjYa&index=35&t=1449s)

- [fortsættelse på ovenstående video, med mere avanceret funktionalitet](https://www.youtube.com/watch?v=fjysAa3N2OI&list=PLBJJ76R_ry5QY9BU5gqxrvtODWFkkTjYa&index=36)


<details>
<summary>Code Example: Controlling NeoPixel Strip with Adafruit IO</summary>

```python
import board, time, neopixel
import os, ssl, socketpool, wifi
import adafruit_minimqtt.adafruit_minimqtt as MQTT

# setup neopixel strip
strip = neopixel.NeoPixel(board.A1, 30)
RED = (255, 0, 0)
BLACK = (0, 0, 0)
strip.fill(BLACK)

# Get adafruit io username and key from settings.toml
aio_username = os.getenv("AIO_USERNAME")
aio_key = os.getenv("AIO_KEY")

# setup a feed to subscribe to
strip_on_off_feed = aio_username + "/feeds/Strip_on_off"
strip_colour_change = aio_username + "/feeds/Strip_colour_change"

# Setup functions to respond to MQTT events

def connected(client, userdate, flags, rc):
    # connected to broker adafruit io
    print("connected to adafruit IO! listening....")

    # Subscribe to all changes on feeds below
    client.subscribe(strip_on_off_feed)
    client.subscribe(strip_colour_change)

def disconnected(client, userdata, rc):
    # disconnected
    print("disconnected from broker")

def message(client, topic, message):
    # the bulk of your code to respond to MQTT

    print(f"topic: {topic}, message: {message}")
    if message == "ON":
        strip.fill(RED)
        print("ON RECEIVED")

    elif message == "OFF":
        strip.fill(BLACK)

    elif message.isdigit():
        brightness_level = int(message)
        strip.brightness = brightness_level / 10.0
        print(f"Received brightness level: {brightness_level}")

# Connect to WiFi
print("connecting to WiFi")
wifi.radio.connect(os.getenv("WIFI_SSID"), os.getenv("WIFI_PASSWORD"))
print("Connected!")

# Create a socket pool
pool = socketpool.SocketPool(wifi.radio)

# Set up a MiniMQTT client
mqtt_client = MQTT.MQTT(
    broker=os.getenv("BROKER"),
    port=os.getenv("PORT"),
    username=aio_username,
    password=aio_key,
    socket_pool=pool,
    ssl_context=ssl.create_default_context()
)

# Setup the "callback" mqtt methods created above
mqtt_client.on_connect = connected
mqtt_client.on_disconnect = disconnected
mqtt_client.on_message = message

# Connect to the MQTT Broker
print("connecting to adafruit IO....")
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


