# AMD Ryzen Hackintosh - Opencore EFI for Asrock B550 series


## Specification
| **Component** | **Model** |
| ------------- | --------- |
| CPU | AMD Ryzen 5 3600 @ 3.6GHz |
| Motherboard | Asrock B550 Series |
| RAM | 32GB (2 x 16GB) Corsair Vengeance RGB @ 3200 CL16 |
| Audio Chipset | ALCS-1200A |
| GPU | Gigabyte RX 580  |
| Ethernet | RTL8125 2.5GbE |
| Ethernet | RTL8111 1GbE |
| OS Disk (Nvme/Sata3) | Samsung 970 EVO+ 500GB | Samsung 860 EVO 250GB |

**macOS version**: Big Sur 11.2 (Can be use for Catalina 10.15.x also)  

**OpenCore version**: 0.6.2  

**SMBIOS**:  iMacPro7,1

## Drivers & Kexts
 - [[Bootloader] OpenCore](https://github.com/acidanthera/OpenCorePkg)
 - [[Patch] AMD_Vanilla](https://github.com/AMD-OSX/AMD_Vanilla)
 - [[Driver] FwRuntimeServices](https://github.com/acidanthera/OpenCorePkg)
 - [[Driver] HfsPlus](https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi)
 - [[Driver] OpenCanopyIcons](https://github.com/blackosx/OpenCanopyIcons)
 - [[Kext] Lilu](https://github.com/acidanthera/Lilu)
 - [[Kext] VirtualSMC](https://github.com/acidanthera/VirtualSMC)
 - [[Kext] WhateverGreen](https://github.com/acidanthera/WhateverGreen)
 - [[Kext] AppleALC](https://github.com/acidanthera/AppleALC)
 - [[Kext] AppleMCEReporterDisabler](https://github.com/AMD-OSX/AMD_Vanilla/blob/opencore/Extra/AppleMCEReporterDisabler.kext.zip)
 - [[Kext] LucyRTL8125Ethernet](https://github.com/Mieze/LucyRTL8125Ethernet)
 - [[Kext] AMDRyzenCPUPowerManagement](https://github.com/trulyspinach/SMCAMDProcessor)
 - [[Kext] SMCAMDProcessor](https://github.com/trulyspinach/SMCAMDProcessor)
 - [[Kext] USBPorts](https://dortania.github.io/OpenCore-Post-Install/usb/manual/manual.html#usb-mapping-the-manual-way)

## Working
- **Sleep/Wake**
- Ethernet 
	- Settings -> Network -> Ethernet -> Advenced -> Hardware: Set Configure from Automatically->Manually Then set Speed to 1000baseT, click ok and apply.

	- When firts install, you can set via terminal:

		`ifconfig en0 media 1000baseT`

## Not working
 - Mic > [See Details] (https://dortania.github.io/OpenCore-Post-Install/universal/audio.html#no-mic-on-amd) (Can be used USB Mics)
 - Hypervisor.framework (VirtualBox and XCode iOS emulator works)
 - Android Studio emulator (Can be replaced with Genymotion)

## How to use
  1. Create directory "EFI" in your EFI partition (e.g. pendrive or hard drive)
  2. Clone this repo and paste directiories "BOOT" and "OC" onto created directory
  3. Download [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) to generate unique SMBIOS information. Run it and select **Generate SMBIOS**, as model select **iMacPro7,1**.
  4. Open config.plist with [**ProperTree**](https://github.com/corpnewt/ProperTree) and go to PlatformInfo > Generic. Set MLB (Board Serial), SystemSerialNumber (Serial) and SystemUUID (SmUUID) to generated values.
  5. Boot it!  

## Disclaimer

This documentation is published for the sole purpose of learning and tech enthusiasm and with no guarantees of any kind, I’m not responsible of any harm of any kind or loss of data that may occur.
