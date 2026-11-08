# Silent Method

Free, open-source alternative to paid "TikTok upload methods". Patches an MP4 so TikTok keeps max quality.

**Use it:** open https://ascendedtweaks.github.io/silent-method/. Drop a video in, get `<name>_tt.mp4`, upload that on tiktok.com (TikTok Studio, desktop) with "High quality uploads" on.

- No install, no account.
- Nothing is uploaded: the file is processed in your browser.
- No re-encode: video and audio stay bit-identical.

## What it changes (container only)

The video and audio packets are copied unchanged into an MPEG-TS stream (H.264 + AAC, ffmpeg-style PIDs and 1.4 s start offset). The file keeps its `.mp4` name. TikTok reads it and plays it at 720p60; phone galleries often show 0:00 or only play the sound.

Limits: H.264 video, AAC audio, max 5 minutes, no fragmented MP4. No guarantee: TikTok can change its pipeline any time.
