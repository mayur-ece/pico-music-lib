# Buzzer Music Library (Raspberry Pi Pico)

Play simple tunes using a buzzer with MicroPython.

---

## 🔧 Setup (Important)

### 1. Flash MicroPython on Pico
1. Download MicroPython `.uf2` from official site
2. Hold **BOOTSEL** button on Pico
3. Plug into PC
4. Copy `.uf2` file into Pico drive

---

### 2. Install Thonny (or any IDE)
- Open Thonny
- Select interpreter → **MicroPython (Raspberry Pi Pico)**

---

### 3. Upload Library
- Copy `buzzer_music.py` to Pico using Thonny

---

## 🔌 Wiring
- Buzzer (+) → GPIO pin (example: GP15)
- Buzzer (-) → GND

---

## ▶️ Example Code

```python
from machine import Pin
from buzzer_music import music
import time

# 4 buzzers
pins = [Pin(15), Pin(16), Pin(17), Pin(18)]

song = (
"0 G4 2 0;2 G4 1 0;3 A4 4 0;7 G4 4 0;11 C5 4 0;15 B4 8 0;"
"24 G4 2 0;24 B4 2 0;26 G4 1 0;27 A4 4 0;31 G4 4 0;35 D5 4 0;39 C5 8 0;"
"48 G4 2 0;48 E5 2 0;50 G4 1 0;51 G5 4 0;55 E5 4 0;59 C5 4 0;63 B4 4 0;67 A4 8 0;"
"76 F5 2 0;76 A4 2 0;78 F5 1 0;79 E5 4 0;83 C5 4 0;87 D5 4 0;91 C5 8 0;"
)

m = music(songString=song, pins=pins, tempo=3)

while True:
    m.tick()
    time.sleep(0.04)
