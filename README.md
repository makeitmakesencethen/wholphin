# Wholphin builds

Personal builds of [Wholphin](https://github.com/damontecres/Wholphin), packaged so they install beside the
official app (`com.github.damontecres.wholphin.mod`) and never overwrite it. They show up in the launcher
as **Wholphin**.

## Download

Take the latest release:

- `…-armeabi-v7a.apk` — 32-bit ARM. Use this unless it refuses to install.
- `…-universal-arm.apk` — same build with 64-bit ARM libraries. Use it if the 32-bit file fails with
  `INSTALL_FAILED_NO_MATCHING_ABIS`.

Both are signed with the same key, so they update over each other. Checksums are in `SHA256SUMS.txt` on the
release.

## Install

Fire TV: install *Downloader* by AFTVnews, allow unknown sources for it, then open the APK link in Downloader.

Android TV: enable developer options and network debugging, then

```
adb connect <tv-ip>:5555
adb install -r <file>.apk
```

First run asks for your Jellyfin server. Ignore the in-app "update available" notice — it compares against
upstream Wholphin and offers a different app.

## What is in these builds

- subtitle rendering identical across the MPV and ExoPlayer backends
- on-device stereo downmix, with the debug overlay reporting what was mixed and the channel counts
- trickplay window settings: size, border on/off, colour, thickness, rounded corners, live preview
- interface fonts and subtitle styling carried over from the source device

## Licence

Wholphin is GPL-2.0 — upstream source at the link above, tag `v1.0.2`. These are personal builds of a
modified GPL application, shared privately; the modified source is being reconstructed and will be published
here.
