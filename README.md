# Thinkpad-X13-Hackintosh-Improved
OpenCore EFI Folder of Thinkpad-X13(i5-10210U)

Forked from `mifjpn/Thinkpad-X13-Hackintosh`, with some QoL improvements

TB was not used.But USBPort.kext is made up to use.

## Spec.
CPU:Core i5-10310U 4core/8thread 1.7GHz-4.4GHz

GPU:Intel UHD Graphics

Display:13.3" FHD (1920x1080)

RAM:16GB/DDR4-266/soldered memory

Storage:NVMe2280,256GB

WiFi,Bluetooth: Intel Wi-Fi 6 AX201, 2.4Ghz-5GHz 600Mbps-9.6Gbps+Bluetooth 5.1

LAN: I219-V 1x RJ-45 via optional ThinkPad Ethernet via optional ThinkPad Ethernet Extension Adapter

## OpenCore

SM-BIOS: MacBookPro 2020(16,3)

OS: Monterey 12.7.4

## Installation Guide

1. Before starting, please make sure to disable the secure boot option in your UEFI bios, otherwise it will refuse to boot from USB.

1. Please follow the["Making the installer in macOS"](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/mac-install.html#downloading-macos-modern-os) guide precisely. The other methods (making installers on windows and linux) doesn't work for me.

1. After OS installation is done, you need to open the EFI partition and copy everything over. Please refer to the ["OpenCore Post-Install"](https://dortania.github.io/OpenCore-Post-Install/) steps.

1. Use [one-key-hidpi](https://github.com/xzhih/one-key-hidpi) option 2 to fix the DPI, otherwise the scaling will be too small.

1. Swap the Windows (Command) and Alt key (Option) in the keyboard settings. 

## QoL Improvements

* Trackpad delay is fixed by modifying `EFI/OC/Kexts/VoodooPS2Controller.kext/Contents/PlugIns/VoodooPS2Trackpad.kext/Contents/Info.plist`. Now typing on the keyboard doesn't disable the Trackpad for too long.
* `intwl.kext` Doesn't work on my machine + OS version, so I replaced it with `AirportItlwm.kext`
* An ICC profile is provided. The X13 display covers 100% sRGB but it's much smaller than the DCI-P3 standard Apple products come with, so color recreation is not as good.

## What Doesn't Work

* The AX201 WiFi card does not show all the hotspots, and the WiFi selection drop-down menu is very slow.