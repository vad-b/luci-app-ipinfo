<div align="center">
  <h1>LuCI support for ip.guide</h1>
  <h3>Shows public ip information in Overview LuCI with ip.guide</h3>
</div>
<hr/>

## About This Fork

This fork is functionally based on [animegasan/luci-app-ipinfo](https://github.com/animegasan/luci-app-ipinfo). The main goal is compatibility with current and newer OpenWrt releases, including the 25.x+ series:

- builds both package formats: `.ipk` for `opkg`-based OpenWrt releases and `.apk` for `apk`-based OpenWrt 25.x+ releases
- includes an installer that auto-detects `opkg` / `apk`, downloads the matching latest release asset, and installs it
- uses `wget` for installation instead of `curl`, since `wget` is much more likely to be available on a base OpenWrt system
- removes the preliminary Google connectivity check before querying `ip.guide`, because Google can be blocked or unreachable while the actual IP lookup still works
- handles `null` or missing nested JSON fields correctly, so absent values such as city, country, or provider details do not break rendering

## Quick Install

Auto-detects `opkg` / `apk` and installs the matching latest release package (`.ipk` or `.apk`):

```
wget -qO- https://raw.githubusercontent.com/vad-b/luci-app-ipinfo/main/install.sh | sh
```

# Preview
![image](https://github.com/user-attachments/assets/eed6bdf9-8e03-44d9-ad1b-71b411257888)
![image](https://github.com/animegasan/luci-app-ipinfo/assets/14136053/f1970b49-2460-4602-8cdf-299bcea282c9)
