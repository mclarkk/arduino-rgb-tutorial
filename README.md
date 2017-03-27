# Instructions for using an Arduino to control RGB LEDs

These instructions cover how to use the Arduino to control an RGB LED. There are two stages to this process. The first stage is to take all the physical components (like the Arduino and LED) and assemble them into a circuit. The second stage is to program the Arduino to control the electrical signals in the circuit.

## Hookup Guide

To hook up all the physical components, first you will gather the parts, then you will connect them with wires.

### Overview of the parts

* 1 x [Arduino Uno](https://www.robomart.com/image/catalog/RM0058/02.jpg).
* 3 x [resistors](http://www.goldmine-elec-products.com/images/G440RB.jpg) with the right resistance values (see below).
* 1 x [RGB LED](https://i.stack.imgur.com/QCE8X.png).
* 4 x [male-to-male jumper wires](https://cdn.solarbotics.com/products/photos/03e0f1ccebb02b4dc5cc17e395d3049b/45040-dscn0624.jpg?w=800) or [standard stripped wires](https://cdn.instructables.com/FZ8/V12B/GYVDJLMY/FZ8V12BGYVDJLMY.MEDIUM.jpg). If the wire colors are red, blue, green, and black, it will make debugging easier, but is not strictly necessary.
* 1 x breadboard. They come in [half size](https://cdn-shop.adafruit.com/970x728/64-00.jpg) and [full size](https://www.electrokit.com/public/upload/productimage/41936-8616-4.jpg), either one is fine.

**Arduino Uno**:

**Resistors**: The most important thing about resistors for the purposes of this tutorial is that they can keep our LEDs from burning out. Our resistors are 220 Ohms. You can tell by putting their band color sequence (red, red, brown, gold) into a [resistor value calculator](http://www.digikey.com/en/resources/conversion-calculators/conversion-calculator-resistor-color-code-4-band). We picked 220 Ohms based on the properties of the particular RGB LEDs that we bought. A different LED might need a different resistor. If you want to learn more about resistors and how we picked the resistance value, you can scroll to the very bottom of this tutorial.

**RGB LED**: An RGB LED actually contains three tiny single-color LEDs inside: red, green, and blue. Here is the [datasheet for the particular brand of RGB LEDs](http://cdn.sparkfun.com/datasheets/Components/LED/YSL-R596AR3G4B5C-C10.pdf) we bought. We used the datasheet to determine that a 220 Ohm resistor would work with this LED (if you want details you can read the final section about resistors). However, you won't need to refer to the datasheet to complete the rest of this tutorial.

**Jumper wires**:

**Breadboard**: On

### How to connect the parts


## Programming the Arduino

Check board type and serial port.
Paste code in sketch (link to some programs).
Upload code.

Explain the building blocks.


## More Resources (Optional)

Here are some more links to tutorials about controlling RGB LEDs with Arduino:

* [Sparkfun tutorial](https://learn.sparkfun.com/tutorials/sik-experiment-guide-for-arduino---v32/experiment-3-driving-an-rgb-led)
* [Adafruit tutorial](https://learn.adafruit.com/adafruit-arduino-lesson-3-rgb-leds?view=all)

## Details About Resistors (Optional)
