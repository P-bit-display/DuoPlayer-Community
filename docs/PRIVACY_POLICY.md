# Privacy Policy for DuoPlayer

**Last Updated:** November 1, 2026

DuoPlayer ("we", "our", or "the App") is committed to protecting your privacy. This Privacy Policy explains our practices regarding user data, network communication, and credentials.

---

### 1. Zero Data Collection
DuoPlayer is designed with privacy at its core:
- **No Personal Data Collected:** We do not collect, track, store, or transmit any personally identifiable information (PII).
- **No Third-Party Analytics:** We do not embed any advertising SDKs, tracking pixels, or third-party behavioral analytics tools.
- **No Telemetry or Profiling:** We do not monitor your viewing history, playback habits, library contents, or file metadata.

---

### 2. Direct Network Connections
- **Direct P2P/Client-to-Server Communication:** All connections initiated by DuoPlayer occur directly between your device and your configured personal media servers (such as your self-hosted Jellyfin server or NAS WebDAV/SMB storage).
- **No Intermediary Relays:** Your media streams, requests, and authentication tokens are never routed through our servers, third-party proxies, or external cloud relays.

---

### 3. Local Credential and Data Security
- **Keychain Storage:** Account passwords and API tokens you provide are stored exclusively inside the Apple Secure Keychain (`kSecClassGenericPassword`) on your device.
- **Local Preferences:** App settings (such as playback position, subtitle preferences, and media source configurations) are saved locally on your device in standard application storage (`UserDefaults`).
- **Data Removal:** Deleting a media source or uninstalling the App immediately removes all associated credentials and cached metadata from your device.

---

### 4. System Permissions
DuoPlayer requests only the permissions necessary for its core functionality:
- **Local Network Access:** Required on iOS to discover and stream media from servers on your local Wi-Fi / home network (e.g., local Jellyfin, Synology NAS, Alist).
- **Background Audio:** Used solely to continue audio playback when you lock your screen or switch apps (if picture-in-picture / background audio is active).

---

### 5. Contact and Support
If you have questions or feedback regarding this Privacy Policy or your data privacy, you can reach us via our official GitHub repository:
- **GitHub Issues:** [https://github.com/P-bit-display/DuoPlayer/issues](https://github.com/P-bit-display/DuoPlayer/issues)
- **Email:** `support@p-bit-display.com`
