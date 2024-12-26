# ESP32-continued-conversation-assistant

This configuration file is used to convert an [M5Stack ATOM Echo](https://shop.m5stack.com/products/atom-echo-smart-speaker-dev-kit) into a voice interface for [home assistant](https://www.home-assistant.io/voice_control/) so that a continued conversation can take place without having to speak the activation word again after [the assistant](https://www.nabucasa.com/config/assist/) has responded.

The Atom Echo is programmed via USB interface under [WSL](https://learn.microsoft.com/de-de/windows/wsl/).

# Install and use ESPHome under WSL

## User Instructions
- Use WSL **Bash** for commands prefixed with `$`.
- Use Windwows **PowerShell** for commands prefixed with `>`.

## 1. Install Python in WSL

Check version
```shell
$ python --version
```

### Create Virtuelle Environment
```shell
$ python3 -m virtuelleUmgebung venv
```

### Activate Virtual Environment
```shell
$ source virtuelleUmgebung/bin/activate
```

## 2. Install and Use USBIPD WIN
WSL does not have access to interfacing hardware by deafualt, but for programming the ESP32, we want to connect it via USB. With USBIPD one can make USB ports available to WSL.

[Official Microsoft Manual](https://learn.microsoft.com/de-de/windows/wsl/connect-usb#install-the-usbipd-win-project)

usbipd-win is used to share USB devices from Windows to a Linux environment in WSL, enabling seamless access to USB hardware. It simplifies USB device integration with WSL for development, debugging, or remote access tasks. Via usbipd-win, ESP32 is connected to WSL under a Windows environment.

[Download USBIPD WIN](https://github.com/dorssel/usbipd-win/releases)

### USBIPD Usage

1. List USB Devices
```powershell
> usbipd list
```

2. Enable an USB device (example: bus ID 4-4)
```powershell
> usbipd bind --busid 4-4
```

3. Attach USB Device
```powershell
> usbipd attach --wsl --busid <busid>
```

## 3. Install and Use ESPHome

[Official Installation Manual](https://esphome.io/guides/installing_esphome)

```shell
$ pip3 install esphome
$ esphome version
```

### ESPHome Usage

[ESPHome CLI-Commands](https://esphome.io/guides/cli.html)

```bash
$ esphome <some_command> --help
```

### Validate – Compilie – Upload – StartLog View
```bash
$ esphome run <CONFIG>
```