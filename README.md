hey, ill use this here space as a log for my build.

### intro
so after oogeling at [samZellof](https://www.youtube.com/watch?v=TrmqZ0hgAXk) and [jeriellsworth](https://www.youtube.com/watch?v=w_znRopGtbE) work on home semiconductor chip fabs i wanted some of that. currntly not intrested in micro work, i want to use some of the ideas in idiot.io work. mostly 10mil+ board designs

### progress
#### 3/4/2018
i had an LCoS type pico projector with me so i started toying with it, looking at possible line pitch and native resolution. 

also started collecting equipment.
 
 * 10x7.5cm FR4 pcb with photoresist coating
 * Sodium hydroxide - for developing 
 * etchant solution - i was feeilng lucky

waiting for night to come so i can do the lithography i read/tested a bit on the aaxa projector.

[aaxa pico HD spec pic](https://i.imgur.com/abyuRuq.png)

* focus - at 10x6cm was ok just the sizes we were dealing with
* pitch- line seperation issues, with vertical resolution, some lines where missing, or faded.  ([video](https://photos.app.goo.gl/Z30P2FHup9IhtfJ62)). its best seen with a grid pattern, but i didn't take suh photo it seems. really hard to capture this as the LCoS is strobing between the 3 LEDs and the angle of projection makes shadows. 
* contrast- spec is 1:2000, it looks really good. but cant say before a real exposure test
* UV output - it has none, there is a UV filter that needs to be removed, also dichroic mirrors on each LED, tuned to "visible spectrum". most research out there is regarding DLP type of projectors, they allow much more light (and single source at that), see [here](https://sites.google.com/site/passive3d/Downhome/Topic1/part1knowledgerepresentationinprolog20)

#### 4/4/2018
during a [teardown stream](https://photos.app.goo.gl/9uD4XJf9v1d5l4xY2) with [eladorbach](http://eladorbach.blogspot.com), Elad pointed me to TI "LightCrafter" evaluation boards for DLP pico projectors.  

* lightcrafter 2000 EVM- 100$  ([link](https://archive.is/dMBDm))
* beagleboard green/black - 60-90$ ([pic](https://i.imgur.com/sUgdQur.png))


just had a chat with @polyfractal, pointed me to sam zellof new post on his crazy instrumntation. he also uses the aaxa pico hd! [link](http://sam.zeloof.xyz/maskless-photolithography/)  with ebay uv leds.. yes 
<s>ill cancel that TI order...</s>

according to lightcrafter2000 [datasheet](http://www.ti.com/lit/ug/dlpu049c/dlpu049c.pdf) it uses following light sources

* LE BA Q6WM - blue, red LED
** Color: blue (460 nm); amber (617 nm) [osram](https://www.osram.com/os/ecat/OSRAM%20OSTAR%C2%AE%20Projection%20Compact%20LE%20BA%20Q6WM/com/en/class_pim_web_catalog_103489/global/prd_pim_device_2191190/), [digikey](https://www.digikey.com/product-detail/en/osram-opto-semiconductors-inc/LE-BA-Q6WM-1T3T-CE-HZJY-23-350-R18-ZC/LEBAQ6WM-1T3T-CE-HZJY-23-350-R18-ZC-ND/6709762)

spectrum  
[![](https://i.imgur.com/yN66bDym.png)](https://i.imgur.com/yN66bDyl.png)

package  
[![](https://i.imgur.com/9Fakw4cm.png)](https://i.imgur.com/9Fakw4cl.png)

* LCG H9RM - green LED
** Color: (515 nm) [osram](https://www.osram.com/os/ecat/OSRAM%20OSTAR%C2%AE%20Projection%20Cube%20LCG%20H9RM/com/en/class_pim_web_catalog_103489/global/prd_pim_device_2190826/),[digikey](https://www.digikey.com/product-detail/en/osram-opto-semiconductors-inc/LCG-H9RM-KZLZ-1/LCGH9RM-KZLZ-1-ND/4834206)

spectrum  
[![](https://i.imgur.com/74W3fH8m.png)](https://i.imgur.com/74W3fH8l.png)



#### whats next
giving up on full disassembly of the LCoS projector for now. 

ordered and digging for information on the lightcrafter2000 board espcially
on the LEDs they use. see if they have enough UV in them, and if not, what the LED package they use and how to replace it with a ~400nm one.


### pico Links

* [teardown of aaxaPicoHD optical assembly](https://polyfractal.com/post/light-engine-teardown-redux/) by @polyfractal  - came across this mid-work, lots of [info](https://polyfractal.com/categories/makerfoundry/) there on maskless photolit, trying to contact him see if he continued his efforts. but he has the same aaxa pico HD LCoS i used, which is not so hot for this.

* [How are pico-projectors built? How do I build one?](https://www.quora.com/How-are-pico-projectors-built-How-do-I-build-one) - exhaustive quora answer, composed in 2015 during the hay day of the google glasses.  

* [Projection displays: Intro and background](https://interaxn.quora.com/Projection-displays-Intro-and-background) - more for the same auther of that crazy qoura answer
* [Projection displays: Core technology](https://interaxn.quora.com/Projection-displays-Core-technology) - and more

### maskless links
* [A maskless photolithographic prototyping system using a low-cost
consumer projector and a microscope](http://pages.pomona.edu/~dmt04747/Pubs/MasklessLithoAJP.pdf) - 2004 paper on microscope maskless photolit 
* [Maskless Photolithography with DLP Projector - 10um Feature Sizes](https://www.youtube.com/watch?v=XVoldtNpIzI) - sam Zeloof intro and method of his MARK II DLP setup
* [Micro and Nanofabrication (MEMS) edX video course](https://www.edx.org/course/micro-nanofabrication-mems-epflx-memsx-0) - free course in a university grade fab lab

### rANDOM LNKS
[Measuring of the Temperature Profile during the Reflow Solder Process](https://dammedia.osram.info/media/resource/hires/osram-dam-2496666/Measuring%20of%20the%20Temperature%20Profile%20during%20the%20Reflow%20Solder%20Process.pdf)
