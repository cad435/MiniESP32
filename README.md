# MiniESP32
A very small dev-board for the original ESP32 (XTENSA Dual-Core) with USB-C PD support.

---

## About
Since the ESP32-C3 was released I enjoyed the use of those ultra-small dev-boards.
Sadly there were no such dev-boards for the "original" ESP32 (XTENSA Dual-Core), so I created my own.

The board measures just **25x31mm** — only slightly bigger than the ESP32-WROOM module itself (19x26mm).


## Features
- **USB-C** connector
- **USB-PD** support via **CH224Q** PD controller
- **Switchable V+ output** — USB-PD voltage can be enabled/disabled via GPIO18
- All usable GPIOs broken out on 2.54mm headers
- 2x I2C, 2x UART, Touch, DAC, ADC
- Onboard LED on GPIO02, Boot button on GPIO00

## USB Power Delivery (CH224Q)
The V2.2 PD revision includes a **CH224Q** USB-PD sink controller.

- **Default output: 9V** — the CH224Q negotiates 9V on power-up
- The voltage can be changed to **5V** via software using the [CH224Q Arduino Library](https://github.com/cad435/CH224Q_Arduino)
- **V+ is switched** — GPIO18 controls a MOSFET that connects/disconnects the negotiated PD voltage to the V+ output pin. This allows you to turn the power output on and off programmatically
- **I2C connection** — the CH224Q is connected to I2C1 on GPIO21 (SDA) and GPIO22 (SCL)

## Pinout

![Pinout](https://github.com/cad435/MiniESP32/blob/main/Pinout.png)

## Manufacturing

Gerber and provided .xlsx files can be used to directly upload to JLCPCB (*.xlsx files for assembly service).

## Files
| File | Description |
|---|---|
| `MiniESP32_Gerber.zip` | Gerber files (panelized, ready for JLCPCB) |
| `MiniESP32_V2.2 PD-Schematic.PDF` | Schematic |
| `BOM-MiniESP32(V2.2 PD).pdf` | Bill of Materials |
| `MiniESP32_V2.2 PD_Assembly.PDF` | Assembly drawing |
| `MiniESP32_V2.2 PD_BoardSpec.PDF` | Board specifications |
| `JLC_PCBA_BOM-MiniESP32(V2.2 PD).xlsx` | BOM for JLCPCB assembly |
| `JLC_PCBA_CPL-MiniESP32(V2.2 PD).xlsx` | Component placement for JLCPCB assembly |
| `MiniESP32.step` | 3D model (STEP) |

## Photo

<img width="914" height="862" alt="27b760d5-4e83-46a3-9fcc-3738d6150797" src="https://github.com/user-attachments/assets/c84265ce-ae5d-44b5-8f16-663698f2379e" />

Note: the patched diode is now fixed and uploaded!


## License
Licensed under the [Open Source Hardware Association License](https://www.oshwa.org/definition/)
