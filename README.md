  # Tenga Proxy Mobile (Wingeon)

  An Android app for managing VPN connections. Powered by [xray-core](https://github.com/XTLS/Xray-core).

  ## Download

  Download the latest APK from the [Releases](https://github.com/vebulogmetra/tenga-proxy-mobile/releases) section.

  ## Supported Protocols

  - **VLESS** — including Reality and XTLS
  - **Trojan** — with TLS
  - **HTTP/HTTPS** — HTTP proxy
  - **Shadowsocks** — experimental (share-link parsing only)

  ## Features

  - **Profile Import**:
    - Share link parsing (`vless://`, `trojan://`, `ss://`, `http://`, `https://`)
    - QR code scanning
    - Paste from clipboard
    - Import from xray/v2ray JSON configuration
    - Subscription support with automatic updates

  - **Routing Settings**:
    - Customizable routing rules
    - Per-app proxy (include / exclude modes)
    - Route exclusions by IPv4/IPv6 CIDR

  - **DNS Settings**:
    - Separate DNS servers for proxy and direct traffic
    - Domain resolution strategy (IPv4 / IPv6 / mixed)
    - DNS-level domain blocking

  - **Failover** — manual switch to a backup profile when the current one is unreachable

  - **Profile Management**:
    - Groups and ordering
    - Latency probing (TCP / through-proxy HTTP)
    - Bulk validation of subscription updates

  ## Requirements

  - Android 7.0 (API 24) or higher
  - Architecture: arm64-v8a
