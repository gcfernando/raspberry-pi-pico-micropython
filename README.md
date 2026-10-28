<a id="micropython-led-blink-example-for-raspberry-pi-pico-2-w"></a>

# Raspberry Pi Pico 2 W — MicroPython LED Blink

**Read online:** [Documentation website](https://gcfernando.github.io/raspberry-pi-pico-micropython/) · [All guides](documentation.md)

Learn GPIO output and timing with a short MicroPython program that toggles the Pico 2 W onboard LED once per second.

## 🔎 Overview

This repository contains one introductory board example. It uses `machine.Pin` and `time.sleep`; it does not configure Wi-Fi or require an external service.

<a id="what-is-included"></a>

## ✨ Features

- Selects the onboard LED with the board alias `Pin("LED", Pin.OUT)`.
- Toggles the LED state every second, for an approximately two-second on/off cycle.
- Keeps the complete program in [main.py](https://github.com/gcfernando/raspberry-pi-pico-micropython/blob/main/PiPico2W/FirstLed/main.py).

## 🚀 Quick start

Connect a Raspberry Pi Pico 2 W running matching MicroPython firmware, open it with a compatible MicroPython editor or REPL, then transfer and run [the example](https://github.com/gcfernando/raspberry-pi-pico-micropython/blob/main/PiPico2W/FirstLed/main.py). Follow the [step-by-step guide](PiPico2W/FirstLed/readme.md) for the program and expected behavior.

<a id="run-requirements"></a>

## 📦 Prerequisites and installation

You need the board, a USB data cable, matching MicroPython firmware and a tool that can access the board's filesystem and REPL. The `machine` module runs on MicroPython; ordinary desktop Python cannot execute this program as written.

See the [official RP2 firmware setup guide](https://docs.micropython.org/en/latest/rp2/tutorial/intro.html). This repository does not supply firmware or a desktop dependency installer.

## 💡 Usage

Run the script interactively while experimenting. Saving it as `main.py` on the board makes it a startup program; stop execution from your tool's REPL when you want to regain control. The loop runs continuously and has no command-line options.

## 🏗️ Architecture

`PiPico2W/FirstLed` contains the program, guide and [MicroPico project marker](https://github.com/gcfernando/raspberry-pi-pico-micropython/blob/main/PiPico2W/FirstLed/.micropico). The marker only identifies the local project folder; it does not install firmware, select a serial port or transfer the script. `main.py` must be run on, or copied to, the board separately. `_config.yml`, `_layouts` and `assets` support the documentation site.

## 🧪 Development and testing

There are no application tests or build scripts; the Repository standards workflow checks metadata separately. Confirm on the board that the LED changes state approximately once per second and that you can interrupt the loop. This documentation review compared the guide's code block with `main.py`; no physical board was available for execution.

## 🛠️ Troubleshooting and limitations

- **`No module named machine`:** run on the MicroPython board rather than desktop Python.
- **LED alias unavailable:** verify the board model and firmware; this sample expects the named `LED` pin.
- **Repeated startup:** a board copy named `main.py` is intentionally persistent; interrupt it through the connected tool before editing.

## 🤝 Contributing

For another board example, state the exact board, firmware, wiring and expected behavior. Include hardware verification details and keep the README linked to the executable source.

## 🔒 Security

Do not include wireless credentials or other secrets in examples or reports. Use the [security policy](SECURITY.md) for private reporting of sensitive issues.

<a id="documentation-links"></a>

## 📄 Support and license

Report reproducible example issues in [repository issues](https://github.com/gcfernando/raspberry-pi-pico-micropython/issues). The repository includes an [MIT license](https://github.com/gcfernando/raspberry-pi-pico-micropython/blob/main/LICENSE).

[Documentation index](documentation.md)

## Repository maintenance

[Contributing](https://github.com/gcfernando/raspberry-pi-pico-micropython/blob/main/CONTRIBUTING.md) · [Security policy](https://github.com/gcfernando/raspberry-pi-pico-micropython/blob/main/SECURITY.md) · [Repository standards](https://github.com/gcfernando/raspberry-pi-pico-micropython/blob/main/REPOSITORY_STANDARDS.md)
