[![Buy Me a Coffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-support-yellow?logo=buy-me-a-coffee&logoColor=white)](https://buymeacoffee.com/tit_robotics)

# Navimow Beta Community Edition - Video Compressor

Compress your videos to MP4 (under 20 MB) right on your computer, ready to
share on Discord. Everything runs locally through ffmpeg - nothing is
uploaded anywhere.

Available for **Mac** (Apple Silicon) and **Windows** (10/11).

## Download

Grab the latest release for your platform from the
[Releases page](https://github.com/tit-robotics/navimow-beta-compresseur/releases).

- **Mac**: `Compresseur.zip` - unzip, then double-click `Compresseur.command`.
ffmpeg is already built into the file, nothing else to install.
- **Windows**: `VideoCompressor-Installer.zip` - unzip, then double-click
`1-CLICK HERE TO INSTALL.bat`. Python and ffmpeg are downloaded and set up
automatically if you don't already have them.

A setup guide (PDF, with screenshots) is attached to each release.

## Features

- Compress one video, or several at once (batch processing)
- Target a specific file size (up to 20 MB, the Discord free-tier limit)
- Hardware-accelerated encoding when available (VideoToolbox on Mac,
NVENC/QuickSync/AMF on Windows), with automatic fallback to software
encoding otherwise
- Adjustable audio bitrate, or strip audio entirely
- Playback speed control (1x to 16x) to shrink long recordings further,
with natural audio pitch preserved automatically
- Trim a clip before compressing, so you only spend your size budget on
the part that matters
- Choice of encoding speed when software encoding kicks in, quality vs.
speed
- Supports all common formats, including iPhone HEVC/MOV and 4K
- Everything processed locally - no upload, no account, no tracking

## What's new

### v2.1 (Mac)

- **Higher Discord size limit** - the target size cap is now 20 MB (up
from 10 MB), matching Discord's current free-tier upload limit.

### v2.0 (Windows)

- **Feature parity with Mac v2.0** - trim a clip down to just the part you
need (Trim start / Trim end fields and a Cut button), and choose the
encoding speed when software encoding kicks in. Same interface as the
Mac version.
- **Higher Discord size limit** - the target size cap is now 20 MB (up
from 10 MB), matching Discord's current free-tier upload limit.
- **More reliable installer** - the desktop shortcut is now created using
the real Desktop folder reported by Windows, so it no longer fails when
OneDrive has redirected the Desktop (a previously common install-breaking
error).
- **New app icon**, used for both the built app and the desktop shortcut.
- **Always shows the current version** - the app's local page now sends
proper no-cache headers, so a browser that loaded an older version never
keeps showing it after an update.
- **Clear end-of-batch confirmation** - a "Compression complete." message
and progress bar now appear once the whole queue is done, matching the
Mac version.

### v2.0 (Mac)

- **Trim before compressing** - cut a clip down to just the part you need
with new Trim start / Trim end fields and a Cut button, right from the
preview player. Compress only the segment that matters instead of the
whole video.
- **Choice of encoding speed** - a new Encoding speed dropdown (used when
software encoding kicks in) lets you trade a bit of processing time for
better quality, or go faster when you just need a quick export.

### v1.2.0 (Mac)

- **Playback speed control** - speed up a video before compressing it (1x
to 16x). A shorter video means more quality budget per second, so a long
screen recording sped up 2x-4x can look noticeably sharper at the same
10 MB target. Audio pitch is kept natural automatically (no "chipmunk"
voices), no matter the speed.
- **Faster hardware compression** - VideoToolbox now runs its own quick
refinement loop to land close to the 10 MB target, instead of always
falling back to slow multi-pass software encoding afterwards.
- **Better HEVC/MOV handling** - videos with an unreadable or unusual
audio track no longer fail outright; the app retries without audio and
tells you when it had to.
- **No more silent conflicts** - the app automatically frees its port on
startup if a previous run is still holding it, so you'll never end up
looking at a stale version by accident.

### v1.10 (Windows)

- **Fully automatic installer** - Python and ffmpeg (with libx264/HEVC
support) are downloaded and set up on their own if missing. Nothing to
install by hand.
- **Compress several videos at once** - drag and drop multiple files, or
select several in the file picker.
- **Faster compression** - hardware encoding (NVENC/QuickSync/AMF) runs
its own quick refinement loop to land close to the 10 MB target.
- **Fixed HEVC/MOV support** - videos with an unreadable or unusual audio
track no longer fail outright.
- **No more silent conflicts** - the app automatically closes any other
running copy of itself on startup.

## License and credits

(c) TiT-Robotics - [www.tit-robotics.com](https://www.tit-robotics.com) -
Navimow Beta Community Edition. All rights reserved.
