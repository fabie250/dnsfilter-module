# dnsfilter v1.3.0

> ⚠️ **此版本存在已知问题，已被标记为不建议使用的版本**：建议继续使用 v1.2.3，等待修复版本发布。

- 新增 SNI 观测引擎（`snid`，Go 静态 arm64）：对指定 App 的 443 连接做本地透明转发，读取 TLS ClientHello 的 SNI，记录真实域名
- 覆盖 HTTPDNS / 直连 IP 的广告 SDK：DNS 看不到的域名，在 TLS 握手层仍可见
- 自动阻断目标 App 的 QUIC（UDP 443），让流量回到可识别的 TCP TLS
- 默认关闭、只观察；面板新增 SNI 页，可按域名加入拦截/放行，切换拦截模式后立即生效（新连接）
- 仍内置 241,788 条 DNS 规则，DNS 层逻辑与 v1.2.3 一致
- 升级保留 `/data/adb/dnsfilter` 下的配置、令牌、黑白名单

# dnsfilter v1.2.3

- 内置 241,788 条拦截规则（离线可用），修复规则只有 377 条导致拦截率接近 0 的问题
- 修复「启动」按钮：优先用 `/system/bin/paneld`，失败则复制到 `/data/local/tmp` 执行，避免 SELinux 拒绝执行模块目录二进制
- 面板与模块版本同步为 v1.2.3
- 安装时若新规则更大，自动替换 `base.txt` / `cn-ads.txt` 并备份为 `.bak`

# dnsfilter v1.2.2

- 新增 `updateJson`：SukiSU / KernelSU 模块列表可直接检查更新并下载
- 「启动」按钮与 `<>` WebUI 均打开新版面板（8098 本地静态页）
- 面板版本与模块版本同步为 v1.2.2，作者 fabie
- 引擎沿用 v1.2.1 的 arm64 二进制，行为不变
