# 群晖 WebDAV 在 iPhone 上怎么播放视频？

如果影片存在群晖 NAS 上，可以在 DuoPlayer 添加 WebDAV 媒体源，直接浏览 NAS 上有权访问的视频目录。

[在 App Store 下载 DuoPlayer](https://apps.apple.com/us/app/duoplayer-video-player/id6830926628?l=zh-Hans-CN)

## 在同一个 Wi-Fi 下连接

1. **准备群晖 WebDAV 服务。** 在 DSM 中打开 WebDAV Server，确认已启用服务。记下实际使用的协议和端口。给观影账号授予目标共享文件夹的读取权限。
2. **填写媒体源。** 在 iPhone 上打开 DuoPlayer 的「添加媒体源」，选择「群晖 Synology NAS (WebDAV)」，填入服务地址和观影账号。假设 NAS 在 `192.168.1.100`，WebDAV 使用 HTTPS 端口 `5006`，共享目录名为 `video`，地址可以写成 `https://192.168.1.100:5006/video`。请以自己的配置为准。使用 HTTPS 时，地址应与证书匹配。
3. **测试连接后保存。** 从片库打开一段 H.264 视频与 AAC 音频的 MP4，确认能看到画面、听到声音并拖动进度。随后再试自己的 MKV 和字幕。

## 连不上或看不到影片

| 现象 | 先检查 |
| --- | --- |
| 连接超时 | iPhone 是否在同一 Wi-Fi，DuoPlayer 是否已获本地网络权限，端口是否为 WebDAV 服务使用的端口。 |
| 提示证书错误 | 核对地址的主机名与证书，确认 iPhone 信任该证书。 |
| 提示 401 或 403 | 核对账号密码和目标共享目录的读取权限。 |
| 能访问服务但列表为空 | 核对 URL 的目录路径，并确认该账号能读取实际存放视频的位置。 |
| MP4 能播，某些 MKV 播不了 | 记录容器、音视频编码和字幕类型。比较 WebDAV 文件播放和 Jellyfin 服务端处理的区别。 |

出门后，家中的局域网地址通常需要通过已配置好的 VPN 才能访问。可以先在家里把基本播放跑通，再用移动网络验证远程连接。

[媒体格式排查](MEDIA_COMPATIBILITY.md) · [DuoPlayer 社区](../README.md) · [反馈连接或播放问题](https://github.com/P-bit-display/DuoPlayer-Community/issues/new?template=bug_report.md)

**English** — Connect a Synology NAS to DuoPlayer on iPhone using your NAS WebDAV URL and a media account with read access. Test the connection on your home Wi-Fi and start with a known-good H.264/AAC MP4.
