# DuoPlayer Privacy Policy · 隐私政策

Updated November 24, 2026

DuoPlayer plays media from sources you configure. The app's privacy manifest declares no tracking or collected data types. The app does not include advertising or behavioral analytics SDKs. The following features involve local storage and network requests.

| Feature | What happens |
| --- | --- |
| Connect and play | The app uses your server address and credentials to access your media. A compatible media server may receive playback progress for your account. Media servers can keep their own access logs. Local network access is used to reach devices on your network. |
| Posters and metadata | When you enable automatic matching or request a match manually, the app may send a title, year or media identifier to Douban, TMDB or your configured metadata endpoint. Poster images are requested from their hosting services. Automatic matching is off by default in a new configuration. |
| Address resolution and demo content | IPv6 lookup may send the configured hostname to a DNS-over-HTTPS provider. Demo images and video may load from external hosts. These hosts receive the network requests needed to deliver the content. |
| Purchases | The app uses Apple StoreKit to retrieve products and check purchase entitlements. |
| Data on your device | The app uses Keychain for stored media credentials. Settings, playback progress, downloaded files and cached artwork or metadata use app storage. Background audio supports continued playback when applicable. |

You can remove configured media sources, manage downloads and clear the metadata cache in the app. If you also want to revoke server access, use the account or session controls on your media server. Your server and external services apply their own retention policies.

**中文摘要**　播放时，媒体服务器会收到访问请求，也可能收到观看进度。启用自动识别或手动匹配时，片名、年份或条目标识可能发往豆瓣、TMDB 或自定义服务。海报、演示内容、域名解析和 Apple 内购也可能产生相应的网络请求。可在 App 内管理媒体源、下载和刮削缓存。

Privacy questions: support@p-bit-display.com. For general support, see the [community help page](SUPPORT.md). Avoid posting credentials or identifiable logs in public issues.
