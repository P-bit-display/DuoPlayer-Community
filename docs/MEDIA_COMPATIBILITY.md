# 为什么同样是 MKV，有的能播，有的需要转码？

MKV、MP4 是容器，里面可以装入不同编码的视频、音轨和字幕。同一个文件，通过 Jellyfin 播放与从 WebDAV 直接打开，走的播放路径可能不同。

| 你遇到的情况 | 建议先做的验证 |
| --- | --- |
| 第一次连接片库 | 先播一段 H.264 视频、AAC 音频的 MP4，确认连接和基础播放。 |
| MKV 通过 Jellyfin 可以播，通过 WebDAV 打不开 | 在 Jellyfin 控制台查看该会话的播放方式。服务器可以重新封装或转码；WebDAV 提供文件本身。 |
| 切换音轨或字幕后开始卡顿 | 记下轨道语言和格式。先用原音轨、关闭字幕试播，再逐项开启，对照服务器的播放信息。 |
| HDR 或 Dolby Vision 颜色异常 | 记录设备、视频编码、HDR 格式和播放路径。再播放一段已知正常的 SDR 视频作对照。 |
| 下载完成后准备离线看 | 断开网络，从下载列表试播，拖动一次时间轴并确认所需字幕。 |

重新封装可以保留原有音视频编码；转码会重新编码至少一条媒体流。实际选择取决于媒体、客户端能力和服务器设置。[Jellyfin 转码文档](https://jellyfin.org/docs/general/post-install/transcoding/)

如需[报告兼容性问题](https://github.com/P-bit-display/DuoPlayer-Community/issues/new?template=bug_report.md)，请附文件容器、视频和音频编码、字幕类型与错误提示。提供这些参数即可，无需上传整部影片。
