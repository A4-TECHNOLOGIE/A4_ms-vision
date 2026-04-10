# A4_ms-vision
Extension MakeCode pour la maquette ms-vision




# pxt-DFRobot_lcdDisplay_uart

MakeCode extension for the DFRobot 2-inch color display with I2C and UART support.

This fork adds UART support for the display so it can be used without sharing the I2C bus.

## UART wiring

Important: UART wiring must be crossed.

- Display **R** -> controller **TX**
- Display **T** -> controller **RX**

## Display mode

Set the display DIP switch to **UART/Serial** mode before using UART functions.

## Validated UART baud rate

Use **9600** baud.

115200 was tested and did not work on the target hardware.

## Example

```typescript
lcdDisplay.lcdInitUART9600(SerialPin.P8, SerialPin.P12)
lcdDisplay.lcdSetBgcolor(0x001F)
lcdDisplay.lcdDisplayText("UART OK", 1, 120, 120, lcdDisplay.FontSize.Large, 0xFFFFFF)
