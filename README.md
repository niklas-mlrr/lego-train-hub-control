# LEGO Train Hub Control

Eine Python-GUI zur Steuerung von LEGO Powered Up Train Hubs über Bluetooth (BLE).


## Installation der Abhängigkeiten


```bash
pip install -r requirements.txt
```

## Nutzung

### Hauptprogramm starten

```bash
python main.py
```

**Wichtig:** Der Train Base sollte **eingeschaltet** sein, bevor das Programm gestartet wird. Das Programm sucht automatisch nach einem Train Hub und verbindet sich.

### Verbindung zurücksetzen

Falls die Verbindung Probleme macht:
- "Disconnect" klicken
- Tran Hub aus und erneut einschalten
- "Connect to Train Base" klicken

## Dateien

| Datei | Beschreibung |
|-------|-------------|
| `main.py` | **Hauptprogramm** – Feature-reichste Version mit GUI. Dies ist die Datei, die für die reguläre Nutzung verwendet werden sollte. |
| `terminal_test.py` | Erste Testversion – Nur Terminal-basiert, um die Verbindung zum Train Hub zu testen |
| `color_sensor_direct.py` | Test-Skript für den Farbsensor |

## Features

### Basic Motor Control

Zwei separate Methoden zur Geschwindigkeitssteuerung:
- **Instant Speed Control** – Direkte Geschwindigkeitsänderung
- **Speed Control (with Button)** – Geschwindigkeitsänderung über Buttons

### Arduino Live Value

Ermöglicht das Auslesen von Werten eines Arduino (bei korrekter Port-Konfiguration), z.B. von einem Flex-Sensor. Diese Werte werden in der aktuellen Konfiguration auch zur Steuerung der Zug-Geschwindigkeit verwendet, wenn ein Arduino erfolgreich verbunden wurde.

**Beispiel-Code für Arduino:** [projektwoche-2025-eisenbahn – main.cpp](https://github.com/niklas-mlrr/projektwoche-2025-eisenbahn/blob/main/Arduino%20-%20Flexsensor%20%26%20Buttons/src/main.cpp)


### Hub Control

Tab zum Einstellen der LED-Farbe auf dem Train Hub.

> **Hinweis:** Nicht alle Features sind vollständig funktionsfähig. Der "Hub Control"-Tab funktioniert derzeit nicht zuverlässig.

## Protokoll

Das Programm nutzt das **LWP3 (LEGO Wireless Protocol 3)** zur Kommunikation mit dem Train Hub. Unterstützte Befehle:
- Motor-Geschwindigkeit (`StartSpeed`, `StartSpeedForTime`, `StartSpeedForDegrees`)
- Hub LED-Farbe
- Hub-Aktionen (Disconnect, Shutdown, VCC Port Control)
- Port-Informationen

## Voraussetzungen

- Python 3.8+
- Bluetooth-fähiges System (für BLE-Verbindung)
- LEGO Powered Up Train Hub (Train Base)
- Optional: Arduino für Sensor-Integration

## Abhängigkeiten

- `pybricksdev` – Pybricks Entwicklungstools
- `bleak` – Bluetooth Low Energy Bibliothek
- `pyserial` – Serielle Kommunikation# lego-train-hub-control
