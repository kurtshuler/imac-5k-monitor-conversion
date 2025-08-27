# 27" iMac 2017 to 5K Display Conversion
This is how I converted a 100 EUR ($115) 2015 iMac 27 inch into a 5k monitor, and saved myself at least 1,000 EUR ($1,200). 

*Based off the work by the great community at https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/*

## 🙌 Community Heroes of the DIY 5K iMac Monitor Conversion

This project wouldn’t exist without the brilliant tinkerers over at the [MacRumors DIY 5K Monitor Success Thread](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/).  
Here are some of the contributors whose knowledge helped me the most. Thank you!

### 🏆 MVPs
- [**@PaulD-UK**](https://forums.macrumors.com/members/pauld-uk.374804/) — Too many great posts to count! Shared countless diagrams, wiring tips, and practical wisdom.
- [**@Regulus67**](https://forums.macrumors.com/members/regulus67.1356758/) - Always helpful answering questions. And very patient with newbies!
- [**@Aiwi**](https://forums.macrumors.com/members/aiwi.505077/) — Deep dives and detailed project logs. Helped demystify the R1811. Has a GitHub explanation of what he did at https://github.com/aiwipro/5K-iMac-Studio-Display-Stock-Look  
- [**@ItsAShaunParty**](https://forums.macrumors.com/members/itsashaunparty.823966/) — Created the useful [DIY 5K at Macrumors GPT](https://chatgpt.com/g/g-683af4dc61448191ad6868a38e8cb1b5-diy-5k-monitor-gpt) for ChatGPT.

💡 *Tip:* If you’re diving into this project, [browse the full thread at Macrumors before asking people questions!](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/)

---

## My goals

I recently bought a 3D printer and looked for a larger computer monitor for use with my 2020 Macbook Pro M1 and Adobe Fusion. There are lots of affordable 4K monitors but the scaling of text and details has always seemed off to me when using my Mac. I started looking for 5K monitors and was totally surprised to see...not much. And what is available is hugely expensive. While Googling 5K monitor reviews I found the [MacRumors DIY 5K Monitor Success Thread](https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/), and my life changed for the better.

I searched for used 27 inch iMacs on Wallapop, which is Spain's eBay. Imagine my surprise when I found a Late 2015 iMac 27 A1419 with a dead logic board being offered for 100 Euros. I contacted the seller and he said the screen worked fine before the logic board died and that he took it to a shop, but it was too expensive to repair. I took a gamble and paid the 100 Euros, betting that both the seller and the computer technician were honest. (Spoiler: They were! :astonished:)

When the board arrived I found it was a LM270QQ1 (SD)(B1). Of course, without a working logic board or a new display driver board I had no idea whether it worked.

### Requirements
Having purchased the iMac and determined the display model number, I needed to decide on on what driver board and other things to purchase. But before doing that I had to think about my requirements:
1. **NO AUDIO** - I didn't want to enable the iMac's built-in audio because people on the forum were having issues with it and I am in the process of designing a 3D printed 2.1 sound system.
2. **NO USB-C CHARGING** - I already have a CalDigit TS3 Plus dock and find it super-useful. The dock will charge the Mac for me. Of course, this means I need to connect 2 cable to my Mac to use: One to the dock for power and peripherals and the second to the iMac display for video only. One thing I learned later is that **I need to use a USB-C to DisplayPort cable for video** to ensure the iMac display's power brick doesn't try to charge my Mac. More on that later.
3. **SILENT** - One of the boards, the R1811, comes with a fan that people find noisy. So I kept the iMac's internal case fan to reuse that, and maybe also run the R1811's board fan with some resistors.
4. **IR REMOTE** - I hate reaching around displays to change settings and want an IR remote that I can point to the front of the display to access the driver board's OSD.

## Deciding on the Driver Board (R1811) and Vendor (Stonetaskin)

BLUF: I chose the [R1811 V4 (with DP1.4 + HDMI 2.1 support)](https://stonetaskin.com/products/diy-5k-universal-r1811-v-4-driver-board-usb-c-freesync-edp-dp1-4-compatible-for-imac-lm270qq1-lm270qq2-screen-external-monitor-1) and the companion [DZ-LP0818 50W Constant Current board](https://stonetaskin.com/products/high-quality-diy-universal-driver-board-50w-current-board-dz-lp0818-resolve-the-panel-brightness-problem-lm270qq1-lm270qq2-1?variant=45363844120730) from [stonetaskin.com](https://stonetaskin.com). 

Here's why I chose the R1811 even though it's the most expensive display driver board:
1. The R1811 gets more frequent firmware updates than the other boards.
2. Users in the Macrumors thread seemed to report fewer issues and quirks with the R1811 board.
3. It comes with an IR remote control and power supply.
4. I can connect an optional [DZ-LP0818 50W Constant Current board](https://stonetaskin.com/products/high-quality-diy-universal-driver-board-50w-current-board-dz-lp0818-resolve-the-panel-brightness-problem-lm270qq1-lm270qq2-1?variant=45363844120730) to increase the display's backlight brightness, if required. I purchased this board because I didn't know at the time how may hours the 2015 had been used, and therefore, if there was any dimunition in screen brightness. 

I decided to buy from Stontaskin because of their good reputation on the forum. My decision was confirmed when during the buying process I started an online chat with them and they were very quick and helpful. The two boards arrive at my home in Spain 8 days after ordering.

Here is what I ordered from Stonetaskin. Prices are all-in. Shipping was free:

| Photo | Item | Price|
|-------|------|------|
|  x |StoneTaskin Original DIY 5K Universal R1811 V.4 Driver Board USB-C Freesync EDP DP1.4 Compatible for iMac LM270QQ1 LM270QQ2 Screen External Monitor Fully Tested Free Shipping LM270QQ1 / Package B |$298.00|
| x  |High-quality DIY Universal Driver Board 50W Current Board DZ-LP0818 Resolve the Panel brightness problem LM270QQ1 LM270QQ2 LM270QQ1 | $36.30 |


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

💡 *Pro tip:* If you’re stuck, **search the forum thread by part number** (R1811, JRY, LM270QQ1, etc.) — it’s the fastest way to jump to relevant build notes.
