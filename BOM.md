# Starbie v1.0 - Initial BOM

Presupuesto objetivo inicial: **$30 USD**

## Componentes principales

| Ref | Cant. | Componente | Valor / Modelo | Paquete / Footprint sugerido | Función | Costo estimado |
|---|---:|---|---|---|---|---:|
| U1 | 1 | MCU Module | Seeed XIAO RP2040 | Footprint módulo XIAO | Microcontrolador principal | $5.00 - $8.00 |
| U2 | 1 | IMU | LIS3DH | LGA/QFN según variante | Detección de inclinación y movimiento | $2.00 - $4.00 |
| U3 | 1 | Charger IC | MCP73831 | SOT-23-5 | Carga de batería LiPo | $0.50 - $1.50 |
| U4 | 1 | LDO 3.3V | AP2112K-3.3 | SOT-23-5 | Regulación de voltaje | $0.30 - $1.00 |
| J1 | 1 | USB-C Receptacle | USB 2.0 Type-C | USB_C_Receptacle_USB2.0 | Entrada de alimentación | $0.50 - $1.50 |
| J2 | 1 | Battery Connector | JST-PH 2.0 2-pin | JST_PH_1x02_P2.00mm | Conector de batería | $0.20 - $0.80 |
| J3 | 1 | OLED Header | 1x4 2.54mm | PinHeader_1x04_P2.54mm | Conexión de pantalla OLED | $0.10 - $0.30 |
| J4 | 1 | Debug Header | 1x4 2.54mm o test pads | PinHeader/TestPoint | UART debug | $0.10 - $0.30 |
| SW1 | 1 | Power Switch | SPDT/SPST Slide | Switch SMD/THT | Encendido/apagado | $0.20 - $0.80 |
| SW2 | 1 | Push Button | Tact switch | SMD/THT | Botón Feed | $0.10 - $0.30 |
| SW3 | 1 | Push Button | Tact switch | SMD/THT | Botón Menu | $0.10 - $0.30 |
| SW4 | 1 | Push Button | Tact switch | SMD/THT | Botón Select | $0.10 - $0.30 |
| BZ1 | 1 | Buzzer | Piezo o magnético | Buzzer footprint | Feedback sonoro | $0.50 - $1.50 |
| Q1 | 1 | NPN Transistor | 2N3904 / S8050 / MMBT3904 | TO-92 o SOT-23 | Driver del buzzer | $0.05 - $0.20 |
| D1 | 1 | Flyback diode | 1N4148 / Schottky pequeña | SOD-123 / DO-35 | Protección si el buzzer es magnético | $0.05 - $0.20 |
| D2 | 1 | Power LED | Verde/rojo | LED_0805 | Indicador de encendido | $0.05 - $0.15 |
| D3 | 1 | User LED | Cualquier color | LED_0805 | Estado del sistema | $0.05 - $0.15 |

## Pasivos y soporte

| Ref | Cant. | Componente | Valor | Footprint sugerido | Función |
|---|---:|---|---|---|---|
| R1 | 1 | Resistor | 5.1kΩ | 0805 | CC1 a GND |
| R2 | 1 | Resistor | 5.1kΩ | 0805 | CC2 a GND |
| R3 | 1 | Resistor | 4.7kΩ | 0805 | Pull-up SDA |
| R4 | 1 | Resistor | 4.7kΩ | 0805 | Pull-up SCL |
| R5 | 1 | Resistor | 1kΩ - 4.7kΩ | 0805 | Base del transistor buzzer |
| R6 | 1 | Resistor | 1kΩ | 0805 | LED de power |
| R7 | 1 | Resistor | 330Ω - 1kΩ | 0805 | LED de usuario |
| R8 | 1 | Resistor | 5kΩ - 10kΩ | 0805 | PROG del MCP73831 |
| C1 | 1 | Capacitor | 1µF - 10µF | 0805 | Entrada del LDO |
| C2 | 1 | Capacitor | 1µF - 10µF | 0805 | Salida del LDO |
| C3 | 1 | Capacitor | 1µF | 0805 | Soporte del cargador |
| C4 | 1 | Capacitor | 100nF | 0805 | Desacoplo IMU |
| C5 | 1 | Capacitor | 100nF | 0805 | Desacoplo MCU |
| C6 | 1 | Capacitor | 100nF | 0805 | Desacoplo adicional |
| MH1-MH4 | 2-4 | Mounting Hole | M2 / M2.5 | MountingHole | Fijación mecánica |

## Estimación total

| Categoría | Estimado |
|---|---:|
| MCU | $5.00 - $8.00 |
| IMU | $2.00 - $4.00 |
| OLED | $3.00 - $6.00 |
| Power + charging | $2.00 - $5.00 |
| Conectores + switch | $1.00 - $3.00 |
| Botones + buzzer + LEDs | $2.00 - $4.00 |
| Pasivos | $1.00 - $2.00 |

**Total estimado:** **$18.00 - $28.00 USD**

## Notas de selección

- Se prioriza una arquitectura simple y económica para mantenerse dentro del presupuesto.
- El uso del **Seeed XIAO RP2040** simplifica el ruteo y reduce riesgo de diseño.
- El **OLED I2C** y el **LIS3DH** comparten el mismo bus I2C para ahorrar pines.
- Se recomienda usar pasivos **0805** para facilitar ensamblaje manual.
- La batería LiPo es opcional en prototipos iniciales, pero el diseño la contempla.
