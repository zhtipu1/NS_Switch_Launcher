# NS Launcher
<img width="1920" height="1080" alt="Screenshot_20260621-201224" src="https://github.com/user-attachments/assets/dc96dd8e-b96e-4965-8bab-2f47916f2b5f" />


A Nintendo Switch-style home screen launcher for Android TV - clean, fast, and built for the couch.

> **Closed source.** Pre-built APKs are available in [Releases](../../releases). Source is not distributed.

---

## What it looks like

NS Launcher replaces your Android TV home screen with a UI inspired by the Nintendo Switch system menu:

- A horizontal app row front and center
- A minimal status bar (clock, Wi-Fi, mic)
- A bottom dock for quick access to Settings, Play Store, Gallery, Controllers, and About
- Sound feedback on navigation, launch, and menus - just like the real thing

## Screenshots:
<img width="1920" height="1080" alt="Screenshot_20260621-200403" src="https://github.com/user-attachments/assets/9d5e7630-a96e-4146-ad99-465375fc54fa" />
<img width="1920" height="1080" alt="Screenshot_20260621-200417" src="https://github.com/user-attachments/assets/ef862597-9258-4963-9de6-ba05d5354e3c" />
<img width="1920" height="1080" alt="Screenshot_20260621-200423" src="https://github.com/user-attachments/assets/6a1d124c-25e0-432e-8963-d328bd866402" />
<img width="1920" height="1080" alt="Screenshot_20260621-200434" src="https://github.com/user-attachments/assets/a38356b7-b407-4319-b642-dda348e4ea79" />

---

## Features

- **Home screen app row** - your favourite apps in one swipe
- **All Software grid** - browse every installed app in a full-screen grid
- **Rearrange apps** - hold select on any app to enter move mode, navigate left/right to reorder, hold again to confirm
- **Add / Remove from home screen** - long-press any app in All Software to pin or unpin it from the home row
- **UI navigation sounds** - authentic Steam Deck-style audio feedback
- **Live clock** - 12-hour format in the status bar
- **Quick-access dock** - Controllers (Bluetooth), Play Store, Gallery, Settings, About
- **No ads, no accounts, no telemetry**

---

## Requirements

- Android TV device (Android 8.0+)

Tested on Xiaomi MiBox 3 & 5. Should work on any Android TV / Google TV device.

---

## Installation

### Option A - Sideload via file manager (easiest)

1. Download the latest `app-release.apk` from [Releases](../../releases)
2. Transfer it to your TV (USB drive, network share, or send to your TV via an app like [Downloader](https://play.google.com/store/apps/details?id=com.esaba.downloader))
3. Open a file manager on the TV and tap the APK to install
4. Allow installation from unknown sources if prompted

### Option B - Install via ADB

```shell
adb connect <your-tv-ip>:5555
adb install app-release.apk
```

---

## Setting NS Launcher as your default home screen

### Method 1 - Remap the Home button (recommended, reversible)

Use [Button Mapper](https://play.google.com/store/apps/details?id=flar2.homebutton) to remap your remote's Home button to launch NS Launcher. This leaves your device's original launcher intact and is fully reversible.

### Method 2 - Disable the stock launcher (permanent until re-enabled)

> ⚠️ Do this at your own risk. These commands have been tested on Chromecast with Google TV. Steps may differ on other devices.

**Disable stock launcher:**
```shell
adb shell pm disable-user --user 0 com.google.android.apps.tv.launcherx
adb shell pm disable-user --user 0 com.google.android.tungsten.setupwraith
```
Press Home - the system will ask you to choose a default launcher. Select NS Launcher.

**Re-enable stock launcher:**
```shell
adb shell pm enable com.google.android.apps.tv.launcherx
adb shell pm enable com.google.android.tungsten.setupwraith
```

> **Note:** On Chromecast with Google TV, the dedicated YouTube button on the remote may stop working after disabling the stock launcher. Use Button Mapper to remap it as a workaround.

---

## How to use

| Action | Button |
|---|---|
| Navigate apps | D-pad left / right |
| Launch app | Select / Enter |
| Open app options | Hold Select (≈0.7s) |
| Enter move mode | Hold Select → "Move" |
| Confirm new position | Hold Select again |
| Open All Software | Navigate to the last card in the row |
| Add/Remove from home | Long-press app in All Software |
| Go back | Back / Escape |

---

## Credits

Built by **Zahidul Haque Tipu**

Based on [FLauncher](https://github.com/etiess/flauncher](https://gitlab.com/flauncher/flauncher) by Étienne Fesser - open-source Android TV launcher licensed under GPL v3.

Sound effects sourced from Deckthemes Switch 2 Sounds pack. (https://deckthemes.com/packs/view?themeId=12b04b34-00c1-4600-8e71-eb0a77f47962)

---

## License

NS Launcher is a closed-source skin. The underlying FLauncher engine it is built on is licensed under the [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.html).
