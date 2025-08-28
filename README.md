# 27" iMac 2015 to 5K Display Conversion (R1811 board)
This is how I converted a 100 EUR ($115) 2015 iMac 27 inch into a 5k monitor, and saved myself at least 1,000 EUR ($1,200). 

*Based off the work by the great community at https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/*

## 🙌 THANK YOU to the members of the DIY 5K iMac Monitor Conversion community!

This project wouldn’t exist without the brilliant tinkerers over at the [MacRumors DIY 5K Monitor Success Thread](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/).  
Here are some of the contributors whose knowledge helped me the most. Thank you!

- [**@PaulD-UK**](https://forums.macrumors.com/members/pauld-uk.374804/) — Too many great posts to count! Shared countless diagrams, wiring tips, and practical wisdom.
- [**@Regulus67**](https://forums.macrumors.com/members/regulus67.1356758/) - Always helpful answering questions. And very patient with newbies!
- [**@Aiwi**](https://forums.macrumors.com/members/aiwi.505077/) — Deep dives and detailed project logs. Helped demystify the R1811. Has a GitHub explanation of what he did at https://github.com/aiwipro/5K-iMac-Studio-Display-Stock-Look  
- [**@ItsAShaunParty**](https://forums.macrumors.com/members/itsashaunparty.823966/) — Created the useful [DIY 5K at Macrumors GPT](https://chatgpt.com/g/g-683af4dc61448191ad6868a38e8cb1b5-diy-5k-monitor-gpt) for ChatGPT.

💡 *Tip:* If you’re diving into this project, [browse the full thread at Macrumors before asking people questions!](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/)

---

## My goals

I recently bought a 3D printer and looked for a larger computer monitor for use with my 2020 Macbook Pro M1 and Adobe Fusion. There are lots of affordable 4K monitors but the scaling of text and details has always seemed off to me when using my Mac. I started looking for 5K monitors and was totally surprised to see...not much. And what is available is hugely expensive. While Googling 5K monitor reviews I found the [MacRumors DIY 5K Monitor Success Thread](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/), and my life changed for the better.

I searched for used 27 inch iMacs on Wallapop, which is Spain's eBay. Imagine my surprise when I found a Late 2015 iMac 27 A1419 with a dead logic board being offered for 100 Euros. I contacted the seller and he said the screen worked fine before the logic board died and that he took it to a shop, but it was too expensive to repair. I took a gamble and paid the 100 Euros, betting that both the seller and the computer technician were honest. (Spoiler: They were! :astonished:)

When the board arrived I found it was a LM270QQ1 (SD)(B1). Of course, without a working iMac logic board or a new display driver board I had no idea whether it worked.

### Requirements
Having purchased the iMac and determined the display model number, I needed to decide on on what driver board and other things to purchase. But before doing that I had to think about my requirements:
1. **NO AUDIO** - I didn't want to enable the iMac's built-in audio because people on the forum were having issues with it and I am in the process of designing a 3D printed 2.1 sound system.
2. **NO WEBCAM OR MIC** - I already have an Osbot Meet SE webcam that has better video than the iMac's internal camera. Also, the folks on the Macrumors forum seemed to have a lot of trouble creating a good internal mic solution. Seemed like little value add for lots of work to do this.
3. **NO USB-C CHARGING** - I already have a CalDigit TS3 Plus dock and find it super-useful. The dock will charge the Mac for me. Of course, this means I need to connect 2 cables to my Mac to use: One to the dock for power and peripherals and the second to the iMac display for video only. One thing I learned later is that **I need to use a USB-C to DisplayPort cable for video** to ensure the iMac display's power brick doesn't try to charge my Mac. More on that later.
4. **SILENT** - One of the boards, the R1811, comes with a fan that people find noisy. So I kept the iMac's internal case fan to reuse that and maybe also run the R1811's board fan with some resistors. I also prefer to use an external power brick for the monitor rather than have it heat up the inside more.
5. **IR REMOTE** - I hate reaching around displays to change settings and want an IR remote that I can point to the front of the display to access the driver board's OSD.

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

When pulling the parts, I noticed that both the logic board and power supply had damage that looked to be a result of arcing. Now I wasn't so sure the panel would work...

The "mystery Mac" before gutting. At this point I had no idea if the panel would work.
<IMAGE HERE>

The inside of the iMac case with only the fan and power button remaining. I have an iFixit toolkit and it was very helpful. You'll need T5, T8 and T10 drivers, plus an extension to remove a screw that is below the motherboard and accessible through a hole in it. There's info about this in the Macrumors forum thread.
<IMAGE HERE>

Here's the iMac fan with it's new wires, color-coded to correctly match the Noctua fan controller
<IMAGE HERE>

This is the power button with the extended wires.
<IMAGE HERE>

## Setting up the initial tests

My next step was to prepare the panel for a power-on test, using only the R1811 display driver board. I figured I would connect the DZ-LP0818 constant current backlight board after I knew the R1811 + panel worked. 

### Connect R1811 cables to panel display data socket and backlight cable
The display data cable is finicky to get in. I watched a couple of Youtube videos, which helped.

Here is the panel with both cables connected:
<IMAGE>

A closeup of the display data cable connection to the panel.
<IMAGE>

A closeup of the R1811 board backlight cable connected to the panel's backlight cable. The black circle side connects with the white side with the line and recesses on the left and right. There's more guidance in the forum thread if needed. If you connect it backwards, the backlight won't come on but apparently you won't fry anything.
<IMAGE>

### Connect the R1811 board to the panel
Here are before and after pictures of the R1811 and the panel.
<IMAGE>

<IMAGE>

A closeup of the R1811 board and cable connections. The backlight cable configuration will change later, once I add the DZ-LP0818 board to maintain/increase the panel backlight.
<IMAGE>

## Power up: The panel works!
Here is the R1811 board with the power on.
<IMAGE>

OSD! I flipped the panel and propped it up so I can see it. I used foam blocks underneath to protect it.
<IMAGE>

Here's how to change the OSD language from Chinese to English:
<IMAGE>

<IMAGE>

I connected my 2020 MacBook Pro M1 using a Thunderbolt 4 cable I had. The OSD and MacOS show that I am getting retina resolution!

### USB-C Power Delivery (PD) and screen flicker
At this stage I noticed the screen was flickering, which was initially disheartening. I eventually realized that my MacBook was drawing power through the USB-C to USB-C cable from the display driver's 24v 5 amp power supply. It was doing this even though I had my MacBook plugged into a separate power supply!

> [!IMPORTANT]
> If you connect your computer to the **R1811's USB-C port** and you are using an under-powered power supply (is that correct English?), it will try to power your computer and cause the display to **flicker**. The 24V 5A power supply from Stonetaskin is fine to power the monitor alone but cannot also power a computer. 
>
> a. You can use a **USB-C to DisplayPort cable** instead to get retina resolution without drawing power from the monitor's power supply, or
> b. You can get a **bigger power supply**, like one of the Mean Well's discussed in the forum

Since I didn't want power delivery from the monitor, I solved the problem by using a USB-C to DisplayPort cable. No more flickering!

## Adding the DZ-LP0818 50W Constant Current board
The purpose of this board is to provide and maintain additional and constant current to the panel backlight. As panel backlights age they become less bright, and this board is meant to address this issue. Since I had already purchased the board for my 2015 panel, not knowing whether I would have a bright (or working) panel, I decided to install it, too.

Here is a photo of the DZ-LP0818 connected between the R1811 and the panel's backlight cable.
<IMAGE>

A closeup of the DZ-LP0818 connected to the R1811.
<IMAGE>

Here is a closeup of the DZ-LP0818 cable connections.
<IMAGE>

And the R1811 cable connections. (I experimented with USB-C power to see if flickering occured with the constant current board installed. It does.)
<IMAGE>

### Creating a color profile using the Datacolor Spyder5
Using the Spyder5 was a pain in the butt because it is no longer supported and the software didn't work well on my Mac. I did create a profile that looked "better" than the iMacPro5K that my Mac originally assigned when I connected the panel. I will do more work on this in the future when I have the monitor internals completed.

## Next steps
Here are my plans for the near future:

### R1811 board fan power
Add resisitors to the R1811 board fan so it makes less noise. I have some Noctua ones laying around.

### iMac case fan power
I already extended the wires but I need to find a way to power it. Rather than connect to the 12V solder pads on the R1811 board, I chose to split the power coming out of the 24V power brick, add a 24V to 12V step down converter (probably with a fuse between it and the power brick, just in case), and a Noctua NA-FC1 fan controller.

### iMac case fan inlet shroud
I will use a 3D printed shroud to connect it.

   
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

