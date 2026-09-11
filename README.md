# Tenga Proxy Mobile (Wingeon)

An Android VPN client powered by [xray-core](https://github.com/XTLS/Xray-core) via [libXray](https://github.com/XTLS/libXray). Kotlin + Jetpack Compose.

## Download

Download the latest APK from the [Releases](https://github.com/vebulogmetra/tenga-proxy-mobile/releases) section.

## Supported Protocols

- **VLESS** — TLS, Reality, XTLS Vision; transports: tcp, ws, h2, grpc, httpupgrade, xhttp
- **Trojan** — TLS, Reality; transports: tcp, ws, h2, grpc, httpupgrade
- **Hysteria2** — QUIC, including finalmask obfuscation
- **HTTP/HTTPS** — HTTP proxy with authentication

`ss://` links are recognized on import, but Shadowsocks profiles are not supported by the engine yet and are marked as unavailable. VMess and SOCKS are not supported.

## Features

- **Profile Import**:
  - Share link parsing (`vless://`, `trojan://`, `hysteria2://`, `hy2://`, `http://`, `https://`)
  - QR code scanning
  - Paste from clipboard
  - Import from xray/v2ray JSON configuration

- **Subscriptions**:
  - Automatic updates, traffic quota and expiry from `subscription-userinfo`
  - Base64 link lists and xray JSON configs as a fallback format
  - Bulk availability validation of subscription servers

- **Routing Settings**:
  - Proxy / direct / block rule lists by domain and IP
  - Optional "Russian IPs direct" bypass
  - Per-app proxy (include / exclude modes)
  - QUIC sniffing so domain rules apply to HTTP/3 traffic

- **DNS Settings**:
  - Separate DNS servers for proxy and direct traffic
  - Domain resolution strategy (IPv4 / IPv6 / mixed)
  - DNS-level domain blocking

- **Failover**:
  - Automatic switch to a working profile when the current one fails its probe
  - Manual switch from the status pill

- **Profile Management**:
  - Groups, search and availability filters
  - Hot profile switch without dropping the tunnel
  - Latency probing (TCP / through-proxy HTTP response time)

- **Traffic statistics** in real time, with a configurable display mode

- **Security**: encrypted local profile database (SQLCipher), secrets masked in logs

## Requirements

- Android 7.0 (API 24) or higher
- Architecture: arm64-v8a
