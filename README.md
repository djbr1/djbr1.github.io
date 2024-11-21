<!-- # djbr1.github.io -->

## Electronic Keyer with Integrated Load Sensor Paddles 
#### (Author [Branko Djokic HB9TXB](https://www.qrz.com/db/hb9txb))     
   [![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/brankodjokic/) [![Facebook](https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white)](https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fblog.djokic.sh%2F&amp;src=sdkprepars)  [![A](https://img.shields.io/badge/X-%23000000.svg?style=for-the-badge&logo=x&label=share%20on%20twitter&logoColor=white&logoSize=auto)](https://twitter.com/intent/tweet?url=https://blog.djokic.ch/&text=Electronic%20Keyer%20with%20Integrated%20Load%20Sensor%20Paddles&hashtags=keyer,iambic,paddle,morse,cwkeyer,hb9txb,morsecode) [![gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:bdjokic76%40gmail.com) [![whatsapp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/41797532319)

<!--  [![View site - GH Pages](https://img.shields.io/badge/View_site-GH_Pages-2ea44f?style=for-the-badge)](https://djbr1.github.io/)  
| [![Twitter URL](https://img.shields.io/twitter/follow/djbr)](https://twitter.com/djbr)      

https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fblog.djokic.sh%2F&amp;src=sdkpreparse
-->




#### Goal: 
Affordable, feature-rich keyer with built-in  iambic paddle, easily assembled without specialised mechanical (machining) skills.


#### Why load sensor:
- In order to reduce backslash,  existing mechanical paddle design utilize ball bearings. It is an overkill as angular (rotational) movement is almost non-existent.
- Mechanical contacts prone to bouncing.
- Minimal contact distance (0.1 mm) and minimal force (10 grams) difficult to maintain with mechanical paddles.
- Load sensor  paddle is self calibrating whereas sensitivity is adjustable from command line interface separately for dot and dash.
- Load sensor paddle is an order of magnitude cheaper than mechanical paddles.
- Better reliability compared to capacitive touch paddle - behaves like customary mechanical paddle.


### Implementation on top of well-known kits: [OE1WKL Morserino-32](#oe1wkl-morserino-32-v6-with-load-sensor-add-on) and [K3NG keyer](#k3ng-keyer-with-load-sensor-add-on)

#### [OE1WKL Morserino-32 v6](https://github.com/djbr1/Morserino-32) with load sensor add-on
**Hardware additions to original Morserino**:
- ESP32 free pin 13 configured as CLK for ADC sensors, one wire soldered
- Pins 2 and 12 formerly used for capacitive touch paddle configured as DATA for two ADC 
- GND and 3.3VEXT taken from JMP1 free holes.
- Breadboard with 2 x CS1237 ADC plus two load sensors

As there were no free pins on Heltec ESP32, capacitive touch and load pressor sensor functionality cannot be present in the same time.Load sensor is activated using preprocessor directive `#define FEATURE_PRESSURE_PADDLES` in `morsedefs.h`.

[![Morserino Image](https://raw.githubusercontent.com/djbr1/Morserino-32/master//Documentation/Hardware/IMG_1763_small.JPG?raw=true)](https://raw.githubusercontent.com/djbr1/Morserino-32/master//Documentation/Hardware/IMG_1763.JPG?raw=true)
[![Morserino Image](https://raw.githubusercontent.com/djbr1/Morserino-32/master//Documentation/Hardware/IMG_1812_small.JPG?raw=true)](https://raw.githubusercontent.com/djbr1/Morserino-32/master//Documentation/Hardware/IMG_1812.JPG?raw=true)

Load sensor paddles sensitivity can be changed using `m32command` syntax through web serial. It works through serial console (eg picocom, minicom, putty) or using browser (Chrome,Opera or Edge).
Controls for sensitivity are supported in Morserino code and in HTML pages<br>
`GET control/pstdot`<br>
`GET control/pstdash`<br>
`PUT control/pstdot/<value>`<br>
`PUT control/pstdash/<value>`<br>

[My fork of Christof Dallermassl OE6CHD Morserino CW trainer](https://github.com/djbr1/morserino32-trainer) provides [HTML](https://github.com/djbr1/morserino32-trainer/blob/main/sensor.html) for this purpose

[![web serial console screenshot](https://github.com/djbr1/Morserino-32/blob/master/Documentation/Hardware/sensor.html_small.jpg?raw=true)](https://github.com/djbr1/Morserino-32/blob/master/Documentation/Hardware/sensor.html.jpg?raw=true)

<br>
<!-- TODO:  single lever functionality ie using just one load sensor - preferred by HST competitors.  -->
Youtube shorts demo:
[![morserino32 shorts youtube](https://img.youtube.com/vi/P5Paj6hcao0/0.jpg)](https://www.youtube.com/watch?v=P5Paj6hcao0)


[![djbr1 - morserino32](https://img.shields.io/static/v1?label=djbr1&message=morserino-32&color=blue&logo=github)](https://github.com/djbr1/morserino-32 "Go to GitHub repo") [![stars - morserino-32](https://img.shields.io/github/stars/djbr1/morserino-32?style=social)](https://github.com/djbr1/morserino-32) [![forks - morserino-32](https://img.shields.io/github/forks/djbr1/morserino-32?style=social)](https://github.com/djbr1/morserino-32) | [![License](https://img.shields.io/badge/License-GPL-blue)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/LICENSE)




#### [K3NG keyer](https://github.com/djbr1/k3ng_cw_keyer/) with load sensor add-on

#### Features (K3NG addon):
- Equally suitable for beginners and experts.
- Hardware components are cheap off-the-shelf  Arduino, load sensor and ADC.
- Can be developed as add-on to existing K3NG keyer kits 
- Configurable "single lever" mode: Tip from right paddle can be unscrewed and only left paddle is used as classic single paddle, as if it would have two sets of contacts for dot and dash.  (not to be confused with "single mode" where iambic mode is inhibited however both paddles are used) 
- Command line interface is available through USB interface using Serial Terminal (Putty, iTerm ...) or  [Web Serial ](https://github.com/ok1cdj/K3NG-keyer-serial-terminal)from laptop,  or [Android Serial Terminal app](https://play.google.com/store/apps/details?id=de.kai_morich.serial_usb_terminal) from handset.
 
- All [K3NG keyer capabilities ](https://github.com/k3ng/k3ng_cw_keyer/wiki) available:
    * CW speed adjustable from 1 to 999 WPM
  * Up to six selectable transmitter keying lines
  * Programming and interfacing via USB port (“command line interface”)
  * [USB or PS2 Keyboard Interface](https://github.com/k3ng/k3ng_cw_keyer/wiki/340-Feature:-Keyboard-&-Mouse#ps2--usb-keyboard-interface) for CW keyboard operation without a computer
  * Logging and Contest Program Interfacing via K1EL Winkey 1.0 and 2.0 interface protocol emulation
  * Optional PTT outputs with configurable lead, tail, and hang times
  * Optional LCD Display – [Classic 4 bit mode](http://arduino.cc/en/Tutorial/LiquidCrystal) , [Adafruit I2C RGB](http://ladyada.net/make/rgblcdshield/) display and [I2C Character Backpack](https://www.adafruit.com/product/292) or [YourDuino I2C LCD Display](http://arduino-info.wikispaces.com/LCD-Blue-I2C)
  * Up to 12 memories with macros
  * Serial numbers
  * CW keyboard (via a terminal server program like Putty or the Arduino Serial program)
  * [Speed potentiometer](https://github.com/k3ng/k3ng_cw_keyer/wiki/360-Feature:-Speed-Control) (optional – speed also adjustable with commands)
  * [QRSS and HSCW](https://github.com/k3ng/k3ng_cw_keyer/wiki/392-Feature:-QRSS-(Slow-Speed-CW)-and-HSCW-(High-Speed-CW))
  * [Beacon / Fox mode](https://github.com/k3ng/k3ng_cw_keyer/wiki/850-Beacon-Operation)
  * [Iambic A and B modes](https://github.com/k3ng/k3ng_cw_keyer/wiki/400-Operating-Modes#iambic-modes)
  * Single lever paddle mode
  * [Straight key support](https://github.com/k3ng/k3ng_cw_keyer/wiki/400-Operating-Modes#straight-key-support)
  * [Ultimatic mode](https://github.com/k3ng/k3ng_cw_keyer/wiki/400-Operating-Modes#ultimatic-mode)
  * [Bug mode](https://github.com/k3ng/k3ng_cw_keyer/wiki/400-Operating-Modes#bug-mode)
  * [CMOS Super Keyer Iambic B Timing](https://github.com/k3ng/k3ng_cw_keyer/wiki/400-Operating-Modes#cmos-super-keyer-timing)
  * [Paddle reverse](https://github.com/k3ng/k3ng_cw_keyer/wiki/400-Operating-Modes#paddle-reverse)
  * [Hellschreiber mode](https://github.com/k3ng/k3ng_cw_keyer/wiki/395-Feature:-Hellschreiber) (keyboard sending, memory macro, beacon)
  * Farnsworth Timing
  * Adjustable frequency sidetone
  * Sidetone disable / sidetone high/low output for keying outboard audio oscillator
  * [Command mode](https://github.com/k3ng/k3ng_cw_keyer/wiki/320-Feature:-Command-Mode) for using the paddle to change settings, program memories, etc.
  * Keying Compensation
  * [Dah to Dit Ratio adjustment](https://github.com/k3ng/k3ng_cw_keyer/wiki/410-Timing-Adjustments#cw-dah-to-dit-ratio-adjust)
  * Weighting
  * [Callsign receive practice](https://github.com/k3ng/k3ng_cw_keyer/wiki/495-CW-Training-Functionality#receive-and-keyboard-interactive-receive-practice)
  * Send practice
  * Memory stacking
  * [“Dead Operator Watchdog”](https://github.com/k3ng/k3ng_cw_keyer/wiki/381-Feature:-Dead-Operator-Watchdog)
  * [Autospace](https://github.com/k3ng/k3ng_cw_keyer/wiki/410-Timing-Adjustments#autospace)
  * Wordspace Adjustment
  * [Pre-configured and Custom Prosigns](https://github.com/k3ng/k3ng_cw_keyer/wiki/425-Prosigns)
  * Non-volatile storage of most settings
  * Modular code design allowing selection of features and easy code modification
  * Non-English Character Support
  * [CW Receive Decoder](https://github.com/k3ng/k3ng_cw_keyer/wiki/385-Feature:-CW-Decoder)
  * [Rotary Encoder Speed Control](https://github.com/k3ng/k3ng_cw_keyer/wiki/360-Feature:-Speed-Control#rotary-encoder-speed-control)
  * [Sleep Mode](https://github.com/k3ng/k3ng_cw_keyer/wiki/387-Feature:-Sleep)
  * [USB Mouse Support](https://github.com/k3ng/k3ng_cw_keyer/wiki/340-Feature:-Keyboard-&-Mouse#usb-mouse)
  * [Mayhew LED Ring Support](https://github.com/k3ng/k3ng_cw_keyer/wiki/360-Feature:-Speed-Control#mayhew-labs-led-ring)
  * [Alphabet Sending Practice](https://github.com/k3ng/k3ng_cw_keyer/wiki/495-CW-Training-Functionality#alphabet-send-practice)
  * QLF / “Messy” Straight Key Emulation
  * [USB Keyboard HID](https://github.com/k3ng/k3ng_cw_keyer/wiki/340-Feature:-Keyboard-&-Mouse#usb-keyboard) (Human Interface Device) Interface (Keyer = keyboard for your computer)
  * [TX/RX Sequencer](https://github.com/k3ng/k3ng_cw_keyer/wiki/383-Feature:-Sequencer)
  * [Training Module](https://github.com/k3ng/k3ng_cw_keyer/wiki/400-CW-Training-Functionality)


#### Prototype:
 
 Basic prototype was built using [CS1237 ADC](https://github.com/tremaru/iarduino_ADC_CS1237) and [Arduino nano](https://github.com/djbr1/k3ng_cw_keyer).
 Also prototypes using ESP32 and Arduino Mega2560 were made where all k3ng keyer features can be activated.
 [**Schematic diagram**](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/k3ng_keyer_nano_cs1237.sch_2024-09-17.pdf) is based on OK1CDJ nano keyer implementation.
 For testing purpose see [**breadboard** using only Arduino Nano, ADC and passive buzzer ](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/nano_cs1237_keyer_k3ng_bb.png).
Arduino, speaker and breadboard are readily available.  [ADC1237](https://www.aliexpress.com/item/1005005412390535.html) and [Load Sensor 300gr](https://www.aliexpress.com/item/1644918827.html) are from Alix.
   
 [![djbr1 - k3ng_cw_keyer](https://img.shields.io/static/v1?label=djbr1&message=k3ng_cw_keyer&color=blue&logo=github)](https://github.com/djbr1/k3ng_cw_keyer "Go to GitHub repo") [![stars - k3ng_cw_keyer](https://img.shields.io/github/stars/djbr1/k3ng_cw_keyer?style=social)](https://github.com/djbr1/k3ng_cw_keyer) [![forks - k3ng_cw_keyer](https://img.shields.io/github/forks/djbr1/k3ng_cw_keyer?style=social)](https://github.com/djbr1/k3ng_cw_keyer) | [![License](https://img.shields.io/badge/License-GPL-blue)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/LICENSE)<br>

#### TODO:    
- PCB design
- BoM for additional components
- physical buttons as required
- optocouplers and 3.5 mm jacks for PPT and TX line
- RFI/EMI shielding
- "paddle only" output if transceiver builtin keyer is preferred

#### Feel free to post your questions and comments.
Github login required for posting comments. If you dont have github account, you may contact by email or social networks.
<script src="https://utteranc.es/client.js"
        repo="djbr1/djbr1.github.io"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>


 

`Everyone is allowed to use this software to build their own kit or assembled unit (even for commercial use) as long as the `[`GPL v3 license`](https://github.com/djbr1/k3ng_cw_keyer/blob/master/LICENSE)` is respected.`



#### Pictures and videos (click for larger):
<!--[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/IMG_1637.JPG?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1637.JPG?raw=true)  -->
[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/IMG_1637-EDIT.jpg?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1637.JPG?raw=true) 
[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/k3ng_keyer_nano_cs1237.sch_2024-09-17.png?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/k3ng_keyer_nano_cs1237.sch_2024-09-17.png?raw=true)
[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/nano_cs1237_keyer_k3ng_bb.png?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/nano_cs1237_keyer_k3ng_bb.png?raw=true)
[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/IMG_1737-EDIT.jpg?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1737-EDIT.JPG?raw=true) 
[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/Screenshot_2024-09-17_at_18.34.58.jpg?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/Screenshot_2024-09-17_at_18.34.58.jpg?raw=true)

 <!--   ![](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1330.JPG?raw=true)  -->
 <!--   ![](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1329.JPG?raw=true)  -->
<!--    ![](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1344.JPG?raw=true)  -->




[Youtube video showing paddle sensitivity](https://www.youtube.com/watch?v=UNnNl10UAn8)

[![Sensitivity demo](https://img.youtube.com/vi/UNnNl10UAn8/0.jpg)](https://www.youtube.com/watch?v=UNnNl10UAn8)





