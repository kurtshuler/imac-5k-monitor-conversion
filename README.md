# 27" iMac 2015 (A1419) to 5K Display Conversion (R1811 board)
This is how I converted a 100 EUR ($115) 2015 iMac 27 inch into a 5k monitor, and saved myself at least 1,000 EUR :euro: ($1,200 💵). 

*Based off the work by the great community at https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/*


| *From this...* | *...to this!* |
|:--:|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/2015%20imac%2027.png" alt="iMac before" width="400"> | PICTURE HERE |

## 🙌 THANK YOU to the members of the DIY 5K iMac Monitor Conversion community!

This project wouldn’t exist without the brilliant tinkerers over at the [MacRumors DIY 5K Monitor Success Thread](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/).  
Here are some of the contributors whose knowledge helped me the most. Thank you!

- [**@PaulD-UK**](https://forums.macrumors.com/members/pauld-uk.374804/) — Too many great posts to count! Shared countless diagrams, wiring tips, and practical wisdom.
- [**@Regulus67**](https://forums.macrumors.com/members/regulus67.1356758/) - Always helpful answering questions. And very patient with newbies!
- [**@Aiwi**](https://forums.macrumors.com/members/aiwi.505077/) — Deep dives and detailed project logs. Helped demystify the R1811. Has a GitHub explanation of what he did at https://github.com/aiwipro/5K-iMac-Studio-Display-Stock-Look  
- [**@ItsAShaunParty**](https://forums.macrumors.com/members/itsashaunparty.823966/) — Created the useful [DIY 5K at Macrumors GPT](https://chatgpt.com/g/g-683af4dc61448191ad6868a38e8cb1b5-diy-5k-monitor-gpt) for ChatGPT.


> [!NOTE]
>💡 If you’re diving into this project, [browse the full thread at Macrumors before asking people questions!](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/)

---

## My approach to this writeup

Rather than simply show my successes and say "Tada!" like a magician pulling a rabbit out of a hat, :magic_wand: :rabbit2:, I am writing this as I am doing the project and will document my failures and false paths. If you see ~~strikethrough text~~, that means I made a mistake or chose a differrent path. Hopefully, this will be more helpful to others than a completely linear success story.

## My motivation

I recently bought a 3D printer and looked for a larger computer monitor for use with my 2020 Macbook Pro M1 and Adobe Fusion. There are lots of affordable 4K monitors but the scaling of text and details has always seemed off to me when using my Mac. I started looking for 5K monitors and was totally surprised to see...not much. And what is available is hugely expensive. While Googling 5K monitor reviews I found the [MacRumors DIY 5K Monitor Success Thread](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/), and my life changed for the better.

I searched for used 27 inch iMacs on Wallapop, which is Spain's eBay. Imagine my surprise when I found a Late 2015 iMac 27 A1419 with a dead logic board being offered for 100 Euros. I contacted the seller and he said the screen worked fine before the logic board died and that he took it to a shop, but it was too expensive to repair. I took a gamble and paid the 100 Euros, betting that both the seller and the computer technician were honest. :crossed_fingers:

When the package arrived I found it was a LM270QQ1 (SD)(B1). Of course, without a working iMac logic board or a new display driver board I had no idea whether it worked.

I called my new possession the *"Mystery Mac"*.

| *The "Mystery Mac" panel model number.* | *The "Mystery Mac" before gutting. At this point I had no idea if the panel would work.* |
|:--:| :--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/panel-model-number.png" alt="iMac before" width="400"> | <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/2015%20imac%2027.png" alt="iMac before" width="400"> |

## My goals and requirements
Having purchased the iMac and determined the display model number, I needed to decide on on what driver board and other things to purchase. But before doing that I had to think about my requirements:
1. **NO AUDIO** - I didn't want to enable the iMac's built-in audio because people on the forum were having issues with it and I am in the process of designing a 3D printed 2.1 sound system.
2. **NO WEBCAM OR MIC** - I already have an Osbot Meet SE webcam that has better video than the iMac's internal camera. Also, the folks on the Macrumors forum seemed to have a lot of trouble creating a good internal mic solution. Seemed like little value add for lots of work to do this.
3. **NO USB-C CHARGING** - I already have a CalDigit TS3 Plus dock and find it super-useful. I want the dock to charge the Mac for me. The con of using the dock is that it can only pass 5K through it's USB-C / Thunderbolt ports, and I don't know if doing this will cause the display driver board to try to charge the Mac through it's USB-C PD feature. If that happens, I would connect the Mac to the monitor using a DisplayPort 1.4 cable separately from the dock.

   3.a. One thing I learned later is that in the *Mac --> Thunderbolt cable --> Monitor* direct connect configuration (without the CalDigit dock in the mix), the display driver board attempts to power Mac. But I think the supplied power supply is too weak to do this (see below). Therefore, **when connected directly, I need to use a USB-C to DisplayPort cable from the Mac to the display board.** This is confirmed only for the *Mac --> Thunderbolt cable --> Monitor* direct connect configuration.

   3.b. I will need to experiment with the *Mac --> CalDigit dock --> Thunderbolt cable --> Monitor* connection to see if that causes the monitor display board to try to power the Mac.
   
5. **SILENT**
   
   4.a. **I kept the iMac's internal case fan to reuse.** An advantage is that the case was designed to suck in air from the back using the iMac's centrifugal fan and push the air out the bottom. This will help with cooling all the boards in the case. The cons are that I'll need a 24V-to-12V step down converter to run it and it limits where I can mount the R1811 board for easy access to the display inputs. I already have a [Noctua NA-FC1](https://noctua.at/en/na-fc1) fan controller which I'll use to dial down the RPMs so it's silent.
   
   4.b. One of the boards, the R1811, comes with a fan that people find noisy, I will **run the board fans with a resistor.** I tested this with some [Noctua NA-RC7 “Low-Noise Adaptor” (LNA)](https://noctua.at/en/na-src7) I have from another project and it works. I have purchased some 180 Ohm 2A resistors from Aliexpress and will replace the Noctua LNA's when I receive them.

   4.c. I also prefer to use an **external power supply** for the monitor rather than have it heat up the inside more. The one from Stonetaskin is 24V 5A with a 5.5mm/2.5mm barrel plug. If I want to charge a computer through USB-C power delivery (PD), I'll need a supply with more amperage and power (more on this below). Right now, I don't want to power my computer using the monitor (see above).

6. **IR REMOTE** - I hate reaching around displays to change settings and want an IR remote that I can point to the front of the display to access the driver board's OSD.

## Deciding on the display driver board (R1811) and vendor (Stonetaskin)

BLUF: I chose the [R1811 V4 (with DP1.4 + HDMI 2.1 support)](https://stonetaskin.com/products/diy-5k-universal-r1811-v-4-driver-board-usb-c-freesync-edp-dp1-4-compatible-for-imac-lm270qq1-lm270qq2-screen-external-monitor-1) and the companion [DZ-LP0818 50W Constant Current board](https://stonetaskin.com/products/high-quality-diy-universal-driver-board-50w-current-board-dz-lp0818-resolve-the-panel-brightness-problem-lm270qq1-lm270qq2-1?variant=45363844120730) from [stonetaskin.com](https://stonetaskin.com). 

Here's why I chose the R1811 even though it's the most expensive display driver board:
1. The R1811 gets more frequent firmware updates than the other boards.
2. Users in the Macrumors thread seemed to report fewer issues and quirks with the R1811 board.
3. It comes with an IR remote control and power supply.
4. I can connect an optional [DZ-LP0818 50W Constant Current board](https://stonetaskin.com/products/high-quality-diy-universal-driver-board-50w-current-board-dz-lp0818-resolve-the-panel-brightness-problem-lm270qq1-lm270qq2-1?variant=45363844120730) to increase the display's backlight brightness, if required. I purchased this board because I didn't know at the time how may hours the 2015 had been used, and therefore, if there was any dimunition in screen brightness. 

I decided to buy from Stonetaskin because of their good reputation on the forum. My decision was confirmed when during the buying process I started an online chat with them and they were very quick and helpful. The two boards arrived at my home in Spain 8 days after ordering.

Here is what I ordered from Stonetaskin. Prices are all-in. Shipping to Spain from China was free:

| Photo | Item | Price|
|-------|------|------|
| <img src="https://stonetaskin.com/cdn/shop/files/e8dafa727eb64e91d8ffac471a1f511d.jpg" alt="StoneTaskin Original DIY 5K Universal R1811 V.4 Driver Board USB-C Freesync EDP DP1.4 Compatible for iMac LM270QQ1 LM270QQ2 Screen External Monitor Fully Tested Free Shipping LM270QQ1 / Package B" width="300"> |StoneTaskin Original DIY 5K Universal R1811 V.4 Driver Board USB-C Freesync EDP DP1.4 Compatible for iMac LM270QQ1 LM270QQ2 Screen External Monitor Fully Tested Free Shipping LM270QQ1 / Package B |$298.00|
| <img src="https://stonetaskin.com/cdn/shop/files/High-quality-DIY-Universal-Driver-Board-50W-Current-Board-DZ-LP0818-Resolve-the-Panel-brightness-problem.webp?" alt="High-quality DIY Universal Driver Board 50W Current Board DZ-LP0818 Resolve the Panel brightness problem LM270QQ1 LM270QQ2 LM270QQ1" width="300">  |High-quality DIY Universal Driver Board 50W Current Board DZ-LP0818 Resolve the Panel brightness problem LM270QQ1 LM270QQ2 LM270QQ1 | $36.30 |

## Gutting the iMac case
My next step was to prepare the iMac case. I pulled out nearly everything because I am not reusing the iMac's speakers. The case didn't come with a RAM cover, so I'll have to 3D print something later. I removed the AC power socket because I plan on keeping the power supply brick outside the case.
1. **I kept the iMac case fan** and soldered longer wires onto the leads to later use with a [Noctua NA-FC1](https://noctua.at/en/na-fc1) fan controller I had laying around.
2. **I left the power button** and extended its wires so I can later attach them to the R1811 control strip's on/off button.

Instructions for how to gut the iMac are at https://www.ifixit.com/Guide/iMac+Intel+27-Inch+Retina+5K+Display+Logic+Board+Replacement/30529 

I have an iFixit toolkit and it was very helpful. You'll need **T5, T8, T10 and T25 screwdrivers**, plus an **extension** to remove a T8 screw that is below the motherboard and accessible through a hole in it (for the A1419, the screw is a T8, not a T10 as stated in the iFixit teardown). There's info about this in the Macrumors forum thread.

| *The "Mystery Mac" with speakers and power supply removed. The pesky T8 screw location is circled.* | *Closeup of the recessed T8 logic board screw.* |
|:--:|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/board-speakers-ps.png" alt="iMac before" width="400"> | <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/logic-board-screw.png" alt="iMac before" width="400"> |

When pulling the parts, I noticed that both the logic board and power supply had damage that looked to be a result of arcing. Now I wasn't so sure the panel would work...

| *The inside of the iMac case with only the fan and power button remaining.* |
|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/imac-case-empty.png" alt="imac case empty" width="400"> |


| *This is the power button with the extended wires.* | *iMac fan with it's new wires, color-coded to correctly match the Noctua fan controller.* |
|:--:|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/power-cable-extended.png" alt="power cable extended" width="400"> | <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/imac-fan.png" alt="imac fan wires" width="400"> |

## Setting up the initial tests

My next step was to prepare the panel for a power-on test, using only the R1811 display driver board. I figured I would connect the DZ-LP0818 constant current backlight board after I knew the R1811 + panel worked. 

### Connect R1811 cables to panel display data socket and backlight cable
The display data cable is finicky to get in. I watched a couple of Youtube videos, which helped.

Here is the panel with both cables connected:

| *Left: Backlight cable. Right: Data cable.* |
|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/panel-cables.png" alt="display panel cables" width="600"> |

Closeups of the display data cable connection to the panel.

| *Display data cable* | *Display data connector closeup* |
|:--:|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/display-data-cable.png" alt="display data cable" width="400"> | <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/display-data-cable-closeup.png" alt="display data cable closeup" width="400"> |

A closeup of the R1811 board backlight cable connected to the panel's backlight cable is below. 

| *Backlight cable connection closeup* |
|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/backlight-cable.png" alt="backlight cable closeup" width="600"> |

> [!IMPORTANT]
>
>The black circle side connects with the white side with the line and recesses on the left and right. There's more guidance in the forum thread if needed. If you connect it backwards, the backlight won't come on but apparently you won't fry anything.

### Connect the R1811 board to the panel
Here is the R1811 connected to the panel.

| *R1811 backlight and data cable connections* |
|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/panel-R1811-power-on.png" alt="R1811 cable connections to panel" width="600"> |

A closeup of the R1811 board and cable connections. The backlight cable configuration will change later, once I add the DZ-LP0818 board to maintain/increase the panel backlight.

| *R1811 cable connections closeup* |
|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/R1811-connections.png" alt="R1811 cable connections closeup" width="600"> |

## Power up: The panel works!

OSD! I flipped the panel and propped it up so I can see it. I used foam blocks underneath to protect it.

| *R1811 startup OSD* |
|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/panel-osd.png" alt="R1811 OSD" width="600"> |



### Change OSD to English
Here's how to change the OSD language from Chinese to English:

| *OSD Chinese language* | *OSD English language* |
|:--:|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/osd-chinese.png" alt="osd chinese" width="400"> | <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/osd-english.png" alt="osd english" width="400"> |

### Verify Mac 5K resolution

I connected my 2020 MacBook Pro M1 using a Thunderbolt 4 cable I had. The OSD and MacOS show that I am getting 5K resolution!

| *5K resolution* | *USB Type C input* |
|:--:|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/mac-retina-resolution.png" alt="iMac monitor conversion 5K" width="400"> | <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/mac-usb-c.png" alt="osd english" width="400"> |



This is how the panel looks at 50% brightness:

| *Panel at 50% brightness* |
|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/mac-brightness.png" alt="Panel at 50% brightness*" width="600"> |




### USB-C Power Delivery (PD) and screen flicker
At this stage I noticed the screen was flickering, which was initially disheartening. I eventually realized that my MacBook was drawing power through the USB-C to USB-C cable from the display driver's 24v 5 amp power supply. It was doing this even though I had my MacBook plugged into a separate power supply!

> [!CAUTION]
> If you connect your computer to the **R1811's USB-C port** and you are using an under-powered power supply (is that correct English?), it will try to power your computer and cause the display to **flicker**. The 24V 5A power supply from Stonetaskin is fine to power the panel alone but cannot also power a computer. 
>
> a. You can use a **USB-C to DisplayPort cable** instead to get retina resolution without drawing power from the monitor's power supply,
>
> or
> 
> b. You can get a **bigger power supply**, like one of the Mean Well's discussed in the forum

Since I didn't want power delivery from the monitor, I solved the problem by using a USB-C to DisplayPort cable. No more flickering!

## Adding the DZ-LP0818 50W Constant Current board
The purpose of this board is to provide and maintain additional and constant current to the panel backlight. As panel backlights age they become less bright, and this board is meant to address this issue. Since I had already purchased the board for my 2015 panel, not knowing whether I would have a bright (or working) panel, I decided to install it, too.

Here are photos of the DZ-LP0818 connected between the R1811 and the panel's backlight cable.

| *R1811 and DZ-LP0818 connections* |*R1811 and DZ-LP0818 connections closeup* |
|:--:|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/R1811-DZ-LP0818-connections.png" alt="R1811 and DZ-LP0818 connections" width="600"> | <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/R1811-DZ-LP0818-connections-closeup.png" alt="R1811 and DZ-LP0818 connections closeup" width="600"> |



> [!IMPORTANT]
>
> I experimented with USB-C power to see if flickering occured with the constant current board installed. It does.

### Creating a color profile using the Datacolor Spyder5
Using the Spyder5 was a pain in the butt because it is no longer supported and the software didn't work well on my Mac. I did create a profile that looked "better" than the iMacPro5K that my Mac originally assigned when I connected the panel. I will do more work on this in the future when I have the monitor internals completed.

## Reduce R1811 board fan noise
To reduce the fan noise, I needed to add some resistors to reduce the voltage to it. I happened to have two [Noctua NA-RC7 “Low-Noise Adaptor” (LNA)](https://noctua.at/en/na-src7) laying around so I connected them in series with the fan using JST XH-2P conenctors. The JST connector kit I used is [this one](https://www.amazon.es/dp/B0CKSJPVZF). I need to use JST's for another project so this was an opportunity for me to practice. I have fat fingers and bad eyes...

| *R1811 board fan with resistors* |
|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/board-fan-resistors.png" alt="R1811 board fan with resistors" width="600"> |

> [!NOTE]
>
> The yellow and red wires are positive and the the black wires are ground.
>

The fan is now nearly silent.

## Enable iMac case fan power
I already extended the wires from the iMac case fan but I needed to find a way to power it. Rather than connect to the 12V solder pads on the R1811 board, I chose to split the power coming out of the 24V power brick, add a 24V to 12V step down converter (with a fuse between it and the power brick, just in case), and a [Noctua NA-FC1 fan controller](https://noctua.at/en/na-fc1).

Here is a picture of how it all connects together. The step down converter output will go to the iMac case fan.

| *iMac monitor conversion power supply setup* |
|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/power-setup.png" alt="R1811 board fan with resistors" width="600"> |

### Stonetaskin power supply barrel size
One thing I didn't catch is that the R1811 board has a power barrel socket that requires a 5.5 mm outside diameter and 2.5mm inside diameter barrel plug. "Standard" size is 5.5 mm / 2.1 mm and this is the size [splitter](https://www.amazon.es/dp/B0DX6ZDM3J) I purchased from Amazon. The splitter worked with the Stonetaskin power brick but I needed an adapter to be able to plug it into the R1811 barrel socket. I had one in my junk drawer so it all worked out.

Here is a picture of the barrel connector sizes for the components in my design:

| *Barrel plug sizes for R1811 board, power supply, splitter and adaptor* |
|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/y-splitter-plus-adapter.png" alt="R1811 power supply and splitter barrel sizes" width="600"> |

### Setting output voltage on the step down converter

Here is the step down converter I used: https://www.amazon.es/dp/B09DYDV3S5

| *Step down converter inputs, outputs and controls* |
|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/step-down-converter.png" alt="step down voltage converter inputs, outputs, and controls" width="600"> |

When I set it to 12 volts using the converter's LED screen, I measure a slight bit more with my multimeter:

| *Display is close to multimeter* |
|:--:|
| <img src="https://github.com/kurtshuler/imac-5k-monitor-conversion/blob/main/images/set-step-down-converter.png" alt="set step down voltage to 12 volts" width="600"> |

### Putting all the electronics together

Here is a photo of all the power electronics connected together. 


## Next steps
Here are my plans for the near future:

### iMac case fan inlet shroud
I will use a 3D printed shroud to connect it. Forum member @Xarli did this https://www.thingiverse.com/thing:6775247. Another make is at https://www.thingiverse.com/thing:7100773.

### Create mounts for boards and step down converter
I will 3D print these. I haven't found ones online for the R1811 and DZ-LP0818 that will work for me, yet.

### Move IR receiver to where iMac FaceTime HD webcam was
I will desolder the R1811 control board's IR receiver and relocate it to where the webcam was located.

### Create new buttons for the OSD and put where USB ports were
This is a longer-term project to tap into the R1811 controller board with 6x6 mm tactile buttons and put them behind new button caps that fit the USB ports in the back. I'll also plug all the other ports. Will require some soldering and 3D printing. Forum member @jag001 did this: https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/page-33?post=32702935#post-32702935. I think this user might have .stl I can use https://www.thingiverse.com/thing:7044482/files.
   
### 📑 Key MacRumors Posts
- [@PaulD-UK on wiring & power (#1822)](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/page-109#post-32717747)  
- [@Aiwi on R1811 setup (#822)](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/page-35#post-31094713)  
- [@Kaeslin’s R9A18 project (#1409)](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/page-57#post-32247683)  
- [WikiPost summary (living index of builds)](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/page-1#post-30975623)  

### 🛠️ Extras
- [Noctua NA-FC1](https://noctua.at/en/na-fc1) — fan controller for iMac fan repurposing.  
- [Ugreen USB-C to DP 1.4 cable](https://www.ugreen.com/products/usb-c-to-displayport-8k-cable) — tested by many in the thread.  
- [Fusion 360](https://www.autodesk.com/products/fusion-360/) — handy for designing custom mounts or enclosures.  

---

