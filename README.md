# standalone-utility
ZZSABIN Standalone utility for MVS

## Instructions and link 

http://www.cbttape.org/~jjaeger/

Use a standalone program ZZSA to fix your MVS system when the system is not available.
I Tested  on Hercules tk4 and Hyperion 4 versions. This example is from Windows 10 so paths may be different in your enviroment.  

Type the commands in a hercules console: 
Device 0c is the 3505 card reader.

 <b>herc ====></b> devinit 0c c:\hercules4.2\zzsa\zzsacard.bin ebcdic eof   
     also works for tk4 herc ====> devinit 0c c:\tk4\hercules\httproot\zzsacard.bin edcdic eof

 herc=====><b>archmode esa/390</b> 

 herc=====><b>ipl 0c</b>  

Then on 3270 console, press enter. (I'm using Vista TN3270) for x3270 trying pressing control-c for clear

Password:<b>ZZSECRET</b> 
 
After you press Enter the main screen will appear.

 ![](https://github.com/JSnetSystems/mvs/blob/master/images/ZZSA_Main_Screen.png)


1. Select 0 ListDev - List all devices to obtain the device number.

   On my machine 0A80 JASRES1 is where my SYS1.PROCLIB lives.

2. Select 3 ListVTOC to list VTOC info for the dataset, in this example SYS1.PROCLIB
   
   Enter device <b>0A80</b> to display dataset listing.

3. Select 4 to display PDS directory if you don’t know the PDS name or skip this and go to step 4

   Enter dataset===><b>SYS1.PROCLIB</b>
   Enter the four digit DASD device number ===><b>0A80</b>
   A listing of the members will be displayed.

4. Enter 2 to edit dataset. I'm using the JES2 member for my example.

   Enter dataset===><b>SYS1.PROCLIB</b>
   Enter member name===><b>JES2</b>
 and 4 digit DASD device number:<b>0A80</b>

   Edit your member as needed to correct the issue for JES2 startup <br>
   Exit to save your member and select X Exit to end program and try to IPL as normal.
