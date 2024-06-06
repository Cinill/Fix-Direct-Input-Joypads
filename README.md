# Enable Vibration in Your Joypad on Windows 10

(In Windows 7/8 it should sort of work by itself, but I haven't checked).

## Supported Devices

These drivers and mini guide will work for devices such as:

- ![Bravis Pu-2200](https://github.com/Cinill/My-gamepad-drivers-collection/assets/72980216/5f2791f9-ca25-4f50-8af5-cab8cd117619) Bravis Pu-2200
- ![Bravis Pu-2222](https://github.com/Cinill/My-gamepad-drivers-collection/assets/72980216/ef60a557-1f4c-41f2-916c-ad2de7959ff1) Bravis Pu-2222
- ![PS2 to USB Convertor](https://github.com/Cinill/My-gamepad-drivers-collection/assets/72980216/e5588ecf-fbcb-4687-9252-621667088e3f) The blue PS2 to USB Convertor

Or all devices with VID_0810&PID_0001 and VID_11ff&PID_3341.

## Troubleshooting

### Gamepad Properties Window Crashes on the Vibration Tab

If your gamepad properties window crashes on the vibration tab:

1. Copy the `joy.cpl` file from the `C:\Windows\SysWOW64` folder to the `C:\Windows\System32` folder with replacement.

Example: [Watch the video](https://www.youtube.com/watch?v=Un8nRb6pDBc)

### x360ce Crashes

If your x360ce crashes:

- Use version 3. [More information](https://github.com/x360ce/x360ce/discussions/1324)

### xOutput Crashes

If your xOutput crashes:

- Use version up to v3.23 (I use v3.22). [More information](https://github.com/csutorasa/XOutput/issues/216)

### PCSX2 Crashes

If your PCSX2 crashes:

1. Unplug your Joypad.
2. Turn off the SDL Input Source in the PCSX2 SDL settings, use xInput from ‘XOutput’.

### Twitchy Right Stick (Relevant for Bravis Pu-2222 When Low on Charge)

1. Unplug your Gamepad.
2. Open `regedit` and navigate to `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\MediaProperties\PrivateProperties\Joystick\OEM\(your OEM gamepad)`.
3. Right-click on your ‘gamepad OEM’ folder, create a new key called ‘Axes’.
4. Right-click on the ‘Axes’ folder, create a key called ‘2’.
5. Inside ‘2’, right-click and create a binary value named ‘Attributes’, set it to ‘00 00 00 00 00 00 01 00 00 35 00’.
6. After that, create in ‘Axes’ a second key: ‘5’, create a binary value called ‘Attributes’, set it to ‘00 00 00 00 00 00 01 00 00 00 32 00’.

It might help, but it didn't work for me. [Discussion on Tom's Hardware](https://forums.tomshardware.com/threads/right-analog-stick-problem.98492/post-9929592)

## Additional Tips

You can also reanimate your drivers by adding `EZFRD64.dll` (sometimes you need to add `FCVAP64.dll`) to the folder:

`C:\Windows\USB Vibration{PID of your device}`

Do it at your own risk.

---

