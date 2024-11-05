<!-- # djbr1.github.io -->

<!-- # FK 11 commit   https://github.com/k3ng/k3ng_cw_keyer/pull/80    -->
<!-- # FK 11 https://groups.io/g/radioartisan/topic/funtronics_fk_11_command_key/102553448   -->

<!-- ### Proof Of Concept -->
## Electronic Keyer with Integrated Load Sensor Paddles 
<!-- ### Arduino Nano / CS1237 ADC  -->
  (Author [Branko Djokic HB9TXB](https://www.qrz.com/db/hb9txb))  [![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/brankodjokic/) [![Facebook](https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white)](https://www.facebook.com/branko.djokic.3/)  [![A](https://img.shields.io/badge/X-%23000000.svg?style=for-the-badge&logo=x&label=share%20on%20twitter&logoColor=white&logoSize=auto)](https://twitter.com/intent/tweet?url=https://djbr1.github.io/&text=Electronic%20Keyer%20with%20Integrated%20Load%20Sensor%20Paddles&hashtags=keyer,iambic,paddle,morse,cwkeyer,hb9txb,morsecode) [![gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)]((mailto:bdjokic76%40gmail.com)) [![whatsapp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/41797532319)

<!--  [![View site - GH Pages](https://img.shields.io/badge/View_site-GH_Pages-2ea44f?style=for-the-badge)](https://djbr1.github.io/)  
| [![Twitter URL](https://img.shields.io/twitter/follow/djbr)](https://twitter.com/djbr)       -->





#### Goal: 
Affordable, feature-rich keyer with built-in  iambic paddle, easily assembled without specialised mechanical (machining) skills.


#### Why load sensor:
- In order to reduce backslash,  existing mechanical paddle design utilize ball bearings. It is an overkill as angular (rotational) movement is almost non-existent.
- Mechanical contacts prone to bouncing.
- Minimal contact distance (0.1 mm) and minimal force (10 grams) difficult to maintain with mechanical paddles.
- Load sensor  paddle is self calibrating whereas sensitivity is adjustable from command line interface separately for dot and dash.
- Load sensor paddle is an order of magnitude cheaper than mechanical paddles.
- Better reliability compared to capacitive touch paddle - behaves like customary mechanical paddle.

#### Features:
- Open source [**github repository**](https://github.com/djbr1/k3ng_cw_keyer/)
- Equally suitable for beginners and experts.
- Hardware components are cheap off-the-shelf  Arduino, load sensor and ADC.
- Can be developed as add-on to existing K3NG keyer kits.
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
 
 For prototype, [CS1237 ADC](https://github.com/tremaru/iarduino_ADC_CS1237) and [Arduino nano](https://github.com/djbr1/k3ng_cw_keyer) were used. 
 See  [**Schematic diagram**](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/k3ng_keyer_nano_cs1237.sch_2024-09-17.pdf) based on OK1CDJ nano keyer implementation.
   
 [![djbr1 - k3ng_cw_keyer](https://img.shields.io/static/v1?label=djbr1&message=k3ng_cw_keyer&color=blue&logo=github)](https://github.com/djbr1/k3ng_cw_keyer "Go to GitHub repo") [![stars - k3ng_cw_keyer](https://img.shields.io/github/stars/djbr1/k3ng_cw_keyer?style=social)](https://github.com/djbr1/k3ng_cw_keyer) [![forks - k3ng_cw_keyer](https://img.shields.io/github/forks/djbr1/k3ng_cw_keyer?style=social)](https://github.com/djbr1/k3ng_cw_keyer) | [![License](https://img.shields.io/badge/License-GPL-blue)](#license)


#### TODO:    
- PCB design
- BoM for additional components
- physical buttons as required
- optocouplers and 3.5 mm jacks for PPT and TX line
- RFI/EMI shielding
- "paddle only" output if transceiver builtin keyer is preferred

 <br/><br/>
 #### Pictures and videos
  ![](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1637.JPG?raw=true)  
![](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/k3ng_keyer_nano_cs1237.sch_2024-09-17.png?raw=true)

 <!--   ![](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1330.JPG?raw=true)  -->
 <!--   ![](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1329.JPG?raw=true)  -->
<!--    ![](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1344.JPG?raw=true)  -->

![](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/Screenshot_2024-09-17_at_18.34.58.jpg?raw=true)

<br/><br/>
[Youtube video showing paddle sensitivity](https://www.youtube.com/watch?v=UNnNl10UAn8)
<br/>
[![Sensitivity demo](https://img.youtube.com/vi/UNnNl10UAn8/0.jpg)](https://www.youtube.com/watch?v=UNnNl10UAn8)
<br/>





