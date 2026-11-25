# dnsfilter v1.3.0

- 新增 SNI 观测引擎（`snid`，Go 静态 arm64）：对指定 App 的 443 连接做本地透明转发，读取 TLS ClientHello 的 SNI，记录真实域名
- 覆盖 HTTPDNS / 直连 IP 的广告 SDK：DNS 看不到的域名，在 TLS 握手层仍可见
- 自动阻断目标 App 的 QUIC（UDP 443），让流量回到可识别的 TCP TLS
- 默认关闭、只观察；面板新增 SNI 页，可按域名加入拦截/放行，切换拦截模式后立即生效（新连接）
- 仍内置 241,788 条 DNS 规则，DNS 层逻辑与 v1.2.3 一致
- 升级保留 `/data/adb/dnsfilter` 下的配置、令牌、黑白名单
