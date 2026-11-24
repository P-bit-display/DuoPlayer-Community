# Jellyfin vs. WebDAV playback on iPhone

A file with an `.mkv` extension can contain many combinations of video, audio and subtitle tracks. Jellyfin may serve the original streams, remux the container or transcode a stream depending on the file, client and server settings. WebDAV serves the file itself. This guide describes a repeatable comparison. The cases below are checks to run, and results depend on your setup.

| Test case | What to compare |
| --- | --- |
| H.264 video and AAC audio in MP4 | Verify that both sources start playback, produce sound and allow seeking. |
| The same MKV on both sources | Note whether playback starts and whether the Jellyfin dashboard reports direct play, remuxing or transcoding. |
| The same title with subtitles off and on | Record subtitle format, track selection, whether text appears, and whether the Jellyfin playback method changes. |

Use the same iPhone, app version, network and file for both runs. Record each result as Pass, Fail or Untested. If playback fails, capture the error and share codec details instead of the original movie.

[English product overview](../README.en.md) · [Report a compatibility result](https://github.com/P-bit-display/DuoPlayer-Community/issues/new?template=bug_report.md) · [Download DuoPlayer](https://apps.apple.com/us/app/duoplayer-video-player/id6830926628)
