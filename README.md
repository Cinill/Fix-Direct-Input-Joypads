Enable vibration in your Joypad on Windows 10 (In Windows 7/8 it should sort of work by itself, but I haven't checked).

These drivers and mini guide will work for devices such as:
Bravis Pu-2200 and Pu-2222, as well as the blue adapter
or all devices with VID_0810&PID_0001 and VID_11ff&PID_3341.

troubleshooting

If your game controllers > properties window crashes on the vibration tab then:
Copy the joy.cpl file from the C:Windows/SysWOW64 folder to the C:Windows/SysSystem32 folder with replacement.
Example:
https://www.youtube.com/watch?v=Un8nRb6pDBc


If you are crashing x360ce:
Use version 3 because:
https://github.com/x360ce/x360ce/discussions/1324

If you are crashing xOutput:
Use version up to v3.23 (I use v3.22)
https://github.com/csutorasa/XOutput/issues/216

If you have a twitchy right stick (relevant on my Bravis pu-2222 when low on charge)

1.unplug your Gamepad
2.open regedit>HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Contro l\MediaProperties\PrivateProperties\Joystick\OEM\(your OEM gamepad)
3.Right click on your ‘gamepad OEM’- folder, create a new key called ‘Axes’
4.right click on the ‘Axes’ folder, create a key called ‘2’.
5.inside ‘2’ right click and create a binary value named ‘Attributes’, set it to ‘ 00 00 00 00 00 00 01 00 00 35 00 ’
6.after that create in ‘Axes’ a second key: ‘5’, create a binary value called ‘Attributes’, set it to ‘ 00 00 00 00 00 00 01 00 00 00 32 00 ’


It might help, but it didn't work for me.
