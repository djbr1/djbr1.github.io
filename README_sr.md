<!-- # djbr1.github.io -->

## Elektronski taster sa integrisanim ručicama 
### studija izvodljivosti
#### (Autor [Branko Djokic HB9TXB](https://www.qrz.com/db/hb9txb))     
   [![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/brankodjokic/) [![Facebook](https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white)](https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fblog.djokic.sh%2F&amp;src=sdkprepars)  [![A](https://img.shields.io/badge/X-%23000000.svg?style=for-the-badge&logo=x&label=share%20on%20twitter&logoColor=white&logoSize=auto)](https://twitter.com/intent/tweet?url=https://blog.hb9txb.ch/&text=Electronic%20Keyer%20with%20Integrated%20Load%20Sensor%20Paddles&hashtags=keyer,iambic,paddle,morse,cwkeyer,hb9txb,morsecode) [![gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:bdjokic76%40gmail.com) [![whatsapp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/41797532319)

<!--  [![View site - GH Pages](https://img.shields.io/badge/View_site-GH_Pages-2ea44f?style=for-the-badge)](https://djbr1.github.io/)  
| [![Twitter URL](https://img.shields.io/twitter/follow/djbr)](https://twitter.com/djbr)      

https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fblog.djokic.sh%2F&amp;src=sdkpreparse
-->

#### Motivacija
Nisam bio zadovoljan složenošću i visokom cenom mehaničkih ručica pa sam odlučio dizajnirati i napisati softver za ručice na bazi "senzora opterećenja" i objaviti kao **Open Source**.
Moja želja je da što veći broj amatera napravi taster sa integrisanom ručicom i vežba telegrafiju, nešto kao  [Taster TS-3](https://www.radista.info/morse_keys/morse_key_TS3.jpg) za 21.vek



#### Zašto se koristi senzor težine:
- Kako bi se smanjio otpor, postojeće mehaničke konstrukcije koriste kuglične ležajeve. To je preterano jer ugaono (rotacijsko) kretanje gotovo da i ne postoji.
- Minimalna kontaktna udaljenost (0,1 mm) i minimalna sila (10 grama) se teško postiže.
- Nasuprot tome, ručka senzora opterećenja se sama kalibriše, dok je osetljivost softverski podesiva pomoću serijskog interfejsa ili putem komandi.
- Senzor opterećenja je red veličine jeftiniji od mehaničkih ručica.
- Bolja pouzdanost u poređenju s kapacitivnim (touch) senzorom - kapacitivni senzor uvek morate pritisnuti na istom mestu što uzrokuje ukočenost šake i prstiju.
- Ručice senzora opterećenja mogu biti proizvoljnih oblika i dimenzija, za razliku od kapacitivnih koje postaju nepouzdane ukoliko su veće od 1-2 cm2.
- Da bi ste napraviti ručicu na bazi senzora, potrebno je samo par jeftinih elektronskih komponenti i najobičniji alat za obradu metalnih delova. Ne koriste se 3D štampači ili CNC mašine, "mehaniku" je moguće sklopiti od delova koje svakako imate u kućnoj radionici.

Prvi prototip sa senzorom je implementiran u jednostavnom Arduino KC4IFB tasteru ([izvorni projekat objavljen u QEX Sep/Oct.2009](http://www.arrl.org/files/file/QEX%20Binaries/09_September/9x09_Chapman.zip )).

Obzirom da je KC4IFB taster suviše skromnih mogućnosti, nastavljen je razvoj i napravljene su izmene (dodaci) u source kod-u za dva najpoznatija open-source tastera: **[K3NG (takmičarski orijentisan)](https://github.com/djbr1/k3ng_cw_keyer_LSP)**  i **[Morserino-32 (namenjen učenju telegrafije)](https://github.com/djbr1/Morserino-32_LSP)**.  

Detaljniji opis je na github stranici **[https://blog.hb9txb.ch](https://blog.hb9txb.ch/)** dok su softverske izmene vidljive u odgovarajućim github repozitorijima.

Ovaj prototip je daleko od završenog. Kompleti delova za K3NG taster su rasprodati (taster je dizajniran još 2012 godine) tako da će add-on za sensor opterećenja ostati u fazi prototipa. Morserino-32 ima velliki auditorijum (preko 10.000 prodatih kompleta delova), ali glavni modul Heltec ESP32 v2 se više ne proizvodi tako da je sudbina neizvesna. Poslednjih par nedelja stižu dobre vesti: softver je portiran na Platformio i funkcioniše na aktuelnom Heltec ESP32 v3 modulu tako da radim razvoj pločice gde će ADC za senzor biti integrisani.

Slobodno proverite opis i izvorni kod. Izvestite o problemima i/ili predložite izmene kroz komentar na dnu stranice ili još bolje kao "issue" u odgovarajućem repozitoriju.



======================================================

#### Morserino-32 pictures and videos (click for larger):
[![djbr1 - morserino32](https://img.shields.io/static/v1?label=djbr1&message=morserino-32&color=blue&logo=github)](https://github.com/djbr1/morserino-32 "Go to GitHub repo") [![stars - morserino-32](https://img.shields.io/github/stars/djbr1/morserino-32?style=social)](https://github.com/djbr1/morserino-32) [![forks - morserino-32](https://img.shields.io/github/forks/djbr1/morserino-32?style=social)](https://github.com/djbr1/morserino-32) | [![License](https://img.shields.io/badge/License-GPL-blue)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/LICENSE)




[![Morserino Image](https://raw.githubusercontent.com/djbr1/Morserino-32/master//Documentation/Hardware/IMG_1763_small.JPG?raw=true)](https://raw.githubusercontent.com/djbr1/Morserino-32/master//Documentation/Hardware/IMG_1763.JPG?raw=true)
[![Morserino Image](https://raw.githubusercontent.com/djbr1/Morserino-32/master//Documentation/Hardware/IMG_1812_small.JPG?raw=true)](https://raw.githubusercontent.com/djbr1/Morserino-32/master//Documentation/Hardware/IMG_1812.JPG?raw=true)
[![Morserino Image](https://raw.githubusercontent.com/djbr1/Morserino-32/master//Documentation/Hardware/IMG_1752_small.jpg?raw=true)](https://raw.githubusercontent.com/djbr1/Morserino-32/master//Documentation/Hardware/IMG_1752.JPG?raw=true)



[My fork of Christof Dallermassl OE6CHD Morserino CW trainer](https://github.com/djbr1/morserino32-trainer) provides [HTML](https://github.com/djbr1/morserino32-trainer/blob/main/sensor.html) for parameter change (adjusting paddle sensitivity)

[![web serial console screenshot](https://github.com/djbr1/Morserino-32/blob/master/Documentation/Hardware/sensor.html_small.jpg?raw=true)](https://github.com/djbr1/Morserino-32/blob/master/Documentation/Hardware/sensor.html.jpg?raw=true)

<br>
<!-- TODO:  single lever functionality ie using just one load sensor - preferred by HST competitors.  -->
Youtube shorts demo:
[![morserino32 shorts youtube](https://img.youtube.com/vi/P5Paj6hcao0/0.jpg)](https://www.youtube.com/watch?v=P5Paj6hcao0)







#### K3NG keyer Pictures and videos (click for larger):
 [![djbr1 - k3ng_cw_keyer](https://img.shields.io/static/v1?label=djbr1&message=k3ng_cw_keyer&color=blue&logo=github)](https://github.com/djbr1/k3ng_cw_keyer "Go to GitHub repo") [![stars - k3ng_cw_keyer](https://img.shields.io/github/stars/djbr1/k3ng_cw_keyer?style=social)](https://github.com/djbr1/k3ng_cw_keyer) [![forks - k3ng_cw_keyer](https://img.shields.io/github/forks/djbr1/k3ng_cw_keyer?style=social)](https://github.com/djbr1/k3ng_cw_keyer) | [![License](https://img.shields.io/badge/License-GPL-blue)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/LICENSE)<br>

<!--[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/IMG_1637.JPG?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1637.JPG?raw=true)  -->
[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/IMG_1637-EDIT.jpg?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1637.JPG?raw=true) 
[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/k3ng_keyer_nano_cs1237.sch_2024-09-17.png?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/k3ng_keyer_nano_cs1237.sch_2024-09-17.png?raw=true)
[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/nano_cs1237_keyer_k3ng_bb.png?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/nano_cs1237_keyer_k3ng_bb.png?raw=true)
[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/IMG_1737-EDIT.jpg?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1737-EDIT.jpg?raw=true) 
[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/Screenshot_2024-09-17_at_18.34.58.jpg?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/Screenshot_2024-09-17_at_18.34.58.jpg?raw=true)
[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/IMG_1344.JPG?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1344.JPG?raw=true)

 <!--   ![](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1330.JPG?raw=true)  -->
 <!--   ![](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1329.JPG?raw=true)  -->
<!--    ![](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1344.JPG?raw=true)  -->




[Youtube video showing paddle sensitivity](https://www.youtube.com/watch?v=UNnNl10UAn8)

[![Sensitivity demo](https://img.youtube.com/vi/UNnNl10UAn8/0.jpg)](https://www.youtube.com/watch?v=UNnNl10UAn8)

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

=====================================================================================
#### Arduino and ESP32 prototypes and sensors
[![image](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/resized/IMG_1824_small.jpg?raw=true)](https://github.com/djbr1/k3ng_cw_keyer/blob/master/k3ng_keyer/ADC_CS1237/IMG_1824.JPG?raw=true)

[Exhibited at Surplusparty Zofingen Switzerland](https://www.facebook.com/photo/?fbid=8925310450834424&set=a.161506880548202)
<iframe src="https://www.facebook.com/plugins/post.php?href=https%3A%2F%2Fwww.facebook.com%2Fbranko.djokic.3%2Fposts%2Fpfbid025Q9LoAPCpsiQWPDDYp6zj8ZT96pvEUVKRWWTM4j9gr5fbb1omou72AvDnHHzjWKjl&show_text=true&width=500" width="350" height="350" style="border:none;overflow:hidden" scrolling="no" frameborder="0" allowfullscreen="true" allow="autoplay; clipboard-write; encrypted-media; picture-in-picture; web-share"></iframe>

[Demo at HB9LU USKA Sektion Luzern - Meeting on 20.09.2024](https://hb9lu.ch/rueckblick-zum-hb9lu-stammabend-vom-20-09-2024/)

[![HB9LU USKA Sektion Luzern - Meeting on 20.09.2024](https://hb9lu.ch/wp-content/uploads/2024/09/HB9LU-2024-09-20-019-300x225.jpg)](https://hb9lu.ch/rueckblick-zum-hb9lu-stammabend-vom-20-09-2024/)

