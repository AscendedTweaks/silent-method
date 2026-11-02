# Silent Method

Free, open-source alternative to paid "TikTok upload methods". Patches an MP4 so TikTok keeps max quality.

**Use it:** open https://ascendedtweaks.github.io/silent-method/. Drop a video in, get `<name>_tt.mp4`, upload that on tiktok.com (TikTok Studio, desktop) with "High quality uploads" on.

- No install, no account.
- Nothing is uploaded: the file is processed in your browser.
- No re-encode: video and audio stay bit-identical.

## What it changes (container only)

- `moov` before `mdat` (faststart), audio/video interleaved per audio frame
- fake 8-byte video samples in `stsz`/`stco` up to duration × 400 (not in `stts`, so players ignore them)
- last video frame duration 1 in `stts`
- `btrt` max bitrate = average bitrate, `pasp` 1:1
- creation/modification times zeroed, `udta`/`meta` removed (e.g. CapCut tags)

Limits: MP4/MOV, max 5 minutes, max 4 GB, no fragmented MP4. No guarantee: TikTok can change its pipeline any time.
