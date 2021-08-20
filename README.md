# MSI-B360M-Mortar-Hackintosh-OpenCore-EFI
OpenCore EFI for MSI B360M Mortar

- OpenCore Version: [0.6.6](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.6.6)
- SMIBIOS: iMac 19,2 (**Retina 4K, 21.5-inch, 2019**)

![Image of Screenshot](https://raw.githubusercontent.com/tronic1983/MSI-B360M-Mortar-Hackintosh-OpenCore-EFI/main/images/Screenshot/Screenshot%202021-08-20%20at%2014.23.45.jpg)

This is my second time for building a Hackintosh PC. Though, I have experienced a few kernel panics. However, it has finally been succeed. The following was my journey.

**Important Note:**

- Do not use Asgard SSD or SAMSUNG PM981. Unless you really enjoy tons of kernel panics.
- Do not use Asgard SSD or SAMSUNG PM981. Unless you really enjoy tons of kernel panics.
- Do not use Asgard SSD or SAMSUNG PM981. Unless you really enjoy tons of kernel panics.

Very Very Very Important, so, I said this three times.

**Hardware:**

- CPU: Intel I5-8400 Coffee Lake
- GPU: MSI RX560 AERO ITX 4G OC Edition
- RAM: 16GB DDR4-2133 (Yes, I have had these old RAM for a long time. But it is OK with Hackintosh.)
- Motherboard: MSI B360M Mortar
- Audio Codec: Realtek ALC892 (alcid = 3)
- Ethernet Card: Intel V219
- Wifi/BT Card: Fenvi T919
- BIOS revision: V16

**BIOS Settings:**

1. Save & Exit → Restore Defaults : Yes
1. Settings \ Advanced \ Integrated Peripherals → Network Stack : [Disabled]
1. Settings \ Advanced \ Integrated Graphics Configuration → DVMT Pre-Allocated : 64MB
1. Settings \ Advanced \ USB Configuration → XHCI Hand-off : [Enabled]
1. Settings \ Advanced \ USB Configuration → Legacy USB Support : [Auto]
1. Settings \ Advanced \ Windows OS Configuration → MSI Fast Boot : [Disabled]
1. Settings \ Advanced \ Windows OS Configuration → Fast Boot : [Disabled]
1. Overclocking \ CPU Features → Intel Virtualization Tech : [Enabled]
1. Overclocking \ CPU Features → Intel VT-D Tech : [Disabled]
1. Settings \ Boot → Boot mode select : [UEFI]

**About config.plist**

- PciRoot(0x0)/Pci(0x2,0x0) -> AAPL,ig-platform-id -> 0300913E
- boot-args -> -v debug=0x100 keepsyms=1 alcid=3 shikigva=80 igfxfw=2 vsmcgen=1
- UEFI -> Quirks -> ReleaseUsbOwnership: YES ( For "AppleNVMe assert failed" issue )

**What works**
- [x] Onboard Sound (alcid = 3)
- [x] Microphone
- [x] Intel Ethernet
- [x] USB-C Port
- [x] USB3 Speeds
- [x] AMD Graphics Card
- [x] Airdrop / Handoff / Sidecar
- [x] Sleep / Wake (See Special Note)
- [x] App Store, iBooks, iMessage and iCloud
- [x] Hardware Accelerate

![Image](https://raw.githubusercontent.com/tronic1983/MSI-B360M-Mortar-Hackintosh-OpenCore-EFI/main/images/Screenshot/Screenshot%202021-08-20%20at%2013.52.01.png)

**Special Note**

In order to successfully sleep and wake, users must do the following:

- Remap USB Ports using Hackintool
- Fix the hibernate mode using Hackintool

![Image](https://raw.githubusercontent.com/tronic1983/MSI-B360M-Mortar-Hackintosh-OpenCore-EFI/main/images/Screenshot/czce599qqbi71.png)

- Turn off "Allow Bluetooth devices to wake this computer", "Wake for network access" and "Power Nap".

![Image](https://raw.githubusercontent.com/tronic1983/MSI-B360M-Mortar-Hackintosh-OpenCore-EFI/main/images/Screenshot/7hs5qojdtbi71.png)
![Image](https://raw.githubusercontent.com/tronic1983/MSI-B360M-Mortar-Hackintosh-OpenCore-EFI/main/images/Screenshot/bqzuhgnftbi71.png)

That's it. I hope this EFI would be helpful for those users who would like to build their own hackintosh PCs.
