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

> ⚖️ **Trade-off (and the toggle):** YouTube only offers AVC1 (H.264) up to **1080p** — 4K/HDR is VP9/AV1-only. So with the default `avc1` setting, videos that exist in several formats top out at 1080p. Videos that only exist in VP9/AV01 are left untouched — the filter only applies when the preferred codec is actually present in the format list.
>
> You can switch back to **Any** anytime in **Settings → Video Player → Preferred Video Codec** (that menu is fixed in this fork — upstream it silently did nothing). Result: videos your TV can decode well play in 4K again; the videos that were stuck at 360p go back to 360p.

## 📥 Installation (TizenBrew)

1. Install [TizenBrew](https://github.com/reisxd/TizenBrew) on your Samsung TV.
2. Open **Module Manager → Add → GH** and enter:
   ```
   0-wea-src/TizenTube
   ```
   (no `gh/` prefix — the module manager adds it automatically)
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