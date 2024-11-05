<!-- # djbr1.github.io -->

<!-- # FK 11 commit   https://github.com/k3ng/k3ng_cw_keyer/pull/80    -->
<!-- # FK 11 https://groups.io/g/radioartisan/topic/funtronics_fk_11_command_key/102553448   -->

### Proof Of Concept 
## Electronic Keyer with Integrated Load Sensor Paddles 
### Arduino Nano / CS1237 ADC 
  (Author [HB9TXB](https://www.qrz.com/db/hb9txb))



<!-- |||||
|:---:|:---:|:---:|:---:| -->
 [![djbr1 - k3ng_cw_keyer](https://img.shields.io/static/v1?label=djbr1&message=k3ng_cw_keyer&color=blue&logo=github)](https://github.com/djbr1/k3ng_cw_keyer "Go to GitHub repo") [![stars - k3ng_cw_keyer](https://img.shields.io/github/stars/djbr1/k3ng_cw_keyer?style=social)](https://github.com/djbr1/k3ng_cw_keyer) [![forks - k3ng_cw_keyer](https://img.shields.io/github/forks/djbr1/k3ng_cw_keyer?style=social)](https://github.com/djbr1/k3ng_cw_keyer) | [![License](https://img.shields.io/badge/License-GPL-blue)](#license)

[![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/brankodjokic/) [![Facebook](https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white)](https://www.facebook.com/branko.djokic.3/)  [![A](https://img.shields.io/badge/X-%23000000.svg?style=for-the-badge&logo=x&label=share%20on%20twitter&logoColor=white&logoSize=auto)](https://twitter.com/intent/tweet?url=https://djbr1.github.io/&text=Electronic%20Keyer%20with%20Integrated%20Load%20Sensor%20Paddles&hashtags=keyer,iambic,paddle,morse,cwkeyer,hb9txb,morsecode) [![gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)]((mailto:bdjokic76%40gmail.com)) [![whatsapp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/41797532319)

<!--  [![View site - GH Pages](https://img.shields.io/badge/View_site-GH_Pages-2ea44f?style=for-the-badge)](https://djbr1.github.io/)  
| [![Twitter URL](https://img.shields.io/twitter/follow/djbr)](https://twitter.com/djbr)       -->





#### Goal: 
Affordable, powerful and flexible keyer with built-in reliable iambic paddle, easily built without specialised mechanical (machining) skills.


#### Why load sensor:
- In order to reduce backslash,  existing mechanical paddle design utilize ball bearings. It is an overkill as angular (rotational) movement is almost non-existent.
- Mechanical contacts prone to bouncing.
- Minimal contact distance (0.1 mm) and minimal force (10 grams) difficult to maintain with mechanical paddles.
- Load sensor based paddle is self calibrating, sensitivity is adjustable from command line interface separately for dot and dash.
- Sensor paddle is an order of magnitude cheaper than mechanical paddles.
- Better reliability compared to capacitive touch paddle, behaves like usual mechanical paddle.

#### Features:
- All [K3NG capabilities (k3ng wiki) ](https://github.com/k3ng/k3ng_cw_keyer/wiki) available.
- Equally suitable for beginners and experts.
- Affordable, off the shelf, load sensor and ADC components.  
  ( total approx. 10 USD for two ADC and two sensors ( ADC 2x1.3 USD, sensor 2 x 2~3 USD   ))
- Boards: "compatible"  Nano board  2 USD  
- Can be developed as add-on to existing K3NG kits.
- Configurable "single lever" mode: Tip from right paddle can be unscrewed and only left paddle is used as classic single paddle, as if it would have two sets of contacts for dot and dash.  (not to be confused with "single mode" where iambic mode is inhibited however both paddles are used) 

#### Prototype:
 
 [Arduino nano implementation](https://github.com/djbr1/k3ng_cw_keyer), allows parameter change through USB interface using [Android Serial Terminal app](https://play.google.com/store/apps/details?id=de.kai_morich.serial_usb_terminal) or  [Web Serial ](https://github.com/ok1cdj/K3NG-keyer-serial-terminal) (works from Chrome) . [CS1237 ADC](https://github.com/tremaru/iarduino_ADC_CS1237) is used as ADC.  
    [**Schematic diagram**](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/k3ng_keyer_nano_cs1237.sch_2024-09-17.pdf) (based on OK1CDJ nano keyer implementation)
   


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





