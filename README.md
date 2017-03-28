# Instructions for using an Arduino to control RGB LEDs

These instructions cover how to use the Arduino to control an RGB LED. There are two stages to this process. The first stage is to take all the physical components (like the Arduino and LED) and assemble them into a circuit. The second stage is to program the Arduino to control the electrical signals in the circuit.

## Hookup Guide

To hook up all the physical components, first you will gather the parts, then you will connect them with wires.

### Overview of the parts

* 1 x [Arduino Uno](https://www.robomart.com/image/catalog/RM0058/02.jpg).
* 3 x [resistors](http://www.goldmine-elec-products.com/images/G440RB.jpg) with the right resistance values (we provide 220 Ohm resistors. See the very bottom section on Details about Resistors if you're interested in how we got this number).
* 1 x [RGB LED](https://i.stack.imgur.com/QCE8X.png).
* 4 x [male-to-male jumper wires](https://cdn.solarbotics.com/products/photos/03e0f1ccebb02b4dc5cc17e395d3049b/45040-dscn0624.jpg?w=800) or [stripped wires](https://cdn.instructables.com/FZ8/V12B/GYVDJLMY/FZ8V12BGYVDJLMY.MEDIUM.jpg). If the wire colors are red, blue, green, and black, it will make debugging easier, but is not strictly necessary.
* 1 x breadboard. They come in [half size](https://cdn-shop.adafruit.com/970x728/64-00.jpg) and [full size](https://www.electrokit.com/public/upload/productimage/41936-8616-4.jpg), either one is fine.
* 1 x [USB A to B cable](https://shop.mchobby.be/142-thickbox_default/cable-usb-type-a-b-arduino-uno.jpg)

**Arduino Uno**: The [Arduino Uno]((https://www.robomart.com/image/catalog/RM0058/02.jpg)) is a board that allows you to connect a programmable microcontroller (the ATmega328, which is labeled in [this diagram](http://www.jtagelectronics.com/wp-content/uploads/2015/08/Arduino-Uno-R3-with-Part-Labels.jpg)) to electrical circuits through pins. You can program the Arduino Uno using the [Arduino IDE](http://learn.linksprite.com/wp-content/uploads/2013/11/Arduino1Blink.png) application. Depending on the program you upload, the microcontroller will change the voltage on its pins in certain ways, which can be used to transmit information or control other components on any connected circuits.

**Resistors**: The most important thing about [resistors](http://www.goldmine-elec-products.com/images/G440RB.jpg) for the purposes of this tutorial is that they can keep our LEDs and Arduino from burning out. Our resistors are 220 Ohms. You can tell by putting their band color sequence (red, red, brown, gold) into a [resistor value calculator](http://www.digikey.com/en/resources/conversion-calculators/conversion-calculator-resistor-color-code-4-band). We picked 220 Ohms based on the properties of the particular RGB LEDs that we bought. A different LED might need a different resistor. If you want to learn more about resistors and how we picked the resistance value, you can scroll to the very bottom of this tutorial.

**RGB LED**: An [RGB LED](https://i.stack.imgur.com/QCE8X.png) actually contains three tiny single-color LEDs inside: one red, one green, and one blue. There are four pins on an RGB LED, one for each color and a fourth one for either ground or high voltage depending on the design of your LED.

Here is the [datasheet for the particular brand of RGB LEDs](http://cdn.sparkfun.com/datasheets/Components/LED/YSL-R596AR3G4B5C-C10.pdf) we bought. We used the datasheet to determine that a 220 Ohm resistor would work with this LED (if you want details you can read the final section about resistors). We also used the datasheet to determine what pins should be connected to what. However, you won't need to refer to the datasheet to complete the rest of this tutorial. It's just here to show you what a datasheet looks like.

**Jumper wires**: [Jumper wires]((https://cdn.solarbotics.com/products/photos/03e0f1ccebb02b4dc5cc17e395d3049b/45040-dscn0624.jpg?w=800)) are normal wires that have had attachments added to the ends to make them easier to connect to pins and breadboards and other circuit components.

**Breadboard**: Breadboards are a convenient way to connect a bunch of electrical components together into circuits. [This picture](http://dm.risd.edu/pbadger/PhysComp/uploads/Devices/LEDbreadboard4.jpg.jpg) shows how the holes are connected together in strips in most breadboards. There are two main parts: The _power rails_ (the vertical strips in the picture) and the _component rails_ (the horizontal strips). The _power rails_ run down the side of the breadboard. Technically you can connect any wire to those rails, but by convention we connect high voltage (for example, 5V) to the red rail labeled with + and we connect ground to the blue rail labeled with -. The _component rails_ are connected in horizontal rows. These rows do not connect across the gap in the middle. Generally you plug various components like (resistors or LEDs) into these rows, and then connect them to the power or ground rails, or to the Arduino.

**USB A to B cable**: [This cable]((https://shop.mchobby.be/142-thickbox_default/cable-usb-type-a-b-arduino-uno.jpg)) is how you will program and power your Arduino Uno and the electrical circuit.

### How to connect the parts

Here is a connection diagram: http://www.letsarduino.com/wp-content/uploads/2014/11/Project-6-RGB-LED-Control-With-Arduino1.jpg

Or this, but it has ground: https://cdn.sparkfun.com/assets/learn_tutorials/3/1/0/Arduino_circuit_02_01.png

I want a diagram that connects to the right pins and has colored wires.

The longest pin of the LED is Pin 2, which corresponds to the black wire in the diagram. LED Pin 1 controls red and is connected to the Arduino's Pin 11. LED Pin 2 is a power thing and is connected to the Arduino's 5V pin (other brands of RGB LEDs may require being connected to the GND pin instead). LED Pin 3 controls green and is connected to the Arduino's Pin 10. LED Pin 4 controls blue and is connected to the Arduino's Pin 11.

A couple of things to note:
* It doesn't matter which way you connect the resistors.
* Other brands of RGB LEDs may require connecting the longest LED pin to one of the Arduino GND (ground) pins instead of the Arduino's 5V pin.

## Programming the Arduino

Install the [Arduino IDE](https://www.arduino.cc/en/main/software) application on your computer if you haven't already. IDE stands for Integrated Development Environment. The Arduino IDE is a code editor that will allow you to write and upload code to the Arduino and do other useful things.

Once the Arduino IDE is installed, open the Arduino application. Once open, go to `Tools > Board` and select Arduino Uno if it isn't already selected.

Next, plug your Arduino Uno into your computer using the USB A to B cable. Go to `Tools > Port` and select the Arduino device. Now you can start uploading programs!

Paste code in sketch (link to some programs).

Upload code.

Explain the building blocks.


## More Resources (Optional)

Here are some more links to tutorials about controlling RGB LEDs with Arduino:

* [Sparkfun tutorial](https://learn.sparkfun.com/tutorials/sik-experiment-guide-for-arduino---v32/experiment-3-driving-an-rgb-led)
* [Adafruit tutorial](https://learn.adafruit.com/adafruit-arduino-lesson-3-rgb-leds?view=all)

## Details About Resistors (Optional)

In case you're not sure what voltage and current are: To help with your intuition, you can think about electricity in a circuit like water in a river.

**Voltage**: To understand voltage, imagine a waterfall. Voltage is like the amount of force with which the water hits the lower river. That force depends on the height difference between the upper river and the lower river. That means that voltage is always a relative quantity between two things. If you have a single wire there is no voltage. In electronics, voltage is the _potential difference_ between two points in a circuit.

**Current**: You can think of current as the volume of water flowing through the circuit.

### Our Problem

Our problem is that too much current can destroy our LED and potentially our Arduino as well! Resistors can help save our parts from burning out.

How do resistors work? Resistors define the relationship between voltage and current. You might have come across the following law before:

```
V = IR
```

Where V is the voltage in volts, I is the current in Amperes, and R is the resistance in Ohms.

Generally, two of these three quantities are fixed and you want to find the third one. In our case, we know what voltage and current values we want. The voltage that we have available from our Arduino is 5V, and we want the voltage to be zero by the time it makes it to the other side of the LED.

and we want to get the resistance. So we can rearrange `V = IR` to calculate `R` given `V` and `I`:

```
R = V/I
```

The voltage that we have available from our Arduino is 5V. We want the voltage to be zero by the time it makes it to the other side of the LED. The "forward voltage" of the LED is X, which means that it which leaves 5-X=Y amount of extra voltage that we want to drop. We also know from the LED datasheet and Arduino pin limits that we want no more than Z amount of current.

Red: Min forward voltage is 1.8 max is 2.2 typical is 2.0. Needs 20 mA of current.

```
R = (5 - 1.8)/0.02 = 160 Ohms   #highest
R = (5 - 2.2)/0.02 = 140 Ohms   #lowest
R = (5 - 2.0)/0.02 = 150 Ohms   #typical
```

We can actually go higher than 160 Ohms, but it will reduce the current resulting in a dimmer red LED.

Green and Blue: Min forward voltage is 3.0 max is 3.4 typical is 3.1. Also needs 20 mA of current.

```
R = (5 - 3.0)/0.02 = 100 Ohms   #highest
R = (5 - 3.4)/0.02 = 80 Ohms    #lowest
R = (5 - 3.1)/0.02 = 95 Ohms    #typical
```

Therefore we know that any resistor with a value between A and B will be safe for our circuit. We picked 220 Ohms because we happened to have them lying around.
