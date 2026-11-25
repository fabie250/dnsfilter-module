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
