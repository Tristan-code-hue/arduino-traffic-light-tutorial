# Arduino Traffic Light Tutorial

This project demonstrates how to build a simple traffic light using an Arduino Uno, three LEDs, and three resistors.

## Parts Required

- Arduino Uno
- Red LED
- Yellow LED
- Green LED
- Three 220 Ω or 330 Ω resistors
- Breadboard
- Jumper wires
- USB cable

## Wiring

Connect the LEDs as follows:

| LED | Arduino pin | Resistor |
|---|---:|---|
| Red | 10 | 220 Ω or 330 Ω |
| Yellow | 9 | 220 Ω or 330 Ω |
| Green | 8 | 220 Ω or 330 Ω |

For every LED:

1. Connect the Arduino pin to one side of a resistor.
2. Connect the other side of the resistor to the LED's long leg.
3. Connect the LED's short leg to `GND`.

Use one resistor per LED.

## Circuit Sequence

The traffic light operates in this order:

1. Green turns on for 5 seconds.
2. Yellow turns on for 2 seconds.
3. Red turns on for 5 seconds.
4. The sequence repeats.

## Uploading the Program

1. Open `traffic_light.ino` in the Arduino IDE.
2. Connect the Arduino Uno to your computer.
3. Select **Tools > Board > Arduino Uno**.
4. Select the correct port under **Tools > Port**.
5. Click the **Upload** button.
6. Wait for the upload to finish.
7. The traffic-light sequence should begin.

## Troubleshooting

### An LED does not turn on

- Make sure the LED is facing the correct direction.
- Check that the short leg is connected to `GND`.
- Check that the resistor and jumper wires are connected correctly.
- Confirm that the pin number in the code matches the wiring.

### Nothing works

- Confirm that the Arduino is receiving power.
- Check that the USB cable supports data.
- Verify that the correct board and port are selected.
- Make sure the program uploaded successfully.

### The LEDs are too bright or too dim

Use a resistor between 220 Ω and 1 kΩ. Never operate an LED without a resistor.
