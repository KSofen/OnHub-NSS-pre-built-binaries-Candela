The NSS patches for OnHub compiled with source code from the OpenWrt 23.05.5 (kernel 5.15.189), and NSS patches by @Kong, @ACwifidude and @vochong --
Final CT (Candela Technologies) drivers support Fast Roaming, but can't reliably support MESH.  Last best firmware for OnHub routers.
This firmware pushes the OnHub to the maximum speed and throughput the hardware is capable of producing.  No more updates to follow.
OnHub routers are far past end of life.  OpenWrt release firmware still supports OnHub, but not NSS hardware.  Use at your own risk.

This firmware supports a lot of powerful OpenWrt features.  OpenVPN, WireGuard, AdGuard, Policy Based Routing, Switch, Dynamic DNS, Proto Relay, USB device mounting, Connecting printers to USB.

A clean install is required for this to operate properly.  If you retain settings and configurations, whatever is in your overlay will remain including packages not just settings.  You have to start over and build a system from scratch.  If you flash, then restore a backup, the same problem occurs - old packages from the overlay will be loaded, not the packages in the firmware.

Candela Technologies published a beta driver that their notes say address small issues in the release driver.  There is a separate firmware-2.bin file here which is that beta driver which is free for non-commercial use.  To tweak performance of OnHub with this driver, you have to navigate to the /lib/firmware/ath10k/qca988x/hw.2.0/ directory.  Retain only the board.bin file and delete other .bin files.  Copy the updated firmware-2.bin file to this directory.  There should now only be the two .bin files:  board.bin and firmware-2.bin - then reboot the router.

I've included a suggested rc.local file with startup commands to enable essential features of the CT drivers.
