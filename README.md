# ffmpeg-mini-win64

Minimal `ffmpeg.exe` and `ffprobe.exe` builds for Windows x64, LGPL-licensed,
cross-compiled from Linux with mingw-w64.

Tailored for [MillstoneMuxer](https://github.com/nichiken) (lossless A/V mux + media info + yt-dlp pipeline).
Optimized for **size** rather than feature completeness.

## What's included

- **Containers**: MP4 / MOV / M4A / Matroska / WebM / MP3 / WAV / FLAC / OGG
- **Decoders**: H.264 / H.265 / VP9 / AAC / MP3 / FLAC / Opus / Vorbis / ALAC / PCM
- **Encoders**: ALAC / AAC / FLAC / PCM
- **Bitstream filters** for stream copy (`-c copy`)
- Static linking, stripped, optimized with `-Os`

## What's NOT included

- AV1 decoder (libdav1d) — common in newer YouTube streams; planned for future release
- x264 / x265 / libvpx encoders (re-encoding video)
- Subtitle rendering (libass / fontconfig / harfbuzz)
- Hardware acceleration (NVENC / AMF / VAAPI / QSV)
- Network protocols (HTTP / HTTPS / RTMP / RTSP)
- `ffplay.exe`
- GPL-only codecs

If you need any of these, use the upstream
[BtbN/FFmpeg-Builds](https://github.com/BtbN/FFmpeg-Builds/releases) instead.

## Releases

Stable releases are published to [Releases](https://github.com/nichiken/ffmpeg-mini-win64/releases).
Each release ships:

- `ffmpeg-mini-win64.zip` — the binaries
- `ffmpeg-mini-win64.zip.sha256` — SHA-256 checksum

## Building locally

This repo only contains the build workflow; ffmpeg source is fetched at build time.
The build runs on `ubuntu-latest` GitHub-hosted runners using mingw-w64.

To trigger a build manually: Actions → "Build ffmpeg-mini for Windows x64" → Run workflow.
To cut a release: push a tag matching `v*` (e.g. `git tag v1.0.0 && git push --tags`).

## License

The build outputs are LGPL-licensed (FFmpeg's LGPL license is bundled into the zip).
This repository's build scripts and config are licensed under LGPL-3.0 (see [LICENSE](./LICENSE)).
