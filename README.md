# ESP32-continued-conversation-assistant

kommt noch

# ESPHome unter Linux installieren und nutzen

## Installation

### Python installieren
[Offizielle Installationsanleitung](https://esphome.io/guides/installing_esphome)

```bash
$ python --version
Python 3.10.1
```

### Virtuelle Umgebung erstellen
```bash
$ python3 -m virtuelleUmgebung venv
```

### Virtuelle Umgebung aktivieren
```bash
$ source virtuelleUmgebung/bin/activate
```

### ESPHome installieren
```bash
$ pip3 install esphome
$ esphome version
Version: 2021.12.
```

### USBIPD WIN installieren
[Download USBIPD WIN](https://github.com/dorssel/usbipd-win/releases)

## Nutzung
[CLI-Nutzung von ESPHome](https://esphome.io/guides/cli.html)

### Hilfe
```bash
$ esphome <some_command> --help
```

### Validieren – Compilieren – Upload – StartLog View
```bash
$ esphome run <CONFIG>
```

## USB für WSL zugänglich machen
[Offizielle Anleitung von Microsoft](https://learn.microsoft.com/de-de/windows/wsl/connect-usb#install-the-usbipd-win-project)

**Achtung: Powershell**

### USB-Geräte auflisten
```bash
$ usbipd list
```

### Freigeben eines USB-Geräts (Beispiel: Bus-ID 4-4)
```bash
$ usbipd bind --busid 4-4
```

### USB-Gerät anfügen
```bash
$ usbipd attach --wsl --busid <busid>