Switch Frame Tap - Windows viewer
=================================

Watch and play your Switch on this PC over a USB-C cable.

ONE-TIME SETUP: the USB driver
------------------------------
Windows needs the generic WinUSB driver for the Switch before any program can
talk to it. Do this once:

  1. On the Switch: install Switch Frame Tap (the Switch zip from the same
     release), reboot, and connect the Switch (handheld) to this PC with the
     USB-C cable.
  2. Download Zadig: https://zadig.akeo.ie/  and run it.
  3. Options -> List All Devices.
  4. Pick "Switch Frame Tap" in the list (USB ID 1209 5F1E).
     Make sure it is that one - not your mouse, keyboard or anything else.
  5. Set the driver on the right to "WinUSB" and click "Install Driver"
     (or "Replace Driver"). Wait for it to finish.

Only Switch Frame Tap's USB ID gets the driver; nothing else on the PC
changes. Tip: the Switch only shows up in Zadig while the sysmodule is running
(a few seconds after the console boots).

USING IT
--------
Double-click SwitchFrameTap.exe. The window shows what it is waiting for and
the keys, and shows the game as soon as one is running. It reconnects by itself when the Switch
reboots or the cable is unplugged. F11 or a double-click: fullscreen. Esc
leaves fullscreen or closes the window. M mutes the game's sound.

NETWORK (play docked)
---------------------
Turn on "Network streaming" in the Switch Frame Tap manager app and restart
the Switch. With the Switch and this PC on the same network (Wi-Fi or the
dock's LAN port), SwitchFrameTap.exe finds the console by itself - no cable,
no driver. The first time, Windows Firewall asks whether to allow it on
private networks: allow it, or it cannot hear the Switch. A cable-free
stream needs a good network: the dock's LAN port, or strong 5 GHz Wi-Fi at
Medium quality.

RECORDING
---------
Press R to record, R again to stop. The recording starts at the next
keyframe (within a second) and is saved as an MP4 in your Videos folder,
under "Switch Frame Tap": the console's own H.264 picture, untouched, and the
game's sound. A red dot shows while it records. 1080p at High quality is about 10 MB a second
(~600 MB a minute); it stops by itself if the disk gets nearly full.

If the title bar says the Switch "has no USB driver", do the setup above.

Keep the DLLs next to SwitchFrameTap.exe.

More: https://github.com/TomasUribe/switch-frame-tap
