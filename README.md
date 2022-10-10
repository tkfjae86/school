# Incognito Proxy 

Incognito mode is nice, but your ISP sees the traffic.  VPNs are pretty neat, but you'll solve CAPTCHAs all day.  Why not have both, with an incognito-only VPN?

The requirements are a SOCKS5 proxy server and a secure tunnel, such as WireGuard with `allowed-ips w.x.y.z/32` (IP address of the proxy) or `ssh -D1080`.  There are commercial VPN providers with WireGuard and SOCKS5, or you could self-host. The **Incognito&nbsp;Proxy** extension solves the sub-problem of "How do I configure a SOCKS5 proxy specifically for Incognito tabs?"

More generally, **this extension configures proxy settings**. It has few features, but its namesake feature is the ability to configure *different* proxy/direct settings for regular windows and incognito windows.

I've tested the "Incognito to SOCKS5 over WireGuard" config on a Chromebook; it is unobtrusive, survives rebooting, and I can still LAN print. Annoyingly, Chrome's WireGuard config forced me to pick a static DNS server; `0.0.0.0` worked at first, but not reliably.

Chrome OS supports IPv6-over-SOCKS5 (but not IPv6-over-WireGuard, sigh), so SOCKS5 could let you reach IPv6-only servers from anywhere.

## Note to other extension developers

Please steal my code, because 'incognito proxy' is a good feature. I copied it from [chrome-extensions-samples](https://github.com/GoogleChrome/chrome-extensions-samples/tree/475b4b6bf1a376e0cb0de715652a46a458b5fe72/mv2-archive/extensions/proxy_configuration) and made minor improvements.

## Chrome installer

https://chrome.google.com/webstore/detail/incognito-proxy/odkbcffeaickjalieahlneeehkgjpade

## Screenshot

![Screenshot](misc/screenshot1.png)
