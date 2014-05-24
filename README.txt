Please follow this guide to the letter.  I do not assume any responsibility or liability for what may happen to your device by attempting to modify your PRL, nor do I provide PRL's.  As the user you assume all responsibility and risks associated with this.  I also assume no risks for the 3rd party software used during this procedure.  Note this is the PRL flash procedure just for the Nexus 5 device.

Preparation Steps:
1. Download the Android SDK and have your six digit MSL number handy.

2. Find the Platform-Tools folder located in the SDK Directory.
	ex: C:\Program Files (x86)\Android\android-studio\sdk\platform-tools
	
3. Be sure to have the Nexus 5 drivers installed and USB Debugging mode enabled. 

4. Download this boot.img from this link (http://forum.xda-developers.com/attachment.php?attachmentid=2422719&d=1385755948)
	Unzip the image and place it INSIDE the platform-tools folder.
	
5. Download and install QPST 2.7 build 402.  DO NOT install build 422!  It is a fake that comes with a nasty accessory (trojan worm).  You should be able to find it on XDA- http://forum.xda-developers.com/showthread.php?t=2263391

6. DO NOT close the command prompt until we are entirely finished with the flash.


Lets get started:
1. In the platform-tools folder, hold shift and right click, then select "Open Command Window Here".

2. Type in the command prompt: adb devices
	Note: You should now see a serial number appear.  This indicates that your devices drivers are installed and it is in USB debugging mode.  If you don't see your device's serial number, try reconnecting the device, using another USB cord, restarting the computer, reinstalling the drivers, checking to be sure USB Debugging is installed, etc.
	
3.  Type: adb reboot bootloader
	Note: This will reboot your devices into Fastboot mode
	
4.  Type: fastboot boot boot.img
	Note: You should see on the cmd line that this is downloading the boot.img.  Afterwards your phone will reboot normally.
	
5.  Type: adb devices
	Note: We are verifying that our phone is still communicating with adb.  See the trouble steps in step 2 if you have any issues.
	
6.	Type: adb shell

7.  Type: su
	Note: You will have to allow superuser permissions on your phone at this point.
	
8.  Type: setprop sys.usb.config diag,adb
	Note: You will not see any activity on the command prompt or phone after this step, but you should hear a should from your computer, if your volume is on, to signify that your computer is installing the diag drivers.

9.	Open QPST Configuration

10. You should see that there are a couple active ports in QPST.  Highlight the one that has some number under the phone tab and has USB for the link.

11. In the menu bar: Start Client > Service Programming

12. Select your phone with your phone number and hit okay.

13. Go to the Roam tab and select "Read from phone".  You will then have to enter your MSL number.

14. In the Roam tab, look in the Preferred Roaming section and browse for your .prl file.  Select it and then click "Write to Phone"

15. Don't freak out... You should have gotten an error stating that your phone returned a permanent error and you will now notices that your phone does not have a signal.  Close out of QPST- don't save any changes. 

16. Type: adb reboot

17.  When your phone reboots check in the Settings>About>Status page to be sure that your PRL took.  Enjoy!