# 27" iMac 2017 to 5K Display Conversion
This is my documentation of how I converted a $115 / 100 Euro 2015 iMac 27 inch into a 5k monitor, and saved myself at least $1,000. 

Based off the work by the great community at https://forums.macrumors.com/threads/diy-5k-monitor-success.2253100/

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

## My goals and decisions

Here are the essentials if you want to turn a 2015 iMac into a standalone 5K monitor:

### 🔌 Driver Boards
- [R1811 V4 (with DP1.4 + HDMI 2.1 support)](https://stonetaskin.com/products/diy-5k-universal-r1811-v-4-driver-board-usb-c-freesync-edp-dp1-4-compatible-for-imac-lm270qq1-lm270qq2-screen-external-monitor-1) — popular board for LM270QQ1 / LM270QQ2 panels.  
- [JRY-W9RQUHD-SA1](https://www.aliexpress.com/item/1005006655038825.html) — another option for 5K builds.  
- [DX-LP0818 Booster](https://www.aliexpress.com/item/1005006529912490.html) — required if your board setup needs an extra voltage step-up.

### ⚡ Power Supplies
- [Meanwell LRS-250-24](https://www.meanwell-web.com/en-gb/ac-dc-enclosed-industrial-power-supply-output-lrs--250--24) — robust 24V supply, widely used.  
- [Meanwell XLG-200-24-A](https://www.meanwell-web.com/en-gb/ac-dc-led-driver-constant-power-xlg--200--24--a) — designed for LEDs, but many have used it successfully for monitors.  
- [Meanwell LRD-250-24](https://es.aliexpress.com/item/1005006614807022.html) — another common choice (quiet & compact).  

### 🖥️ Panels
- **LM270QQ1 / LM270QQ2** — the original iMac 27" 5K panels.  
- **LM270QQ3** — newer revisions, sometimes supported by R1811/JRY boards (check seller specs!).

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
