<div align="center">

# 👨🏻‍💻 HP EliteDesk 800 G4/G5 Hackintosh

> Unlock the macOS Experience on Your HP EliteDesk

A hackintosh EFI configuration designed to bring the best of both worlds — the power and reliability of the HP EliteDesk hardware combined with the seamless user experience of macOS.

Optimized for **HP EliteDesk 800 G4 and G5 DM 35W/65W** models, and adaptable to various Series 800 G4, G5, and SFF models with **CoffeeLake (CFL)** and **CoffeeLake Refresh (CFLR)** processors.

📖 Detailed installation guide: [The Perfect MacMini Hackintosh](https://cmalf.github.io/blog/the-perfect-macmini-hackintosh)

</div>

---

## ⛩ Release History

| Release                                                                                                                          | Description                                          |
| -------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------- |
| [OC 1.0.0 EFI R001](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases/tag/Hackintosh)                          | Initial EFI release with OpenCore 1.0.0              |
| [RestrictEvents-1.1.4](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases/tag/RestrictEvents)                   | Experimental Sequoia Beta support                    |
| [OC 1.0.1 EFI R001](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases/tag/OC-1.0.1-EFI-R001)                   | EFI updated to OpenCore 1.0.1                        |
| [OC 1.0.2 EFI R001](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases/tag/OC1.0.2-EFI-R001)                    | EFI updated to OpenCore 1.0.2                        |
| [Sonoma 14.7.1 / Sequoia 15.1](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases/tag/Sonoma14.7.1-Sequoia15.1) | Sonoma 14.7.1 available; upgradeable to Sequoia 15.1 |
| [Sequoia 15.1.1](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases/tag/Sequoia-15.1.1)                         | Sequoia 15.1.1 update available                      |
| [OC 1.0.3 + GUI](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases/tag/OC1.0.3-EFI-GUI)                        | Updated to OC 1.0.3 with OpenCore GUI added          |
| [Sequoia 15.2 + OC 1.0.3](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases/tag/Sequoia-15.2)                  | Sequoia 15.2 available; bundled with OC 1.0.3        |
| [Sequoia 15.3.2 + OC 1.0.4](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases/tag/Sequoia-15.3.2-OC-1.0.4)     | Sequoia 15.3.2 available; updated to OC 1.0.4        |
| [Sequoia 15.5](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases/tag/Sequoia-15.5)                             | Sequoia 15.5 (24F74) update available                |
| [macOS Tahoe 26 & 26.0.1](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases/tag/Tahoe26)                       | Upgrade available — macOS Tahoe 26.0 (25A354)        |
| [macOS Tahoe 26.1 & 26.2](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases/tag/Tahoe26.1)                     | Tahoe 26.1 (25B78) & Tahoe 26.2 (25C56) available    |

---

## 📝 Update Notes

### My Hackmini with Sonoma 14.5

<img src="https://github.com/user-attachments/assets/f4d1887a-8560-4ac3-bd5c-07415e4f8afc" width=600 alt="General">

### Sonoma 14.6

- Smooth OTA update
- If you receive a failure notification, temporarily disable **SBM (Secure Boot Model)**
- After a successful update, you may re-enable SBM to `J174` or default

### Sonoma 14.6.1

- Smooth update
- `SBM = Disabled`

### Sonoma 14.7

- Upgrade applied without any issues — hack is working perfectly
- `SBM = Disabled`

### Sequoia 15.0 — Known Issues

- **Ethernet issue on Remote Desktop only:**
  - Deactivate and re-activate Ethernet in System Settings
  - Unplugging and re-plugging the RJ-45 connector also resolves it
  - No Ethernet issues observed in other applications
- Wi-Fi and Bluetooth: ✅ Working
- Staying on **Sonoma 14.7** is recommended if Remote Desktop Ethernet stability is required

---

## ❗ Notice

> Starting from this point, update notes will **no longer be maintained in this README**.
> All future updates will be posted in the [**Releases**](https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/releases) section.

---

<div align="left">

## © Credits

[thk]: https://img.shields.io/badge/Thanks%20to:-orange
[ghrp]: https://github.com/cmalf/HP-EliteDesk-800-G4-G5-Hackintosh/
[dvd]: https://img.shields.io/badge/deeveedee-white
[phm]: https://img.shields.io/badge/The%20Perfect%20MacMini8,1%20Hackintosh-blue
[pp]: https://img.shields.io/badge/Profile-cyan
[phmlk]: https://www.insanelymac.com/forum/topic/343937-guide-catalina-big-sur-monterey-ventura-sonoma-sequoia-on-hp-elitedesk-800-g4g5-mini-the-perfect-macmini81-hackintosh/
[dvdp]: https://www.insanelymac.com/uploads/monthly_2023_10/old-lady-small.thumb.jpg.a626f536e4dd345141fb85959e3d0ec0.jpg
[dvdlk]: https://www.insanelymac.com/forum/profile/1099364-deeveedee/

[![ghrp][thk]][ghrp]<br>
![dvdp]<br> [![dvdlk][dvd]][dvdlk] <br>

- Provided a guide for installing macOS on the HP EliteDesk 800 G4 / G5 Mini, <br> which is based on [![phmlk][phm]][phmlk] <br>
- See deeveedee's [![dvdlk][pp]][dvdlk] on insanelymac for details.

</div>
