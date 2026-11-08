# Media & Codec Compatibility Matrix

## Overview
DuoPlayer adopts an intelligent dual-engine architecture:
- **AVFoundation (AVPlayerEngine)**: First-class hardware-accelerated playback for Apple-native formats, high energy efficiency, system Picture-in-Picture (PiP), and native HDR10 / Dolby Vision output.
- **VLC Engine (VLCPlayerEngine)**: Fallback engine handling complex MKV containers, ASS/SSA stylized subtitles, multi-track audio switching (e.g., DTS, FLAC, Vorbis), and non-standard bitstreams.

## Video Codec & Container Matrix

| Container | Video Codec | Audio Codec | Subtitles | Recommended Engine | Hardware Accel | Notes |
|:---|:---|:---|:---|:---|:---|:---|
| MP4 / M4V | H.264 (AVC) | AAC, AC3, E-AC3 | SRT, WebVTT, tx3g | AVPlayer | Yes (VideoToolbox) | Direct native playback |
| MP4 / MOV | H.265 (HEVC) 8/10-bit | AAC, E-AC3, TrueHD (downmix) | SRT, WebVTT | AVPlayer | Yes | Full native 4K support |
| MKV (Remote Jellyfin) | H.264 / HEVC | AAC, AC3, E-AC3 | SRT, WebVTT | AVPlayer (via HLS fMP4) | Yes (Hardware) | Dynamic Jellyfin HLS remuxing prevents black screen |
| MKV (Local / Raw) | HEVC 10-bit / VP9 | DTS-HD, TrueHD, FLAC | ASS / SSA (styled) | VLC Engine | Software / Hybrid | VLC handles complex font rendering & non-Apple demux |
| WebM | VP8 / VP9 / AV1 | Opus, Vorbis | WebVTT | VLC Engine | Yes (AV1 on M3+/A17+) | Open web media formats |

## HDR & Dolby Vision Playback Decisions

| Standard | Profile / Level | AVPlayer Native Support | Decision Logic & Fallback Path |
|:---|:---|:---|:---|
| **SDR (Rec.709)** | Standard 8-bit | Full | Direct AVPlayer playback |
| **HDR10** | Main 10, Rec.2020, ST 2084 | Full | Native AVPlayer rendering on HDR displays |
| **HLG** | ARIB STD-B67 | Full | Native AVPlayer rendering on HDR displays |
| **Dolby Vision Profile 5** | Single-track HEVC, IPT-C2, no fallback | Full on Apple devices | Direct AVPlayer playback; tone-maps on SDR displays |
| **Dolby Vision Profile 7 (MEL/FEL)** | Dual-track UHD Blu-ray | Base Layer only | Fallback: Extracts base HDR10 layer; ignores secondary EL |
| **Dolby Vision Profile 8.1** | Cross-compatible HEVC + HDR10 base | Full | Direct AVPlayer playback; uses HDR10 metadata fallback |
| **Dolby Vision Profile 8.4** | HLG base (Apple Camera format) | Full | Direct AVPlayer playback |

## Subtitle Engine
- **External SRT / VTT**: Parsed into native timed cues (`SubtitleCue`), rendered via synchronized SwiftUI overlay with customizable typography and position.
- **Embedded MKV Subtitles**: Extracted or rendered by VLC engine with font styling preserved.
- **ASS / SSA Stylized**: Parsed with timing and formatting tags or handled by VLC's libass renderer.
