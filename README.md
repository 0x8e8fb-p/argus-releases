# Argus — the ad blocker for Android TV

Argus blocks ads and trackers **at the DNS layer** on Android TV, Google TV and
Fire TV: YouTube, Prime Video, Hotstar, SonyLiv, Zee5 and anything else on the
device. It runs a local VPN that filters DNS, so every lookup is resolved on the
TV itself — nothing is routed through us and there is no account in the path.

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
[`v1.3.4`](https://github.com/0xargusapp/Argus-TV/releases/tag/v1.3.4).

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

1. Create a profile at [my.nextdns.io](https://my.nextdns.io) and copy its
   config ID.
2. Argus → Settings → Config ID, paste it.
3. Home → Start, then approve the VPN prompt.

Blocklists, allow/deny rules and YouTube ad blocking are configured in the
NextDNS dashboard. Argus only relays DNS to that profile over DoH.

## Requirements

Android TV 7.0 (API 24) or newer, ARM or x86. One universal APK.

## Notes

- An account is optional. Protection works signed out, offline, and after an
  account is deleted.
- Not on the Play Store, deliberately: a DNS-filtering VPN is not a category
  the store supports.
- Found a bug or want to appeal a ban? argusapp@proton.me
