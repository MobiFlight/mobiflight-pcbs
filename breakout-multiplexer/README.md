# MobiFlight Multiplexer Breakout Board
The MobiFlight Multiplexer Breakout Board is a breakout board for easier use of the 74HC4067 multiplexer.

On the top side, The board uses XH JST connectors for the individual inputs. On the back, you can add up to two 74HC4067 modules (https://shop.mobiflight.com/product/multiplexer).

On the bottom side, you plug in the 74HC4067 modules. Version 1.2 now shows information about the orientation and all important pins are labeled.
You can daisy chain the boards.

For more information on how to configure the board with MobiFlight, check out the [MobiFlight Connector documentation](https://github.com/MobiFlight/MobiFlight-Connector/wiki/Input-and-Output-devices#input-multiplexer).

## Board overview
![Top View](breakout-multiplexer-top.png)

### Multiplexer IN
Connection coming from your Mobiflight board, or another MobiFlight Multiplexer Breakout Board as daisy chain.

* Pin1 - GND
* Pin2 - VCC
* Pin3 - Channel 1
* Pin4 - Channel 2
* Pin5 - Channel 3
* Pin6 - Channel 4

### Data 0
Connection coming from your Mobiflight board.

* Pin1 - GND
* Pin2 - Signal pin (for the first 74HC4067)

### Data 1
Connection coming from your Mobiflight board.

* Pin1 - GND
* Pin2 - Signal pin (for the second 74HC4067)

### Multiplexer OUT
Connection to daisy chain another MobiFlight Multiplexer Breakout Board.

* Pin1 - GND
* Pin2 - VCC
* Pin3 - Channel 1
* Pin4 - Channel 2
* Pin5 - Channel 3
* Pin6 - Channel 4

### Button01-08
First row of connectors for input devices buttons and switches:

* Pin1 - Connection TO switch
* Pin2 - Connection FROM switch

Polarity doesn't matter for switches.

### Button09-16
Second row of connectors for input devices buttons and switches:

* Pin1 - Connection TO switch
* Pin2 - Connection FROM switch

Polarity doesn't matter for switches.

### Button 17-24
First row of connectors for input devices buttons and switches:

* Pin1 - Connection TO switch
* Pin2 - Connection FROM switch

Polarity doesn't matter for switches.

### Button 25-32
Second row of connectors for input devices buttons and switches:

* Pin1 - Connection TO switch
* Pin2 - Connection FROM switch

Polarity doesn't matter for switches.

## Mounting of 74HC4067 modules
![Mounting orientation 74HC4067 modules](breakout-multiplexer-74hc4067.png)

As one can see on the picture, the 74HC4067 are mounted with the silkscreen facing up. Due to the asymmetric connectors, the orientation cannot be confused.

## MobiFlight Configuration

If you are using an Arduino Mega, connect the first two pins on the ** Multiplexer In** connector to GND, 5V and the four remaining pins to free Arduino pins, like D2, D3 D4 and D5. These pins are shared by both multiplexers and are already connected to both on the board.

Connect another two data pins to Data0 and Data1 connectors, the first pin is again GND, in case you are using a premade connector. The rightmost pins are the data pins, and you can verify these on the backside of the curcuit board where the pins are labeled as well. 

![image](https://github.com/MobiFlight/mobiflight-pcbs/assets/2587818/d38acea9-0853-4c9f-adc7-96773ab6a843)

You should first add one multiplexer device with the four data pins configured as follows, and select also the pin connected to Data0. Data1 will be assidned to a another Multiplexer device we add after this one.

![226143462-3bedf9fe-c78f-402c-b73f-0bc42e2be1f8](https://github.com/MobiFlight/mobiflight-pcbs/assets/2587818/4343863f-7fe1-492a-b9ed-07e8d59b0a64)

For the second multiplexer add another multiplexer device from the menu, the four selector pins will be the same, and the **data pin** will a unique one for the second multiplexer, D7 for example.

Click "Upload config" and your device should work.

## Case
You can print a case for the board [using this STL file](breakout-multiplexer-case.stl) for better handling and look:

![Case Preview](breakout-multiplexer-case-preview.png)

![Case Preview](breakout-multiplexer-case-preview-2.png)

## Additional information

### Bottom side
![Top View](breakout-multiplexer-bottom.png)

### Schematic
![Schematic](schematic.png)
