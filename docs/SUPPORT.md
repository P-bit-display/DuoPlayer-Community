# iPhone 上 Jellyfin 连不上或无法播放？DuoPlayer 排障指南

| 遇到的问题 | 先检查这里 |
| --- | --- |
| 家里也连不上 | 在同一台手机、同一个 Wi-Fi 下用浏览器打开 Jellyfin 地址。核对协议、端口、路径和账号，再在 App 内点「测试连接」。 |
| 家里能播，出门连不上 | 用移动网络访问你配置的远程地址。家庭局域网地址通常只能在家中网络或已连接的 VPN 使用。 |
| WebDAV 能连接，看不到文件 | 核对服务地址、媒体目录路径和读取权限。[查看群晖 WebDAV 的 iPhone 连接步骤](synology-webdav-iphone.md)。 |
| 能看到海报，播放失败 | 先用一段 H.264/AAC 的 MP4 对照，再查看[格式与字幕指南](MEDIA_COMPATIBILITY.md)。 |

## Jellyfin 能看到海报，视频却播不了

1. 在同一台 iPhone、同一网络下，用浏览器登录同一个 Jellyfin 账号，尝试播放同一影片。
2. 在 DuoPlayer 试播一段 H.264 视频、AAC 音频的 MP4。如果只有某部影片失败，记下容器、音视频编码和字幕格式。尝试关闭字幕再对照一次。
3. 如果服务端有对应的播放会话，查看 Jellyfin 控制台显示的播放方式。提交反馈时附上这个信息，便于区分连接、格式和转码问题。

## Jellyfin 在家能连，移动网络连不上

先核对 App 里用的是家庭局域网地址还是已经配置好的远程地址。如果使用 VPN，连接后再测试。用 iPhone 浏览器验证该地址能否打开 Jellyfin 登录页，然后回到 DuoPlayer 测试连接。

[首次连接 Jellyfin](MOVIEPILOT_JELLYFIN_SOP.md) · [群晖 WebDAV 连接步骤](synology-webdav-iphone.md) · [DuoPlayer 下载](https://apps.apple.com/us/app/duoplayer-video-player/id6830926628?l=zh-Hans-CN)

[提交播放或连接问题](https://github.com/P-bit-display/DuoPlayer-Community/issues/new?template=bug_report.md) · [提交功能建议](https://github.com/P-bit-display/DuoPlayer-Community/issues/new?template=feature_request.md)

**English support.** Include your device, OS and app versions, source type, and the steps that reproduce the issue. For playback problems, include the file container, codecs and subtitle format if known. Remove passwords, tokens, private server addresses and personal filenames from screenshots or logs before posting.

For direct inquiries: support@p-bit-display.com
