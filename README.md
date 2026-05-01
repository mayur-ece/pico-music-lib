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
from buzzer_music import play_tone

BUZZER_PIN = 15

# Play A note (440Hz for 0.5 sec)
play_tone(BUZZER_PIN, 440, 500)
