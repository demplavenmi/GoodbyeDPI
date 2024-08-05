
 
As Windows stop codes go, DRIVER\_POWER\_STATE\_FAILURE is fairly interesting. It indicates that a driver on your PC has fallen into an invalid or inconsistent power state. Thus, it usually occurs as PCs resume normal activity from some kind of Sleep or Hibernation state. Essentially, it crashes your PC and gives you a BSOD to avoid damage to the system or to data storage devices that might otherwise occur if the drivers and their associated devices were allowed to continue working.
 
If you view the crash dump file from this BSOD, which you can do by installing and launching BlueScreenView, it will often identify a file by name as part of the crash data. By searching on the name, you can often associate it with some specific device inside (or, as is most typical for this error) plugged into your PC.
 
**Download File ————— [https://verbbatomi.blogspot.com/?file=2A0SlS](https://verbbatomi.blogspot.com/?file=2A0SlS)**


 
In fact, the most common devices that provoke a DRIVER\_POWER\_STATE\_FAILURE error are USB drives (and other devices) of one kind or another: flash drives, drive docks, or external drive enclosures that may house SSDs, flash drives, or conventional hard disk drives.
 
If you continue to get DRIVER\_POWER\_STATE\_FAILURE errors, boot your PC into Safe Mode. When you get to the desktop, run Device Manager, and use it to uninstall any newly-added device drivers. Simply right-click any newly-added device, then select Uninstall device from the resulting pop-up menu.
 
The first of these commands uses the Windows Deployment Image Servicing and Management (DISM) command to check the components of the current running Windows image, and attempt repairs on any components that come up short during its integrity and checksum tests. In most cases, this will fix issues related to corrupt or damaged files in the Windows component store (by default C:\Windows\WinSxS).
 
Another Fresh install of Win 11 to be doubly sure of things and found that in the process of updating, rolling back and updating my BIOS a few times as part of troubleshooting that the default setting of auto installing ASUS Armory Crate had turned on sneaking in my fresh windows install.

After a couple of more wipes/installs to be sure I can now confirm that in my case it was **an incompatibility between drivers and tools: ASUS Armory Crate Versions 5.8.9.0, 5.8.9.5 installed with AMD Chipset Drivers 5.08.02.027 through to 6.03.19.217 and Adrenilane 24.3.1 or later are the root cause of Windows Blue Screen**
 
It would seem **ASUS Armory Crate 5.8.9.0/5.8.9.5 is not compatible with the latest AMD chipset and Adrenilane software** suite. I suspect either they are conflicting with trying to monitor or take control of a driver at the same time on boot and time the driver out.
 
Same, I am going crazy right now over issues with stuttering, losing 1000 points in Cinebench and stuttering in games from KB5035853 so I uninstalled that, was better but still existed. Went from 24.3.1 to 24.2.1 and fixed it.

did some testing and went back to 24.3.1, minor stuttering but still worse than before. Around the same time, the "fix" for KB5035853 came out and I uninstalled that. Still had bad performance.
Still only 17100 in R23 even after using Asus's x3d profile, which my other motherboard ASRock B650M Pro RS Wifi I was able to get 18400 points with PBO -20 undervolt.
 
(blue screens have been happening since fresh install with X670E-E board)

I've gone through multiple different versions of windows figuring out what is causing the bad performance in the first place, and what is causing the blue screens.
Sometimes I'm able to play a game (Team Fortress 2 with a friend for an hour) and it was fine, other times it's within minutes and it blue screens.
I can tell it's about to happen due to connecting a drive and it doesn't show up in file explorer, or I attempt to open up the windows settings menu and it does nothing, or I open up the sound panel and it does nothing.
 
This in combination on googling Keywords "Asus X670E Cold Boot BSOD Crash Stability Issues" I came across a post in the ASUS ROG Support Forums implying the Intel Ethernet Controller i225v driver may be conflicting: -forum.asus.com/t5/amd-600-series/x670e-e-cold-boot-stability-issues/td-p/896168
 
If this truly fixes it, it may seem that the latest Adrenalin Drivers (24.3.1) along side the Intel Ethernet driver coming from Asus/Armory Crate (2.1.3.3) are conflicting with each other for a power state driver delay on cold boot causing the Blue Screen.
 
Found a way to reproduce it a bit more consistently by logging in and letting the PC idle on desktop for 2 and a half mins or so without touching anything. Then the BSOD happens. This will make trouble shooting a little more easier to pinpoint.
 
So I think I found a fix.

I think it was caused by seriously outdated drivers. If I installed drivers manually without armory crate, it worked fine.

I'm on 10 IoT LTSC now with Armory Crate and after it installed it's drivers, I went to the asus website and downloaded the latest as well as using 24.3.1 adrenaline drivers.
 
Unfortunately I tried every possible thing software wise and ended up wiping with a clean install of Windows 11. Installed latest Chipset Drivers and Adrenalin Drivers and as soon as those were loaded, BSOD 0x9f
 
It crashed 7 times in a row trying to boot past the first 2mins of Windows usage yesterday. Once it's up it's fine and will last the whole day without a crash doing anything and everything thrown at it. Restart it manually once, and it's a roll of the dice, BSOD another 4 times until I could get it stable. So not hardware heat related as it happens hot or cold.
 
One thing I do notice, is that if HWInfo won't load when I try to open it after logging in, the BSOD crash is 100% pending on that specific reboot attempt within 90-120 seconds. HIInfo may be the cause? It's not running on startup but maybe a driver it puts in is conflicting? Uninstalled HWinfo to see if it'll make a difference.
 
please update on how it goes, ive been having the same problem for about a month. clean wiped my pc, at first i thought it was one of my hard drives or ssds being corrupted, but it seems like it is a driver issue, WhoCrashed says the same thing, either memory corruption or faulty drivers. although i dont think its HWInfo, since my pc crashes even after ive formated. i think its something from andrenaline.
 
Never in my 25 years of IT Engineering have I come across such an elusive unsolveable issue. Individually the parts test okay with memtests, cpu tests, furmark etc just this weird driver error on start up and the machine can run days without a BSOD doing production/gaming/general work once booted without a 0x9f BSOD.
 
Would using an Nvidia GPU get around this problem? Or due to the iGPU still being present the blue screens still happen?

I've gotten 2 driver power state again randomly the past week or two.

I'm trying to stay AMD but all these issues compared to Intel that I'm having it making me want to switch back.
 
Same driver state power failure using the latest AMD adrenalin software. Was on the driver from February 24.2.1, which worked without any issues, but upgrading to anything newer than this version results in exactly the same bugcheck error and random reboots, mostly when the PC is in an idle state. 

I've gamed on the machine for several hours with the latest drivers 24.5.1, and had zero issues, but left it idle overnight and came to find it rebooted overnight with the bugcheck x09F error. Will try this suggestion to fully remove Armoury Crate. Thank you!
 
My mobo is equipped with Intel AC9560 wi-fi/bluetooth adapter: it works pretty fine even if most of warning and error (non critical) in event viewer are related to it. Today i was trying to pair my phone (Samsung J3 2017) with my PC: it's been my first attempt after my clean WIN10 1809 install and android OREO update (in the previous phone-PC setting pairing gave me any issue):
 
windows found my device and showed connected but my phone wasn't paired (as i could see from the phone), no way to communicate between phone and PC. So i tried to reboot my phone and no success; tried to disconnect phone from PC settings and Windows settings panel freezed (but the PC worked) so i tried to reboot PC and after rebooting logo the system didn't restart and i had to force it by reset button. The system restarted and i found no error in event viewer i tried again to pair PC and phone: the same thing (win said connected but not the phone) but this time after few minutes i get BSOD "driver power state error" and stuck at 0% for several minutes. I had to force restart by reset button again: unfortunately windows didn't save dmp file so i can't debug BSOD. Since my driver were taken from intel site ( 20.110 for wifi and 21.10.1 latest for BT) and not from gigabyte manufacturer, i rolled back to latest available gigabyte driver for BT (20.100 from motherboard site) but didn't try to pair again my device: i don't really need it.
 
My question: BSOD (in my case the first) it's always a bad experience and you immediately think of some hardware problem.. So i'm little scared: do you think my BSOD could be related just to Bluetooth driver problem? Unfortunately i didn't get dmp file and looking around i didn't find any issue in similar build setting.
 a2f82b0cb4
 
