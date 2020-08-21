# standalone-utility
ZZSABIN Standalone utility for MVS

## Instructions and link 

http://www.cbttape.org/~jjaeger/

Use a standalone program ZZSA to fix your MVS system when the system is not available.
I Tested  on Hercules tk4 and Hyperion 4 versions. This example is from Windows 10 so paths may be different in your enviroment.  

Type the commands in a hercules console: 
Device 0c is the 3505 card reader.

 herc ====> devinit 0c c:\hercules4.2\zzsa\zzsacard.bin ebcdic eof   <enter>
     also works for tk4 c:\tk4\hercules\httproot\zzsacard.bin edcdic eof

 herc=====> archmode esa/390 <enter>

 herc=====>ipl 0c  <enter>

Then on 3270 console, press enter. (I'm using Vista TN3270) for x3270 trying pressing control-c for clear
Password is ZZSECRET <all caps>

<image here>

1. Select 0 ListDev - List all devices to obtain the device number.

On my machine 0A80 JASRES1 is where my SYS1.PROCLIB lives.

2. Select 3 ListVTOC to list VTOC info for the dataset, in this example SYS1.PROCLIB
Enter device 0A80 to display dataset listing.

3. Select 4 to display PDS directory, if you don’t know the PDS name or skip this and go to step 4.
Enter dataset===>SYS1.PROCLIB
Enter 4 digit DASD device number ===> 0A80
A listing of the members will be displayed.

4. Enter 2 to edit dataset
Enter dataset===>SYS1.PROCLIB
Enter member name===>JES2
and 4 digit DASD device number:  0A80

Edit you member as needed to correct the issue for JES2 startup
Exit to save your member and select X Exit to end program and try to IPL as normal.
