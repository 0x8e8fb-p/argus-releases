# Argus — the ad blocker for Android TV

Argus blocks ads and trackers **at the DNS layer** on Android TV, Google TV and
Fire TV: YouTube, Prime Video, Hotstar, SonyLiv, Zee5 and anything else on the
device. It runs a local VPN that answers DNS through a filtering profile Argus
manages for you, so there is nothing to configure, no account in the path, and
no browsing history collected.

**Download and install guide → https://argus-alpha-dusky.vercel.app/download**

That page carries the current version, the file size, the SHA-256 and the
install steps. This repository holds the signed APKs and their notes.

---

## Direct download

Stable URL, always the newest published build:

```
https://github.com/0xargusapp/Argus-TV/releases/download/latest/argus.apk
```

Every version keeps its own tag, for example
[`v1.3.6`](https://github.com/0xargusapp/Argus-TV/releases/tag/v1.3.6).

## Install

### Downloader (no computer)

1. Install **Downloader by AFTVnews** from your TV's store.
2. On Android TV 12+ enable Developer Options: Settings → System → About → tap
   **Android TV OS build** seven times.
3. In Downloader, enter:
   ```
   github.com/0xargusapp/Argus-TV/releases/download/latest/argus.apk
   ```
4. Allow Downloader to install unknown apps, then Install.

### Obtainium (updates itself)

Add `https://github.com/0xargusapp/Argus-TV` as an app source with the APK
filter `argus\.apk$`. Every future release is offered as an update.

### adb (from a computer)

```
adb install -r argus.apk
```

## Verify what you installed

```
shasum -a 256 argus.apk
```

Compare with `argus.apk.sha256` on the release, or with the checksum printed on
the download page. Every build is signed with the same key
(`CN=Argus, O=NexusBlock`), so updates install over the top — no uninstall.

## First run

1. Open Argus and press **Start**.
2. Approve the Android VPN prompt — it appears once.

That is the whole setup. The filtering profile is fetched automatically, and
blocklist changes reach the TV on its next refresh without a new install.

## Requirements

Android TV 7.0 (API 24) or newer, ARM or x86. One universal APK.

## Notes

- An account is optional. Protection works signed out, offline, and after an
  account is deleted.
- Not on the Play Store, deliberately: a DNS-filtering VPN is not a category
  the store supports.
- Found a bug or want to appeal a ban? argusapp@proton.me
