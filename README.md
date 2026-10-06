# Starbie

## Español

**Starbie** es una pequeña mascota digital controlada por movimiento, inspirada en un Tamagotchi de escritorio.  
Este proyecto está siendo desarrollado como una placa personalizada en **KiCad** para **Hack Club**.

### Idea del proyecto

La meta de Starbie es crear una mascota virtual simple y expresiva que pueda:
- reaccionar al movimiento,
- mostrar animaciones en una pantalla pequeña,
- responder a botones del usuario,
- emitir sonidos retro con un buzzer.

Descripción base del proyecto:

> "A tiny motion-controlled digital pet, basically a desktop Tamagotchi"

### Características principales

- Microcontrolador compacto y económico
- Sensor de movimiento (IMU/acelerómetro)
- Pantalla OLED por I2C
- Alimentación por USB-C
- Soporte para batería LiPo
- Cargador integrado
- Regulación a 3.3V
- 3 botones de interacción
- Buzzer para feedback sonoro
- LEDs de estado
- Pads/header de depuración
- Agujeros de montaje y silkscreen personalizada

### Arquitectura de hardware

#### Núcleo de procesamiento
- **Seeed XIAO RP2040**

#### Sensor de movimiento
- **LIS3DH** por I2C

#### Pantalla
- **OLED SSD1306 0.96\" I2C**

#### Alimentación
- **USB Type-C**
- **MCP73831** para carga de batería LiPo
- **AP2112K-3.3** como regulador LDO
- **JST-PH 2.0** para batería
- Switch de encendido/apagado

#### Interacción
- 3 pulsadores
- Buzzer con transistor NPN
- LED de power
- LED de usuario

### Objetivos del diseño

- Mantener el costo cerca del presupuesto inicial de **$30 USD**
- Simplificar el ruteo usando módulos y buses compartidos
- Diseñar una placa compacta, clara y ensamblable
- Crear una base sólida para una futura versión con firmware y carcasa 3D

### Estado del proyecto

Archivos principales:
- `wara.kicad_sch`
- `wara.kicad_pcb`
- `wara.kicad_pro`

### Plan de desarrollo

1. Definir el esquemático completo
2. Validar ERC
3. Asignar footprints
4. Diseñar el PCB
5. Validar DRC
6. Generar BOM y archivos de fabricación
7. Ensamblar y probar hardware
8. Desarrollar firmware de la mascota

### Silkscreen prevista

La PCB incluirá:
- nombre del proyecto: **Starbie**
- autor/usuario: **jhamilCTCT**
- versión de hardware: **v1.0**
- etiquetas claras para conectores y pines

### Futuras mejoras

- Pantalla a color SPI
- Animaciones más complejas
- Modo de ahorro de energía
- Carcasa impresa en 3D
- Sensor táctil adicional
- Conectividad inalámbrica en otra revisión

### Licencia

Por definir.

### Créditos

Proyecto creado por **jhamilCTCT** para **Hack Club**.

---

## English

**Starbie** is a tiny motion-controlled digital pet inspired by a desktop Tamagotchi.  
This project is being developed as a custom **KiCad** board for **Hack Club**.

### Project idea

The goal of Starbie is to create a small and expressive virtual pet that can:
- react to motion,
- show animations on a small display,
- respond to user button input,
- make retro sounds through a buzzer.

Core project description:

> "A tiny motion-controlled digital pet, basically a desktop Tamagotchi"

### Main features

- Compact, low-cost microcontroller
- Motion sensor (IMU / accelerometer)
- I2C OLED display
- USB-C power input
- LiPo battery support
- On-board battery charging
- 3.3V regulation
- 3 user buttons
- Buzzer for sound feedback
- Status LEDs
- Debug pads/header
- Mounting holes and custom silkscreen

### Hardware architecture

#### Processing core
- **Seeed XIAO RP2040**

#### Motion sensing
- **LIS3DH** over I2C

#### Display
- **0.96\" SSD1306 I2C OLED**

#### Power
- **USB Type-C**
- **MCP73831** LiPo charging IC
- **AP2112K-3.3** LDO regulator
- **JST-PH 2.0** battery connector
- ON/OFF power switch

#### User interaction
- 3 push buttons
- Buzzer with NPN transistor driver
- Power LED
- User/status LED

### Design goals

- Stay close to the initial **$30 USD** budget
- Keep routing simple by using modules and shared buses
- Build a compact, understandable, and hand-assemblable PCB
- Create a solid base for future firmware and a 3D-printed enclosure

### Project status

Main files:
- `wara.kicad_sch`
- `wara.kicad_pcb`
- `wara.kicad_pro`

### Development plan

1. Complete schematic design
2. Run ERC validation
3. Assign footprints
4. Design PCB layout
5. Run DRC validation
6. Generate BOM and manufacturing files
7. Assemble and test hardware
8. Develop the digital pet firmware

### Planned silkscreen

The PCB will include:
- project name: **Starbie**
- author/user: **jhamilCTCT**
- hardware version: **v1.0**
- clear labels for connectors and pins

### Future improvements

- SPI color display
- More complex animations
- Low-power mode
- 3D-printed enclosure
- Extra touch input
- Wireless connectivity in a future revision

### License

To be decided.

### Credits

Created by **jhamilCTCT** for **Hack Club**.
