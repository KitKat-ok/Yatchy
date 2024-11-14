<h1 align="center">
  Yatchy
</h1>
<p align="center">
  <b>Y</b>our W<b>atchy</b>, with all the flaws of the original fixed
</p>

<p float="left" align="middle">
  <img src="/img/Yatchy1.png" width="340,5" height="384"/>
</p>

Project under "construction", nothing is final yet, but most is probably

Yatchy features, compared to 2.0 watchy:

<sub>watchy v3 <a href="https://github.com/Szybet/WatchySourcingHub#original-watchy-v3">is a joke</a>, It's not even open source, it has many flaws so I don't even compare to it</sub>

#### Key points:
- USBC instead of micro usb
- Better buttons, they won't break easily
- Better battery life
- Hardware hackable
- Fixed many issues and improved minor things

## More detail
<details>
  <summary><h2>For regular users</h2></summary>

- Heavy increase in battery life, even with the screen updating every minute <sub>(The esp32c6 has a riscv lp core, which i connected to the screen, which means the device never really wakes up fully to only update the screen, not only that i fixed sqfmi flaws (Using 2 voltage dividers for example) I also use the external crystal clock for the RTC which means no RTC IC... and many more such things)</sub>
- Better buttons, more solid, shouldn't and probably won't break that much if at all. They are also less noisy.
- Solid USB-C port <sub>(It's THT soldered)</sub>
- no more usb compability problems <sub>(Because i use native esp32c6 jtag programming)</sub>
- better detection of charging <sub>(In software it was hacky on the original watchy, there were problems with it, never worked good)</sub>
- support for more wireless protocols, home automation ones, wifi 6 too
- ~~Mouse bites to more easily make your yatchy smaller, of the size of the screen and not the watchy form factor~~ <sub>JLCPCB decided to treat it as a seperate design and charge double, so I removed it. Stupid.</sub>
- TVS diodes, voltage spike protection - which means no more destroyed devices because watchy doesn't follow any USB spec and allows your device to burn down...
- Following all the specs of the various IC's - on the watchy it was just Yolo no capacitors here and there
- More precise time, based on some loose math and experiments, it should drift only a minute after a month, compared to the watchy its a lot better

</details>

<details>
  <summary><h2>For advanced users</h2></summary>

- A module area, with almost all exposed pins from the esp, power lines, and many gpio pins thanks to the expander IC - You can create your own, increase the capability of you yatchy without modifying everything inside - solar panel module, encoder instead of the button, sd card module, frontlight module, torchlight module, speaker module, microphone module, some environmental sensors. The only limitation is your imagination (And the size of the module)
- the low power core while using the high power core could be used to write portable apps for the yatchy <sub>(but we could achieve that with lua anyway I think)</sub>
- All the components are newer, still available and produced. Ordering a Yatchy PCB and the parts, soldering them themself is possible and easier than the watchy
- All QFN packages IC's on the board have increased pad sizes, so if you are skilled enough to solder QFN packages, here it will be easier
- I used traces teardrops, so more solid traces & pads
- JTAG debugging via usb, yay

</details>

<details>
  <summary><h2>Flaws</h2></summary>

- No battery connector, the module pads are small - so it's not for everyone, harder to use / assembly (solder!) for beginers
- It's watchy like but not watchy case compatible, the size and form factor is the same but the obvious obstacle is USBC, even with it the buttons are different and placed a little off to save some space
- It's a 4 layer PCB, so a bit more costly
- No easy hard reset option, you will need to short pins, but if you need to do it, then you made something really wrong. <sub>When developing the Yatchy, I only once needed a full reset</sub>
- A complicated license

</details>

## Software
It's fully supported by [InkWatchy](https://github.com/Szybet/InkWatchy). Maybe a rust firmware in the future? We will see...

## Hardware sources, buying, reselling, license
Everything explained [here](https://github.com/Szybet/Yatchy/tree/main/hardware)

# Community

<a href="https://discord.gg/6PUmRXZRGD">Join the *atchy community on discord</a>
