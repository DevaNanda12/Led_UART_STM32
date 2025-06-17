# STM32 UART LED Toggle Project

This project demonstrates how to toggle the onboard LED on an STM32 Nucleo-F446RE board via UART communication.

---

## Board Used
- STM32 Nucleo-F446RE

## Tools
- STM32CubeIDE
- HAL Drivers

## Project Overview

The project configures USART2 to receive UART data at 115200 baud using interrupt-driven communication. When the character `'b'` is received over UART, the onboard LED connected to **pin PA5** toggles its state (ON to OFF or OFF to ON).

## How It Works

- **UART Configuration**: USART2 is initialized for TX/RX at 115200 baud.
- **GPIO Setup**: Pin PA5 is set as an output to control the built-in LED.
- **Interrupt-based UART Reception**: The MCU continuously listens for UART data using interrupts.
- **Callback Function**: Upon receiving the character `'b'`, the LED toggles.

The main loop (`while(1)`) is empty as all UART handling and LED toggling happens inside the UART receive interrupt callback.

## UART Command Summary

| Input Character | Action           |
|-----------------|------------------|
| `'b'`           | Toggle onboard LED |

## How to Use

1. Clone or download the project.
2. Open it in STM32CubeIDE.
3. Build and flash the firmware to the STM32 Nucleo-F446RE board.
4. Open a serial terminal (e.g., CoolTerm) connected to USART2 at 115200 baud.
5. Send the character `b` to toggle the LED.

## Pinout

| Signal | Pin  | Description        |
|--------|-------|--------------------|
| LED    | PA5   | Onboard LED output |
| USART2 TX | PA2 | UART transmit      |
| USART2 RX | PA3 | UART receive       |

## Author

- Deva Nanda S

---

## License

This project is licensed under the MIT License.
