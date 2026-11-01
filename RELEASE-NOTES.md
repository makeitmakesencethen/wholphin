# Wholphin — personal build (v1.0.2, 2026-11-01)

A custom build of [Wholphin](https://github.com/damontecres/Wholphin) v1.0.2, packaged as its own app so it
installs alongside the official one and never overwrites it.

## Assets

**`wholphin-2026-11-01-1.0.2-20-g38a9f5ca-armeabi-v7a.apk`** — 46.7 MB. 32-bit ARM.

**`wholphin-2026-11-01-1.0.2-20-g38a9f5ca-universal-arm.apk`** — 78.9 MB. The same build plus the
`arm64-v8a` native libraries from upstream Wholphin v1.0.2, for 64-bit devices. Everything else is
identical: the dex files, resources and 32-bit libraries are unchanged, and the added libraries are
byte-identical to upstream's.

Both are signed with the same key, so either updates over the other. They are **not** signed with the key
used by any earlier build, so they install as a new app rather than updating one.

## Install

Fire TV: install *Downloader* (AFTVnews), allow unknown sources for it, open the APK link there.

Android TV: enable developer options and network debugging, then from a computer on the same network

```
adb connect <tv-ip>:5555
adb install -r <file>.apk
```

It appears in the launcher as **Wholphin**. First run asks for your Jellyfin server.

The in-app update check points at upstream Wholphin and will offer v1.0.9. That is a different app —
ignore it, or change *Settings → Advanced → Update URL*.

## What is different from upstream

- subtitle rendering matches between the MPV and ExoPlayer backends, including per-font metrics
- stereo downmix performed on the device (a media3 audio processor with role-based folding, dropped LFE,
  per-layout normalisation), with the debug overlay reporting what was mixed and the source versus output
  channel counts
- playback settings for the trickplay window: size, border on/off, border colour, border thickness,
  rounded corners, previewed with the same composable that draws the real window
- interface fonts and a subtitle style carried over from the device this was built for

## Licence

Wholphin is GPL-2.0. Upstream source: https://github.com/damontecres/Wholphin, tag `v1.0.2`. These are
personal builds of a modified GPL application, shared privately; the modified source is being reconstructed
and will be published here when it is ready.
