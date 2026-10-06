# Starbie Schematic Build Guide

This file describes the exact symbols and order recommended to finish `wara.kicad_sch` in KiCad.

## Symbol selection

### Local library
- `starbie:XIAO_RP2040_Module`

### KiCad standard libraries
- `Connector:USB_C_Receptacle_USB2.0_16P`
- `Battery_Management:MCP73831-2-OT`
- `Regulator_Linear:AP2112K-3.3`
- `Sensor_Motion:LIS3DH`
- `Connector_Generic:Conn_01x02`
- `Connector_Generic:Conn_01x04`
- `Switch:SW_SPST`
- `Switch:SW_Push`
- `Device:R_Small`
- `Device:C_Small`
- `Device:LED_Small`
- `Transistor_BJT:Q_NPN_BEC`
- `Device:Buzzer`
- `power:GND`
- `power:+3V3`

## Placement order

1. Place `USB_C_Receptacle_USB2.0_16P` as `J1`
2. Place two `R_Small` parts as `R1`, `R2` for `CC1` and `CC2`
3. Place `MCP73831-2-OT` as `U3`
4. Place `Conn_01x02` as `J2` for battery
5. Place `SW_SPST` as `SW1`
6. Place `AP2112K-3.3` as `U4`
7. Place `XIAO_RP2040_Module` as `U1`
8. Place `LIS3DH` as `U2`
9. Place `Conn_01x04` as `J3` for OLED
10. Place three `SW_Push` buttons as `SW2`, `SW3`, `SW4`
11. Place `Q_NPN_BEC` as `Q1`
12. Place `Buzzer` as `BZ1`
13. Place two `LED_Small` symbols as `D2`, `D3`
14. Place `Conn_01x04` as `J4` for debug
15. Place passive support parts `R3..R8`, `C1..C6`

## Net naming

Create and reuse these labels:

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

## Minimal required connections

### USB-C and charger
- `J1.VBUS -> USB_5V`
- `J1.CC1 -> R1 -> GND`
- `J1.CC2 -> R2 -> GND`
- `U3.VDD -> USB_5V`
- `U3.VSS -> GND`
- `U3.VBAT -> BAT+`
- `U3.PROG -> R8 -> GND`

### Battery and regulation
- `J2.1 -> BAT+`
- `J2.2 -> GND`
- `BAT+ -> SW1 -> VBAT_SW`
- `U4.VIN -> VBAT_SW`
- `U4.GND -> GND`
- `U4.VOUT -> +3V3`
- `C1` at `VIN`
- `C2` at `VOUT`

### MCU and I2C
- `U1.3V3 -> +3V3`
- `U1.GND -> GND`
- `U1.SDA -> I2C_SDA`
- `U1.SCL -> I2C_SCL`
- `R3: I2C_SDA -> +3V3`
- `R4: I2C_SCL -> +3V3`

### IMU
- `U2.VDD -> +3V3`
- `U2.GND -> GND`
- `U2.SDA -> I2C_SDA`
- `U2.SCL -> I2C_SCL`
- `U2.INT1 -> IMU_INT1` optional
- `U2.INT2 -> IMU_INT2` optional

### OLED
- `J3.1 -> GND`
- `J3.2 -> +3V3`
- `J3.3 -> I2C_SCL`
- `J3.4 -> I2C_SDA`

### Buttons
- `SW2 -> BTN_FEED -> GND`
- `SW3 -> BTN_MENU -> GND`
- `SW4 -> BTN_SELECT -> GND`

### Buzzer and LEDs
- `U1.BUZZER_DRV -> R5 -> Q1 base`
- `Q1 emitter -> GND`
- `Q1 collector -> BZ1-`
- `BZ1+ -> +3V3` or `VBAT_SW`
- `D2 power LED: +3V3 -> R6 -> LED -> GND`
- `D3 user LED: LED_USER -> R7 -> LED -> GND`

### Debug
- `J4.1 -> UART_TX`
- `J4.2 -> UART_RX`
- `J4.3 -> +3V3`
- `J4.4 -> GND`

## Validation targets

- ERC clean or only intentional warnings
- all rails named consistently
- every IC decoupled
- every LED has series resistor
- no direct buzzer drive from GPIO
