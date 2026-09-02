# Argus — Ad Blocker for Android TV

Argus blocks ads system-wide on your Android TV / Google TV / Fire TV: YouTube, Prime Video, Hotstar, SonyLiv, Zee5, and 20+ other streaming apps. It runs a local VPN that filters DNS — everything happens on the device, nothing leaves it.

**Latest APK (stable URL, always the newest build):**
```
https://github.com/0x8e8fb-p/argus-releases/releases/download/latest/argus.apk
```

---

## Install — pick the easiest path

### 1. Downloader app (easiest, TV-only, no computer)

1. Open the app store on your TV (Google Play or Amazon Appstore) and install **Downloader by AFTVnews** (orange icon).
2. On Google TV / Android TV 12+: enable Developer Options first — Settings → System → About → tap **Android TV OS build** 7 times.
3. Open Downloader, enter:
   ```
   github.com/0x8e8fb-p/argus-releases/releases/download/latest/argus.apk
   ```
4. When prompted, allow Downloader to **install unknown apps** (Settings button in the prompt).
5. Select **Install**. Done.

### 2. Obtainium (auto-updates forever)

If you already use [Obtainium](https://github.com/ImranR98/Obtainium):
1. Add App → paste `https://github.com/0x8e8fb-p/argus-releases`
2. Set "APK filter" to `argus\.apk$` if asked.
3. Install. Obtainium notifies and installs every future update.

(Argus also has its own built-in updater — either mechanism works.)

### 3. Send Files to TV / LocalSend (phone → TV)

1. Install **Send Files to TV** (or LocalSend) on both phone and TV from the Play Store.
2. Download `argus.apk` on your phone from the stable URL above.
3. Send it to the TV, open the received file, allow install from unknown sources when asked, install.

### 4. USB drive

1. Copy `argus.apk` to a FAT32 USB stick.
2. Plug into the TV, open a file manager (X-plore or FX File Explorer from the Play Store — not the stock one).
3. Open the APK, allow unknown sources for the file manager, install.

### 5. adb (advanced)

```bash
adb connect <tv-ip>:5555
adb install argus.apk
```
Enable Developer Options + USB/Wireless debugging on the TV first. adb installs stay exempt from Google's developer-verification checks.

### 6. F-Droid client (custom repo)

Add this repository in your F-Droid client (Repositories → +):
```
https://0x8e8fb-p.github.io/argus-releases/repo/
```
The repo is signed by the same key as the APKs here — updates flow automatically after each release.

---

## After install (fresh TV checklist)

1. **Approve the VPN dialog** when Argus first opens — required, it's how filtering works.
2. Recommended: Settings (Argus) → **Always-on VPN** → enable it in the system VPN settings — keeps protection up across reboots.
3. Recommended: allow the **battery optimization exemption** when prompted.
4. Optional (power users): system Private DNS toggle needs one adb command:
   ```bash
   adb shell pm grant com.nexusblock android.permission.WRITE_SECURE_SETTINGS
   ```
   Argus works fully without it.

## Troubleshooting

- **"Blocked by Play Protect" / "unverified developer"** — choose Details → Install anyway. Argus is not registered with Google's developer verification; nothing is wrong with the APK. (Android is adding a stricter flow from late 2026: enable it once under Developer Options → "Apps from unverified developers" if your device requires it.)
- **App icon missing from home screen** — some launchers hide sideloaded apps: Settings → Apps → See all apps → Argus. Most TV launchers show it normally.
- **Verify your download** — `sha256sum argus.apk` must match `argus.apk.sha256` attached to the [latest release](https://github.com/0x8e8fb-p/argus-releases/releases).

## Not on Google Play / Amazon Appstore

Both stores ban system-wide ad blockers by policy. Sideloading via the paths above is the official distribution channel — only trust APKs from this repository.
