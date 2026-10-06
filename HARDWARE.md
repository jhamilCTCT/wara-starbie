# Starbie Hardware Notes

## Overview

`Starbie v1.0` is a compact motion-controlled digital pet board built around an RP2040 module, an I2C IMU, and an I2C OLED display.

## Recommended electrical architecture

- **MCU module:** Seeed XIAO RP2040
- **IMU:** LIS3DH
- **Display:** SSD1306 OLED over I2C
- **Battery charger:** MCP73831
- **LDO:** AP2112K-3.3
- **Power input:** USB-C, USB 2.0 power-only compatible

## Primary nets

- `USB_5V`
- `BAT+`
- `VBAT_SW`
- `+3V3`
- `GND`
- `I2C_SDA`
- `I2C_SCL`
- `BTN_FEED`
- `BTN_MENU`
- `BTN_SELECT`
- `BUZZER_DRV`
- `LED_USER`
- `UART_TX`
- `UART_RX`
- `IMU_INT1`
- `IMU_INT2`

## Functional blocks

### 1. USB-C input
- `VBUS -> USB_5V`
- `CC1 -> 5.1k -> GND`
- `CC2 -> 5.1k -> GND`

### 2. Battery charging
- `USB_5V -> MCP73831.VDD`
- `MCP73831.VBAT -> BAT+`
- `BAT+ -> JST battery connector`

### 3. Main power path
- `BAT+ -> SW1 -> VBAT_SW`
- `VBAT_SW -> AP2112K VIN`
- `AP2112K VOUT -> +3V3`

### 4. Processing and peripherals
- `+3V3` powers the MCU, IMU, OLED, user LED, and logic stage
- `I2C_SDA` and `I2C_SCL` are shared between LIS3DH and OLED

### 5. User interaction
- three buttons to GND using MCU internal pull-ups
- one user LED
- one buzzer driven with NPN transistor

## Mounting and marking

- 2 to 4 mounting holes, M2 or M2.5
- front silkscreen:
  - `Starbie`
  - `jhamilCTCT`
  - `v1.0`

## Current implementation status

- `README.md` created
- `BOM.md` created
- `wara.kicad_sch` includes title block and architecture scaffold
- custom local symbol library added for XIAO RP2040 module representation

## KiCad note

The project is structured so the schematic can be completed in KiCad GUI with standard libraries plus the local `starbie.kicad_sym` library.
