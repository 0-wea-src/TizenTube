# TizenTube fork (0-wea-src)

A fork of [TizenTube](https://github.com/reisxd/TizenTube) fixing the **360p-only playback** bug on Samsung TVs: some videos were locked to 360p because the player bound them to VP9/AV01 formats the TV can't decode at higher resolutions.

## What changed

- The codec setting actually works now (upstream wrote the wrong config key — the menu silently did nothing)
- Default codec is `avc1` — affected videos play at up to 1080p

## Codec setting

Settings → Video Player → Preferred Video Codec: `avc1` (default) fixes the stuck videos, `Any` unlocks 4K HDR. If a video ever gets stuck at 360p again, set it back to `avc1`.

## Install

TizenBrew → **Module Manager → Add → GH** → `0-wea-src/TizenTube`

## Issues

[Open an issue](https://github.com/0-wea-src/TizenTube/issues)