# Blink the Pico 2 W Onboard LED with MicroPython

Configure the board's named LED pin as an output and toggle it once per second. This example introduces GPIO output and blocking delays with a continuous loop.

## 📦 Prerequisites and installation

Use a Raspberry Pi Pico 2 W with matching MicroPython firmware, a USB data cable and a MicroPython editor or REPL tool. The `machine` module belongs to the board runtime; ordinary desktop Python cannot run this script as written.

For firmware setup, follow the [official RP2 getting-started guide](https://docs.micropython.org/en/latest/rp2/tutorial/intro.html). No external wiring or network connection is used by this program.

<a id="program"></a>

## 💡 Program

The following matches [main.py](https://github.com/gcfernando/raspberry-pi-pico-micropython/blob/main/PiPico2W/FirstLed/main.py):

```python
from machine import Pin
from time import sleep

led = Pin("LED", Pin.OUT)

while True:
    led.toggle()
    sleep(1)
```

<a id="how-it-works"></a>

## 💡 How it works

1. `Pin("LED", Pin.OUT)` selects the board's named onboard LED and configures it as an output. The program does not explicitly set an initial high/low value before the first toggle.
2. `led.toggle()` changes the current LED state.
3. `sleep(1)` waits one second before the next state change.
4. The `while True` loop repeats until execution is stopped.

The LED changes state once per second; a complete on/off cycle takes about two seconds. No network connection is used.

<a id="run-it-on-the-board"></a>

## 🚀 Run it on the board

Install the matching MicroPython firmware for your Pico 2 W, connect through a compatible editor or MicroPython REPL, and run the [source program](https://github.com/gcfernando/raspberry-pi-pico-micropython/blob/main/PiPico2W/FirstLed/main.py). Saving it as `main.py` on the board lets MicroPython run it at startup.

Interrupt execution from the REPL before editing or replacing a continuously running startup script.

## 🧪 Verification

Expected board behavior is one LED state change per second. Verify both visible toggling and the ability to stop execution. The code block was compared with the source during documentation review; physical hardware execution was not performed.

## 🛠️ Troubleshooting and limitations

| Symptom | Check |
|---|---|
| `No module named machine` | Run on MicroPython on the board, not desktop Python. |
| The named pin is unavailable | Confirm the board and firmware expose the `LED` alias. |
| The script restarts on reconnect | Check whether it was saved as the board's startup `main.py`. |

The script has no options, Wi-Fi initialization or shutdown handler. Its one-second delay is intended for a visual learning example rather than precision timing.

See the [official RP2 quick reference](https://docs.micropython.org/en/latest/rp2/quickref.html).

---

<a id="documentation-links"></a>

## 🔗 Related documentation

[Repository overview and license](../../README.md) · [Documentation index](../../documentation.md)
