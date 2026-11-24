# DuoPlayer — Jellyfin, Emby and NAS Video Player for iPhone

DuoPlayer plays video from your own Jellyfin, Emby or WebDAV library, including a Synology NAS with WebDAV enabled. In the iPhone Duo tabletop layout, the movie plays above the timeline and subtitle controls.

[Download on the App Store](https://apps.apple.com/us/app/duoplayer-video-player/id6830926628) · [中文介绍](README.md) · [Report a problem](https://github.com/P-bit-display/DuoPlayer-Community/issues/new?template=bug_report.md)

<img src="docs/assets/tabletop-controls.jpg" width="320" alt="Tabletop playback layout with video above playback controls" />

## Connect your library

- **Jellyfin or Emby.** In Add Media Source, select Jellyfin / Emby, enter your server address and viewing account, test the connection, then save.
- **Synology NAS or other WebDAV storage.** Choose WebDAV, enter the WebDAV service URL and directory, then test with an account that can read that directory.
- **First playback.** On your home Wi-Fi, try a familiar H.264/AAC MP4 before testing files with different codecs or subtitles.

[Playback compatibility guide in English](docs/jellyfin-webdav-playback-en.md) · [Foldable screenshots](docs/DEVICE_COMPATIBILITY.md#界面截图) · [Synology setup guide in Chinese](docs/synology-webdav-iphone.md)

## Browse and watch

- **Foldable layouts.** Tabletop mode places playback controls below the video. Book mode arranges the panes side by side.
- **Chinese title search.** Search by title, full pinyin or pinyin initials.
- **Interface languages.** Simplified Chinese, Traditional Chinese, English and Japanese.

## iPhone playback and setup questions

- **How do I watch videos from a Synology NAS on iPhone?** Connect to the NAS WebDAV service with a viewing account that can read the shared folder. [Synology WebDAV setup (Chinese)](docs/synology-webdav-iphone.md)
- **Why does an MKV play through Jellyfin but fail over WebDAV?** Compare the same file on both sources and check the playback method in the Jellyfin dashboard. [MKV, subtitles and transcoding on iPhone](docs/jellyfin-webdav-playback-en.md)
- **What does a foldable iPhone video player look like in tabletop mode?** The video sits above the timeline, playback and subtitle controls. [iPhone Duo foldable playback screenshots](docs/DEVICE_COMPATIBILITY.md#界面截图)

## Help improve DuoPlayer

When reporting playback trouble, include your app and iOS versions, media source and server version, container, audio and video codecs, and subtitle format. Remove account details, server addresses, and tokens from screenshots or logs.

[Open a support issue](https://github.com/P-bit-display/DuoPlayer-Community/issues/new?template=bug_report.md) · [Privacy policy](docs/PRIVACY_POLICY.md)
