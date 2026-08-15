# ▶️ TizenTube fork (0-wea-src)

> A fork of [TizenTube](https://github.com/reisxd/TizenTube) by [@reisxd](https://github.com/reisxd).
> Fixes the **encoding bug** that locked certain videos to **360p**.

## 🚀 Why this fork exists

On Samsung TVs, the YouTube client binds some videos to VP9/AV01 codecs that the TV can only decode at **360p**.
The original TizenTube had two issues that made its codec setting useless:

1. The settings UI wrote the key **`preferredVideoCodec`**, while the format filter reads **`videoPreferredCodec`** — a key mismatch, so the setting silently did nothing.
2. The default was `any`, so the player kept binding the low-resolution VP9 formats.

This fork fixes both:

* **Correct key** in the settings UI — the codec menu now actually works.
* **AVC1 by default** (`videoPreferredCodec: avc1`) — the player picks H.264 (AVC1) formats on videos that offer them, unlocking the video's native resolution.

> ⚖️ **Trade-off:** dual-codec videos may cap at **1080p** (the AVC1 ceiling). Videos that only exist in VP9/AV01 play exactly as before — the filter only applies when the preferred codec is present in the format list, so VP9-only videos are never broken.

## 📥 Installation (TizenBrew)

1. Install [TizenBrew](https://github.com/reisxd/TizenBrew) on your Samsung TV.
2. Open **Module Manager → Add → GH** and enter:
   ```
   gh/0-wea-src/TizenTube
   ```
3. Launch the module — it displays as **TizenTube (0-wea-src)**, so it can't be confused with any other installed TizenTube version.

> 💡 Don't run two TizenTube modules at the same time — they inject into the same app.

## ✨ Features

- 📺 **Picture-in-Picture Mode**
- 🛑 **Ad Blocker**: enjoy your favourite streaming website without interruptions
- ❗ **SponsorBlock Support**: automatically skip sponsored segments
- ⏭️ **Video Speed Control**: adjust playback speed to your preference
- 🔺 **DeArrow Support**: remove clickbait and misleading video titles

## 💬 Support

Report issues or request features via the [issue tracker](https://github.com/0-wea-src/TizenTube/issues).

Original TizenTube community: [r/TizenTube](https://www.reddit.com/r/TizenTube/) · [Discord](https://discord.gg/m2P7v8Y2qR) · [Telegram](https://t.me/tizentubeofficial)

---

<p align="center">
    <img width="600px" src=".github/assets/TizenTube Standalone Banner.png">
    <br>
    <sub> TizenTube logo, banner and README by <a href="https://github.com/Zyborg777">@Zyborg777</a> </sub>
</p>