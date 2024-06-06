Enable vibration in your Joypad on Windows 10 (In Windows 7/8 it should sort of work by itself, but I haven't checked).
==========

These drivers and mini guide will work for devices such as:
-
![sddefault](https://github.com/Cinill/My-gamepad-drivers-collection/assets/72980216/5f2791f9-ca25-4f50-8af5-cab8cd117619) Bravis Pu-2200;
-

![original-95-1](https://github.com/Cinill/My-gamepad-drivers-collection/assets/72980216/ef60a557-1f4c-41f2-916c-ad2de7959ff1)
Bravis Pu-2222;
-

![81PxeRC2HPL _AC_UF350,350_QL80_](https://github.com/Cinill/My-gamepad-drivers-collection/assets/72980216/e5588ecf-fbcb-4687-9252-621667088e3f)
The blue PS2 to USB Convertor;
-

or all devices with VID_0810&PID_0001 and VID_11ff&PID_3341.
-



Troubleshooting
==
If your gamepad properties window crashes on the vibration tab then:
-
Copy the joy.cpl file from the C:Windows/SysWOW64 folder to the C:Windows/SysSystem32 folder with replacement.
Example:
https://www.youtube.com/watch?v=Un8nRb6pDBc

If your x360ce crashes:
-
Use version 3 because:
https://github.com/x360ce/x360ce/discussions/1324

If your xOutput crashes:
-
Use version up to v3.23 (I use v3.22)
https://github.com/csutorasa/XOutput/issues/216

If your PCSX2 crashes:
-
Unplug your Joypad, and turn off the SDL Input Source in the PCSX2 SDL settings, use xInput from  ‘XOutput’.


If you have a twitchy right stick (relevant on my Bravis pu-2222 when low on charge):
-
1.unplug your Gamepad

2.open regedit>HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\MediaProperties\PrivateProperties\Joystick\OEM\(your OEM gamepad)

3.Right click on your ‘gamepad OEM’- folder, create a new key called ‘Axes’

4.right click on the ‘Axes’ folder, create a key called ‘2’.

5.inside ‘2’ right click and create a binary value named ‘Attributes’, set it to ‘ 00 00 00 00 00 00 01 00 00 35 00 ’

6.after that create in ‘Axes’ a second key: ‘5’, create a binary value called ‘Attributes’, set it to ‘ 00 00 00 00 00 00 01 00 00 00 32 00 ’



It might help, but it didn't work for me.
https://forums.tomshardware.com/threads/right-analog-stick-problem.98492/post-9929592


P.S.: You can also reanimate your drivers by adding EZFRD64.dll (sometimes you need to add FCVAP64.dll) to the folder:
-
C:Windows/USB Vibration{PID of your device}

Do it at your own risk.
====
