# Bloxy Flix — Stream Source

> A free, watermark-free restreaming hub for international public broadcasts, powered by [Intchoson](https://www.intchoson.com).

---

## Overview

**Bloxy Flix** is an open, publicly accessible streaming service designed to provide clean and unobstructed access to international television and radio broadcasts. The platform aggregates live feeds from several hard-to-reach broadcasters and makes them available for restreaming to YouTube, Twitch, and other platforms — without watermarks, automatic content blocks, or paywalls.

The Stream Source portal serves as the technical backbone of Bloxy Flix's restreaming infrastructure, offering direct HLS stream endpoints alongside an in-browser player for immediate preview and testing.

---

## Live Streams

The following broadcast feeds are currently available through the Bloxy Flix Stream Source:

| Channel | Type | Source |
|---|---|---|
| Korean Central Television (KCTV) | Video (HLS) | Via Intchoson |
| Korean Central Broadcasting Station (KCBS) | Audio (HLS) | Via Intchoson |
| Voice of Korea (VOK) | Audio (HLS) | Via Intchoson |
| Pyongyang FM | Audio | Hosted by Bloxy Flix |

Stream endpoints are available directly on the [Stream Source portal](https://bloxyflix-kctv.netlify.app). KCTV and the radio channels sourced via Intchoson are delivered in HLS (`.m3u8`) format, compatible with OBS Studio, Streamlabs, FFmpeg, VLC, and any broadcast software that supports HLS input. Pyongyang FM is independently hosted and maintained by Bloxy Flix.

---

## Features

- **Watermark-free streams** — All feeds are provided without overlaid branding or visual obstruction.
- **No automatic blocking** — Stream sources are maintained to avoid automated content ID or takedown triggers during rebroadcast.
- **In-browser preview** — The Stream Source portal includes a built-in Video.js player for KCTV and native audio players for radio channels, allowing quick verification before going live.
- **One-click credit copy** — Built-in buttons generate properly formatted attribution text for use in stream titles and descriptions.
- **Platform agnostic** — Streams are compatible with any platform that accepts RTMP input or HLS ingest, including YouTube Live, Twitch, Facebook Live, and Kick.

---

## Usage

> ⚠️ **Current Method — Screen Capture Live Streaming:** Direct HLS ingest is not yet available. Once Intchoson officially provides a public HLS endpoint, Bloxy Flix will integrate direct stream ingest and update this documentation accordingly.

### Restreaming via Screen Capture (OBS Studio)

This method works for any platform (YouTube, Twitch, Kick, Facebook Live, etc.) and requires no technical stream configuration beyond a standard OBS setup.

**Requirements:**
- [OBS Studio](https://obsproject.com/) (free, open source)
- A web browser (Chrome or Firefox recommended)
- A streaming account on your platform of choice

**Steps:**

1. Open the [Bloxy Flix Stream Source portal](https://bloxyflix-kctv.netlify.app) in your browser.
2. Select the channel you wish to restream using the tab buttons (KCTV, KCBS, Voice of Korea, or Pyongyang FM).
3. Press **Play** on the in-browser player to begin the stream.
4. Open **OBS Studio** and add a new **Window Capture** or **Browser Source** pointing to the stream portal.
   - For **Window Capture**: Select your browser window from the source dropdown.
   - For **Browser Source**: Enter `https://bloxyflix-kctv.netlify.app` as the URL and set your desired resolution.
5. Adjust the canvas crop in OBS to frame only the player area, removing any surrounding page elements.
6. Configure your **Stream Settings** in OBS (Settings → Stream) with your platform's server and stream key.
7. Click **Start Streaming**.

**Recommended OBS Settings:**

| Setting | Recommended Value |
|---|---|
| Base (Canvas) Resolution | 1280×720 or 1920×1080 |
| Output (Scaled) Resolution | Match canvas |
| Frame Rate | 30 fps |
| Encoder | x264 or hardware (NVENC/AMF) |
| Bitrate | 2500–6000 Kbps (platform dependent) |

### Adding Attribution to Your Stream

Before going live, include the credit text in your stream title or description. Use the **Copy Stream Supporter Credit** button on the portal to automatically generate the correct attribution for whichever channel you are streaming.

---

## Roadmap

| Feature | Status |
|---|---|
| Screen capture restream support | ✅ Available now |
| Official HLS m3u8 direct ingest | ⏳ Pending — awaiting official public HLS provision from Intchoson |
| Additional channel support | 🔜 Planned |

> Direct HLS ingest will allow restreaming software such as OBS, FFmpeg, and Streamlabs to pull the live feed without screen capture, resulting in higher quality and lower system overhead. This feature will be enabled as soon as Intchoson makes an officially supported HLS stream publicly available.

---
## Attribution & Credit

Bloxy Flix makes use of stream infrastructure provided by **Intchoson** for KCTV, KCBS, and Voice of Korea feeds. Please note that **Bloxy Flix and Intchoson are independent services and are not affiliated with one another.** Pyongyang FM is hosted independently by Bloxy Flix and is unrelated to Intchoson.

All users who restream content through this service are kindly requested to include the following attribution in their stream title, description, or chat:

```
Source: [Channel Name] ~ via https://www.intchoson.com
```

One-click credit copy buttons are available directly on the [Stream Source portal](https://bloxyflix-kctv.netlify.app) for convenience.

**Failure to credit Intchoson undermines the sustainability of this service. Please credit accordingly.**

---

## Disclaimer

All streams provided through Bloxy Flix are intended strictly for **educational, informational, and journalistic purposes**. Bloxy Flix is an independent service and is not affiliated with, endorsed by, or in any formal partnership with any of the broadcasters featured on this platform, including but not limited to KCTV, KCBS, Voice of Korea, or Pyongyang FM. Bloxy Flix and Intchoson are separate, independent entities with no formal affiliation. The use of Intchoson's stream infrastructure does not constitute a partnership, endorsement, or organisational relationship of any kind.

Users are solely responsible for ensuring that their use of these streams complies with the terms of service of any platform they restream to, as well as all applicable local, national, and international laws. Bloxy Flix assumes no liability for any misuse of the streams or endpoints provided herein.

---

## Related Links

- **Bloxy Flix Main Site** — [bloxyflix.netlify.app](https://bloxyflix.netlify.app)
- **Stream Source Portal** — [bloxyflix-kctv.netlify.app](https://bloxyflix-kctv.netlify.app)
- **Stream Infrastructure** — [intchoson.com](https://www.intchoson.com)

---

*© Bloxy Flix. All rights reserved. Stream infrastructure provided by Intchoson.*
