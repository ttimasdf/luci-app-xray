[![Build Packages](https://github.com/ttimasdf/luci-app-xray/actions/workflows/build.yml/badge.svg?branch=custom)](https://github.com/ttimasdf/luci-app-xray/actions/workflows/build.yml)

# luci-app-xray

Yet Another LuCI frontend for Xray. An *opinionated* forked version of [yichya/luci-app-xray](https://github.com/yichya/luci-app-xray) with lots of quality of life improvements.

This project will *never* provide updates through an opkg feed. It's easy though, but adding a custom feed from untrusted source (anywhere, even me!) is a huge security flaw. Manual installation with `opkg` or pack the ipk into the firmware image with OpenWrt imagebuilder is recommanded.

| OpenWrt Version |     compatible?     |
| :---------------: | :--------------------: |
|      22.03      |          ✅          |
|      21.02      | ✅(Not fully tested) |
|     ≤19.07     |    ⚠️(Untested)    |

# Features

- Proxy server management.
- Separate upstream proxies for TCP and UDP.
- Transparent proxy through nftables (>=22.03) or iptables (<=21.02)
- Proxy rules config by whitelist/blacklist.
- Xray [confdir support](https://xtls.github.io/config/features/multiple.html), allowing maximum flexibility.
- Using Xray as a HTTPS reverse proxy.
- ulimit configuration (file descriptors, memory usage) for Xray process.
- Configuration option to bypass proxy for network traffic from intranet hosts by host MAC address.
- Configuration option to bypass proxy for network traffic from router processes by UID and GID.
- Optional dnsmasq takeover, which automatically setting xray DNS inbound as dnsmasq upstream.
