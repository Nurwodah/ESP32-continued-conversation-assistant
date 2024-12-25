# ESP32-continued-conversation-assistant

kommt noch

# Install and use ESPHome with WSL

## User Instructions
- Use WSL **Bash** for commands prefixed with `$`.
- Use Windwows **PowerShell** for commands prefixed with `>`.

## 1. Install Python in WSL
[Official Installation Manual](https://esphome.io/guides/installing_esphome)

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

## Install ESPHome with pip
```shell
$ pip3 install esphome
$ esphome version
```

## 2. Install USBIPD WIN
WSL does not have access to interfacing hardware by deafualt, but for programming the ESP32, we want to connect it via USB. With USBIPD one can make USB ports available to WSL.

[Official Microsoft Manual](https://learn.microsoft.com/de-de/windows/wsl/connect-usb#install-the-usbipd-win-project)

usbipd-win is used to share USB devices from Windows to a Linux environment in WSL, enabling seamless access to USB hardware. It simplifies USB device integration with WSL for development, debugging, or remote access tasks. Via usbipd-win, ESP32 is connected to WSL under a Windows environment.

[Download USBIPD WIN](https://github.com/dorssel/usbipd-win/releases)

## 3. USBIPD Usage

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

## 4. ESPHome Usage

[CLI-Commands of ESPHome](https://esphome.io/guides/cli.html)

### Help
```bash
$ esphome <some_command> --help
```

### Validate – Compilie – Upload – StartLog View
```bash
$ esphome run <CONFIG>
```