# Starbie Pin Map

## MCU target

Primary target module: **Seeed XIAO RP2040**

## Suggested signal assignment

| Signal | Suggested GPIO | Function |
|---|---:|---|
| `UART_TX` | GPIO0 | Debug TX |
| `UART_RX` | GPIO1 | Debug RX |
| `IMU_INT1` | GPIO2 | Optional interrupt |
| `IMU_INT2` | GPIO3 | Optional interrupt |
| `I2C_SDA` | GPIO4 | Shared I2C data |
| `I2C_SCL` | GPIO5 | Shared I2C clock |
| `BTN_FEED` | GPIO6 | Button input |
| `BTN_MENU` | GPIO7 | Button input |
| `BTN_SELECT` | GPIO8 | Button input |
| `BUZZER_DRV` | GPIO9 | NPN buzzer driver |
| `LED_USER` | GPIO10 | Status LED |

## Power pins

| Signal | Use |
|---|---|
| `+3V3` | Main regulated system rail |
| `GND` | Common ground |
| `VBAT_SW` | Battery rail after power switch |

## Bus devices

### LIS3DH
- `SDA -> I2C_SDA`
- `SCL -> I2C_SCL`
- `INT1 -> IMU_INT1` optional
- `INT2 -> IMU_INT2` optional

### OLED header
- `Pin 1 -> GND`
- `Pin 2 -> +3V3`
- `Pin 3 -> I2C_SCL`
- `Pin 4 -> I2C_SDA`

## Notes

- Final GPIO mapping can be adjusted when the exact XIAO symbol and footprint pinout are confirmed in KiCad.
- Keep the I2C pair dedicated if possible.
