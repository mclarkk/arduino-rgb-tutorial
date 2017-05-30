# Instructions for using an Arduino to control RGB LEDs

These instructions cover how to use the Arduino to control an RGB LED. There are two stages to this process. The first stage is to take all the physical components (like the Arduino and LED) and assemble them into a circuit. The second stage is to program the Arduino to control the electrical signals in the circuit.

## Hookup Guide

To hook up all the physical components, first you will gather the parts, then you will connect them with wires.

### Overview of the parts

* 1 x Arduino Uno ([pic](https://www.robomart.com/image/catalog/RM0058/02.jpg)). ([Buy on Adafruit](https://www.adafruit.com/product/50)) ([Buy on Sparkfun](https://www.sparkfun.com/products/11021))
* 3 x resistors ([pic](http://www.goldmine-elec-products.com/images/G440RB.jpg)) with the right resistance values (we provide 220 Ohm resistors). ([Buy](https://www.adafruit.com/product/2780)) <!--See the very bottom section on Details about Resistors if you're interested in how we got this number).-->
* 1 x RGB LED ([pic](https://i.stack.imgur.com/QCE8X.png)). LEDs come in "cathode" and "anode" flavors. The only difference is that cathode LEDs will be connected to ground (0V) and are turned on by setting the pin voltage high (e.g., 5V), whereas anode LEDs will be connected to high voltage (e.g., 5V) and turned on by setting the voltage low (0V). We suggest that beginners use cathodes because they are more intuitive to work with, but we happened to buy anodes for this exercise. ([Buy cathode](https://www.sparkfun.com/products/105)) ([Buy anode](https://www.sparkfun.com/products/10820))
* 4 x male-to-male jumper wires ([pic](https://cdn.solarbotics.com/products/photos/03e0f1ccebb02b4dc5cc17e395d3049b/45040-dscn0624.jpg?w=800)) or stripped wires ([pic](https://cdn.instructables.com/FZ8/V12B/GYVDJLMY/FZ8V12BGYVDJLMY.MEDIUM.jpg)). If the wire colors are red, blue, green, and black, it will make debugging easier, but is not strictly necessary. Don't be fooled by [male-to-female](https://cdn.sparkfun.com//assets/parts/2/9/8/7/09387-02.jpg) or [female-to-female](https://upload.wikimedia.org/wikipedia/commons/3/33/Female-Female_Jumper_Wire.jpg) jumpers! ([Buy](https://www.sparkfun.com/products/8431))
* 1 x breadboard. They come in [half size](https://cdn-shop.adafruit.com/970x728/64-00.jpg) and [full size](https://www.electrokit.com/public/upload/productimage/41936-8616-4.jpg), either one is fine. ([Buy](https://www.sparkfun.com/products/12002))
* 1 x USB A to B cable ([pic](https://shop.mchobby.be/142-thickbox_default/cable-usb-type-a-b-arduino-uno.jpg)). ([Buy](https://www.sparkfun.com/products/512))

**Arduino Uno**: The Arduino Uno is a board that allows you to connect a programmable microcontroller (the ATmega328, which is the big rectangle labeled on the right-hand side in [this diagram](http://www.jtagelectronics.com/wp-content/uploads/2015/08/Arduino-Uno-R3-with-Part-Labels.jpg)) to electrical circuits through pins. You can program the Arduino Uno using the [Arduino IDE](http://learn.linksprite.com/wp-content/uploads/2013/11/Arduino1Blink.png) application. Depending on the code you upload, the microcontroller will change the voltage on its pins in certain ways, which can be used to transmit information or control other components on any connected circuits.

**Resistors**: The most important thing about resistors for the purposes of this tutorial is that they can keep our LEDs and Arduino from burning out. Our resistors are 220 Ohms. You can tell by putting their band color sequence (red, red, brown, gold) into a [resistor value calculator](http://www.digikey.com/en/resources/conversion-calculators/conversion-calculator-resistor-color-code-4-band). We picked 220 Ohms based on the properties of the particular RGB LEDs that we bought. A different LED might need a different resistor. If you want to learn more about resistors and how we picked the resistance value, feel free to ask!<!--you can scroll to the very bottom of this tutorial.-->

**RGB LED**: An RGB LED actually contains three tiny single-color LEDs inside: one red, one green, and one blue. There are four pins on an RGB LED, one for each color and a fourth one that connects to low voltage (aka "ground") on cathode LEDs, or high voltage (e.g., 5V) for anode LEDs. We bought anodes, so our LEDs will connect to 5V.

<!--Here is the [datasheet for the particular brand of RGB LEDs](http://cdn.sparkfun.com/datasheets/Components/LED/YSL-R596AR3G4B5C-C10.pdf) we bought. We used the datasheet to determine that a 220 Ohm resistor would work with this LED (if you want details about this process feel free to ask!)<!--you can read the final section about resistors). We also used the datasheet to determine what pins should be connected to what. However, you won't need to refer to the datasheet to complete the rest of this tutorial. It's just here to show you what a datasheet looks like.-->

**Jumper wires**: Jumper wires are normal wires that have had attachments added to the ends to make them easier to connect to pins and breadboards and other circuit components. Stripped wires do not have those nice plastic attachments, so sometimes the ends can get bent and annoying to work with if you are connecting and disconnecting them often, but electrically they will work just as well.

**Breadboard**: Breadboards are a convenient way to connect a bunch of electrical components together into circuits. [This picture](http://dm.risd.edu/pbadger/PhysComp/uploads/Devices/LEDbreadboard4.jpg.jpg) shows how the holes are connected together in strips in most breadboards. There are two main parts: The _power rails_ (the vertical strips in the picture) and the _component rails_ (the horizontal strips). The _power rails_ run down the side of the breadboard. Technically you can connect any wire to those rails, but by convention we connect high voltage (for example, 5V) to the red rail labeled with + and we connect ground to the blue rail labeled with -. The _component rails_ are connected in horizontal rows. These rows do not connect across the gap in the middle. Generally you plug various components like (resistors or LEDs) into these rows, and then connect them to the power or ground rails, or to the Arduino.

**USB A to B cable**: The USB cable is how you will program and power your Arduino Uno and the electrical circuit.

### How to connect the parts

Now that you have your parts, it's time to put them together! [Here is the hookup diagram for our circuit](https://raw.githubusercontent.com/mclarkk/arduino-rgb-tutorial/master/Arduino_circuit.png). Your finished circuit will look like something like [this](https://cdn-learn.adafruit.com/guides/images/000/000/113/medium800/project_3_on_breadboard.jpg), except that the black wire will connect to 5V instead of ground. Note that our hookup diagram is for an anode LED. If you have a cathode LED, your black wire will connect to ground instead of 5V. All of the ground pins (marked GND) are connected on the Arduino, so you can use any GND pin you want.

The one thing the hookup diagram does not show is which of the LED pins are connected to which wires.

The LED's pins are numbered in order from Pin 1 to Pin 4. The longest pin of the LED is Pin 2. [Here is an illustration of the LED pin labels on a cathode LED](https://cdn.sparkfun.com/assets/learn_tutorials/3/6/0/RGBPinOUt.png). Since we are using anodes instead of cathodes, our LED's Pin 2 will connect to 5V instead of ground.

* LED Pin 1 controls red and is connected to the Arduino's Pin 9.
* LED Pin 2 is a power thing. In anodes like the ones we are using, it is connected to the Arduino's 5V pin. In cathodes, it is connected to the GND pin.
* LED Pin 3 controls green and is connected to the Arduino's Pin 10.
* LED Pin 4 controls blue and is connected to the Arduino's Pin 11.

Start connecting your circuit! Because the LED's pins are uneven lengths, you will almost certainly have to bend the pins to insert them all the way into the breadboard. Also, so long as no power is flowing through the circuit, you can connect things together in any order.

<!--A couple of things to note:

* Resistors can be connected in either orientation.
* Other brands of RGB LEDs may require connecting the longest LED pin to one of the Arduino GND (ground) pins instead of the Arduino's 5V pin.-->

## Programming the Arduino

Now that you have assembled your circuit, it's time to program the Arduino!

Install the [Arduino IDE](https://www.arduino.cc/en/main/software) application on your computer if you haven't already. IDE stands for Integrated Development Environment. The Arduino IDE is a code editor that will allow you to write and upload code to the Arduino and do other useful things.

Once the Arduino IDE is installed, open the Arduino application. Once open, go to `Tools > Board` and select Arduino Uno if it isn't already selected.

Next, plug your Arduino Uno into your computer using the USB A to B cable. Go to `Tools > Port` and select the Arduino device. Now you can start uploading programs!

Go to `File > New` then delete the template code in the new window and paste [this code](https://raw.githubusercontent.com/mclarkk/arduino-rgb-tutorial/master/adafruit_example.ino) into the window. Then click the round Upload button (the right-pointing arrow icon located second from the top left). You should see things happening on the bottom and then the message "Done uploading." Your Arduino should start going through some colors!

The example code is a good place to start playing around with controlling the LED! If you are using a cathode LED, setting the pin high for a particular color LED will turn that LED on, as you would expect. For an anode LED, setting it high will turn it _off_, and setting it low will turn it on.

Another program to try is [this one](https://raw.githubusercontent.com/mclarkk/arduino-rgb-tutorial/master/rainbow_fade.ino). It will flash through the colors and then fade smoothly though the colors. There are a lot of comments in the code, but the code itself is simpler than the length of the file would suggest.

## More Resources (Optional)

Here are some more links to tutorials about controlling RGB LEDs with Arduino:

* [Sparkfun tutorial](https://learn.sparkfun.com/tutorials/sik-experiment-guide-for-arduino---v32/experiment-3-driving-an-rgb-led)
* [Adafruit tutorial](https://learn.adafruit.com/adafruit-arduino-lesson-3-rgb-leds?view=all)

<!---## Details About Resistors (Optional)

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

Therefore we know that any resistor with a value between A and B will be safe for our circuit. We picked 220 Ohms because we happened to have them lying around.-->
