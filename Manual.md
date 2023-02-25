SPI aktivieren mit raspi-config

sudo apt install python3-dev python3-pip
sudo pip3 install spidev
sudo pip3 install mfrc522

Write Command:

#!/usr/bin/env python

import RPi.GPIO as GPIO
from mfrc522 import SimpleMFRC522

reader = SimpleMFRC522()

try:
        id, text = reader.read()
        print(id)
        print(text)
finally:
        GPIO.cleanup()
        
Read Command:

#!/usr/bin/env python

import RPi.GPIO as GPIO
from mfrc522 import SimpleMFRC522

reader = SimpleMFRC522()

try:
        text = input('New data:')
        print("Now place your tag to write")
        reader.write(text)
        print("Written")
finally:
        GPIO.cleanup()
        
MPD als Benutzer installieren.

Bluetooth mit pulseaudio.

