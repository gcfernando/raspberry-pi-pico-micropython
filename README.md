# Raspberry Pi Pico 2 W LED example

Learn MicroPython GPIO output and timing by toggling the Pico 2 W onboard LED once per second.

[![Repository standards](https://github.com/gcfernando/raspberry-pi-pico-micropython/actions/workflows/repository-standards.yml/badge.svg)](https://github.com/gcfernando/raspberry-pi-pico-micropython/actions/workflows/repository-standards.yml) [![Read the documentation](https://img.shields.io/badge/Read-the_documentation-2563eb?style=flat-square)](https://gcfernando.github.io/raspberry-pi-pico-micropython/)

This is one introductory board example for learners starting with `machine.Pin` and `time.sleep`. It uses the named onboard LED and needs no external wiring, Wi-Fi setup or service.

## Quick start

1. Connect a Raspberry Pi Pico 2 W using a USB data cable.
2. Install MicroPython firmware matching the board, following the [official RP2 setup guide](https://docs.micropython.org/en/latest/rp2/tutorial/intro.html).
3. Open the board in a compatible MicroPython editor or REPL tool.
4. Transfer and run [PiPico2W/FirstLed/main.py](PiPico2W/FirstLed/main.py). The LED should change state approximately once per second.

The [step-by-step program guide](PiPico2W/FirstLed/readme.md) explains each line. The `machine` module belongs to MicroPython on the board; ordinary desktop Python cannot execute the program as written.

## Requirements and usage

You need the board, matching firmware, a USB data cable and a tool that can access its filesystem and REPL. The repository provides the program, not firmware or a desktop installer.

```python
from machine import Pin
from time import sleep

led = Pin("LED", Pin.OUT)

while True:
    led.toggle()
    sleep(1)
```

One state change per second gives an approximately two-second on/off cycle. Run the script interactively while experimenting. Saving it as `main.py` on the board makes it a startup program; interrupt the loop through the connected tool before editing. It has no command-line options or shutdown handler.

## Development and verification

The source and its guide live in `PiPico2W/FirstLed/`. Its `.micropico` marker identifies a project folder; it does not install firmware, select a serial port or transfer the program. The remaining website files support the [documentation site](https://gcfernando.github.io/raspberry-pi-pico-micropython/).

There is no application build or automated hardware test suite. Verify on the board that the LED toggles and that you can stop execution. Documentation/source inspection does not establish a successful physical-board run. The Repository standards workflow checks metadata only.

## Troubleshooting

| Symptom | Check |
| --- | --- |
| `No module named machine` | Run on the MicroPython board rather than desktop Python. |
| Named LED pin unavailable | Confirm the board model and firmware expose the `LED` alias. |
| Script runs again after restart | Check whether the board has a startup file named `main.py`; interrupt it through the REPL. |

## Contributing, support and license

Use [repository issues](https://github.com/gcfernando/raspberry-pi-pico-micropython/issues) for reproducible problems. New examples should state the board, firmware, wiring, expected behavior and actual hardware checks. Follow [CONTRIBUTING.md](CONTRIBUTING.md) and the [repository standards](REPOSITORY_STANDARDS.md).

Keep wireless credentials and other secrets out of examples and reports; use the [security policy](SECURITY.md) for sensitive findings. This repository has an [MIT license](LICENSE). The [documentation index](documentation.md) provides further source navigation.

<!-- Preserve links to earlier README sections. -->
<a id="-architecture"></a>
<a id="-contributing"></a>
<a id="-development-and-testing"></a>
<a id="-features"></a>
<a id="-overview"></a>
<a id="-prerequisites-and-installation"></a>
<a id="-quick-start"></a>
<a id="-security"></a>
<a id="-support-and-license"></a>
<a id="-troubleshooting-and-limitations"></a>
<a id="-usage"></a>
<a id="documentation-links"></a>
<a id="guide-prerequisites-and-installation"></a>
<a id="guide-quick-start"></a>
<a id="guide-troubleshooting-and-limitations"></a>
<a id="guide-usage"></a>
<a id="micropython-led-blink-example-for-raspberry-pi-pico-2-w"></a>
<a id="raspberry-pi-pico-2-w--micropython-led-blink"></a>
<a id="raspberry-pi-pico-2-w--micropython-led-example"></a>
<a id="repository-maintenance"></a>
<a id="run-requirements"></a>
<a id="what-is-included"></a>
