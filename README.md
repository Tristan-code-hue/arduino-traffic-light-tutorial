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

## Arduino Code

The complete Arduino sketch is available in [`traffic_light.ino`](traffic_light.ino). It configures pins 8–10 as outputs and uses `digitalWrite()` to turn each LED on or off. The `delay()` calls control how long each light remains on.

```cpp
const int redLed = 10;
const int yellowLed = 9;
const int greenLed = 8;

void setup() {
  pinMode(redLed, OUTPUT);
  pinMode(yellowLed, OUTPUT);
  pinMode(greenLed, OUTPUT);
}

void loop() {
  // Green light: traffic may proceed.
  digitalWrite(greenLed, HIGH);
  digitalWrite(yellowLed, LOW);
  digitalWrite(redLed, LOW);
  delay(5000);

  // Yellow light: prepare to stop.
  digitalWrite(greenLed, LOW);
  digitalWrite(yellowLed, HIGH);
  digitalWrite(redLed, LOW);
  delay(2000);

  // Red light: traffic must stop.
  digitalWrite(greenLed, LOW);
  digitalWrite(yellowLed, LOW);
  digitalWrite(redLed, HIGH);
  delay(5000);
}
```

### How the Code Works

- `setup()` runs once when the Arduino starts and sets the LED pins as outputs.
- `loop()` runs repeatedly, switching through the green, yellow, and red phases.
- `HIGH` turns an LED on and `LOW` turns it off.
- The delays are measured in milliseconds: `5000` is 5 seconds and `2000` is 2 seconds.

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
