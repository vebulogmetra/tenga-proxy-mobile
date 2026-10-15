# Tenga Proxy Mobile (Wingeon)

An Android VPN client powered by [xray-core](https://github.com/XTLS/Xray-core) via [libXray](https://github.com/XTLS/libXray), plus a WDTT tunnel core that reaches a node through the TURN relays of VK calls. Kotlin + Jetpack Compose.

## Download

Download the latest APK from the [Releases](https://github.com/vebulogmetra/tenga-proxy-mobile/releases) section.

## Supported Protocols

- **VLESS** — TLS, Reality, XTLS Vision; transports: tcp, ws, h2, grpc, httpupgrade, xhttp
- **Trojan** — TLS, Reality; transports: tcp, ws, h2, grpc, httpupgrade
- **Hysteria2** — QUIC, including finalmask obfuscation, port hopping, obfs salamander and brutal
- **Shadowsocks** — AEAD and 2022 (blake3) ciphers; stream ciphers and SIP003 plugins are not supported
- **HTTP/HTTPS** — HTTP proxy with authentication
- **WDTT** — a tunnel to a node through the TURN relays of VK calls (`wingeon://connect?…` links issued by the panel)

VMess and SOCKS are not supported.

## Features

- **Profile Import**:
  - Share link parsing (`vless://`, `trojan://`, `hysteria2://`, `hy2://`, `ss://`, `http://`, `https://`, `wingeon://connect`)
  - QR code scanning
  - Paste from clipboard
  - Import from xray/v2ray JSON configuration
  - Links are validated before a profile is saved

- **Subscriptions**:
  - Traffic quota and expiry from `subscription-userinfo`, provider name and metadata, renew link
  - Base64 link lists and xray JSON configs as a fallback format
  - Fetched through the tunnel while the VPN is on, falling back to a direct request
  - Availability check of subscription servers from the group menu

- **WDTT tunnel**:
  - Tunnel settings: number of streams, transport to VK servers (auto / UDP / TCP), readiness condition
  - Live status on the main screen: streams, transport, pending VK confirmation
  - VK captcha in an in-app window; VK access is kept between connections to ask for it less often

- **Routing Settings**:
  - Proxy / direct / block rule lists by domain, IP and geo categories
  - Optional "Russian IPs direct" bypass
  - Per-app proxy with a preset of VPN-aware apps, excluded networks
  - Downloadable geo databases (signed manifest), import of Happ routing profiles
  - QUIC sniffing so domain rules apply to HTTP/3 traffic

- **DNS**:
  - Remote DNS by IP or DoH URL (DoH by default); app DNS is intercepted inside xray
  - Direct domains are resolved by the system resolver, so the client works on networks with DNS allow-lists
  - DNS-level domain blocking

- **Censorship circumvention**: TLS fragmentation (global and per profile), mux for VLESS and Trojan

- **Failover**:
  - Automatic switch to a working profile when the current one fails its probe
  - Manual switch from the status pill

- **Profile Management**:
  - Groups with drag-and-drop ordering, search and availability filters
  - Hot profile switch without dropping the tunnel
  - Group ping with live results (TCP / through-proxy HTTP response time)

- **Always-on and autostart**: connection restore for always-on VPN and after reboot; Quick Settings tile and launcher shortcut

- **Traffic statistics** in real time, with a configurable display mode

- **Diagnostics**: log viewer and sharing with sensitive data scrubbed, xray-core update check

- **Security**: encrypted local profile database (SQLCipher), one-time credentials for local xray inbounds, secrets masked in logs

## Requirements

- Android 7.0 (API 24) or higher
- Architecture: arm64-v8a
