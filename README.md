# ATmega328P Simple MCU Development Board

## Overview

This project is a minimal standalone development board built around the **ATmega328P** microcontroller.  
The objective of this design is to create a compact and functional MCU board capable of running embedded applications without relying on a full Arduino board.

The board includes the essential circuitry required for stable operation:

- Power supply connections  
- External clock source  
- Reset circuitry  
- Decoupling capacitors  
- ISP programming header  

Designed using KiCad.

---

## System Architecture

The board consists of five primary functional blocks:

1. Power Supply Section  
2. Microcontroller Core  
3. Clock Circuit  
4. Reset Circuit  
5. Programming Interface  

---

## Microcontroller Core — ATmega328P

The ATmega328P is an 8-bit AVR microcontroller.

### Key Features

- 32 KB Flash memory  
- 2 KB SRAM  
- 1 KB EEPROM  
- 23 programmable I/O pins  
- SPI, I2C, UART interfaces  
- 10-bit ADC  

The MCU operates typically at 5V and supports clock frequencies up to 16 MHz using an external crystal.

---

## Power Supply and Decoupling

### 0.1 µF Decoupling Capacitors

**Purpose:**  
Provide local charge storage and suppress high-frequency noise.

**Theory:**  
When the MCU switches internally, it draws short bursts of current.  
Without proper decoupling capacitors placed close to the VCC pins, voltage dips can occur, causing instability.

Best practice:
- 0.1 µF ceramic capacitor placed close to VCC  
- Short traces between capacitor and power pins  
- Direct connection to ground  

---

## Clock Circuit

### External Crystal (16 MHz)

**Purpose:**  
Provide a stable and accurate clock signal.

**Configuration:**

- Crystal connected between XTAL1 and XTAL2  
- Two 22 pF capacitors connected from each crystal pin to ground  
- Short, symmetric traces  

---

## Reset Circuit

### Components

- 10k pull-up resistor  
- Push-button switch  

**Theory:**  
The RESET pin is active-low.  
The 10k resistor keeps RESET high during normal operation.  
Pressing the button pulls RESET low, restarting the MCU.

---

## ISP Programming Interface

Used to flash firmware into the microcontroller.

### Pins

- MOSI  
- MISO  
- SCK  
- RESET  
- VCC  
- GND  

This allows programming using an external AVR programmer.

---

## PCB Design Considerations

- Decoupling capacitors placed near MCU power pins  
- Crystal traces kept short  
- Logical component placement  
- Two-layer PCB layout  

---

## Tools Used

- KiCad (Schematic + PCB)
- 2-layer PCB design
- Through-hole DIP package

---

## Future Improvements

- Add full ground plane  
- Optimize routing  
- Convert to 4-layer stackup  
- Compact SMD version  

---

## Status

✔ Schematic complete  
✔ PCB routed  
✔ Gerbers generated  
