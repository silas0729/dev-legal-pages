# AuraTunnel 技术支持 / Support

最后更新 / Last updated：2026-08-29  
支持邮箱 / Support email：silas980729@gmail.com

## 产品说明

AuraTunnel 是一个 iOS Packet Tunnel 客户端。用户需要导入自己有权使用的代理节点或 HTTPS 订阅。AuraTunnel 不销售、不赠送，也不运营 VPN 节点或订阅服务。

AuraTunnel 采用 App Store 付费下载方式，App 内没有订阅、消耗型或非消耗型购买项目。

## 系统要求

- iOS 16.0 或更高版本；
- 支持安装 Network Extension 的 iPhone 或 iPad；
- 有效的用户自有节点或 HTTPS 订阅；
- 连接时可用的 Wi-Fi 或蜂窝网络。

## 首次使用

1. 打开 App，阅读“VPN 数据与隐私说明”，可先切换中文或英文。
2. 在“节点库”中选择“扫码”或系统“粘贴”按钮，导入节点或订阅。
3. 在导入确认页核对来源和数量。
4. 在“连接”页选择一个节点和路由模式。
5. 点击“建立安全通道”。首次连接时 iOS 会询问是否允许添加 VPN 配置。
6. iOS 状态变为“已连接”后，再测试网站或 App。

不需要通过 TestFlight 才能安装 VPN 配置。使用正确签名和 Network Extension entitlement 的 Xcode 真机安装、TestFlight 和 App Store 版本，都可以在用户首次主动连接时由 iOS 安装系统 VPN 配置。

## 权限说明

### 系统 VPN 配置

只有在用户点击连接或明确准备系统 VPN 时，AuraTunnel 才会调用 iOS 保存 Packet Tunnel 配置。拒绝后可稍后再次点击连接；导入的节点不会因此消失。

### 相机

只有点击“扫码”后才会出现用途说明，继续后 iOS 才会请求相机权限。画面只用于实时二维码识别，不保存或上传。拒绝相机权限后仍可通过系统“粘贴”按钮或手动导入。

### 剪贴板

AuraTunnel 不会在启动时或后台读取剪贴板。只有点击 iOS“粘贴”按钮后才读取文本，并在导入前再次确认。

### 本地网络

只有当用户选择或测试位于局域网内的节点时，iOS 才可能请求本地网络权限。使用公网节点不需要 AuraTunnel 扫描局域网；App 也不使用 Bonjour 搜索设备。

## 支持的导入格式

- Shadowsocks (`ss://`)
- SOCKS5 (`socks5://`)
- VMess (`vmess://`)
- VLESS (`vless://`)
- Trojan (`trojan://`)
- Hysteria 2 (`hysteria2://` 或 `hy2://`，是否可连接取决于当前转发核心能力)
- HTTPS 订阅包装格式 (`sub://`)

节点和订阅包含认证信息。请勿将二维码、完整 URL、JSON 或配置备份发送给不受信任的人。

## 路由模式

- 智能分流：中国大陆常用域名直连，其他流量使用所选代理；
- 规则配置：使用用户保存的代理和直连域名规则；
- 全局代理：除隧道建立和必要系统旁路外，流量使用所选代理；
- 全部直连：流量不经过代理节点；
- 场景模式：常用境外社交和流媒体使用代理，其余流量直连。

切换路由模式时，正在运行的隧道会安全重启以应用规则。

## 常见问题

### 导入订阅提示离线

首次允许网络访问或刚切换 Wi-Fi/蜂窝网络时，系统路径可能尚未就绪。保持 App 在前台并重试。AuraTunnel 的临时 URLSession 会等待短暂的网络路径切换，但订阅服务器不可达、证书无效或地址过期仍会失败。

### 节点已导入但无法连接

1. 在节点菜单中运行“测试”；
2. 核对服务器、端口、UUID/密码、TLS、Host、Path 和传输方式；
3. 确认节点协议受当前版本支持；
4. 切换 Wi-Fi/蜂窝网络；
5. 打开“活动”页查看 Packet Tunnel 诊断；
6. 联系节点提供方确认服务器是否可用。

### 连接超时

在“设置 > 连接提醒”中可选择 10、15、20 或 30 秒等待上限，并可分别关闭连接失败提醒和意外断开提醒。提醒只由系统连接状态变化触发，不会在后台轮询。

### 已连接但网页无法打开

- 先切换“全局代理”确认节点是否具备完整 TCP、UDP 和 DNS 能力；
- 若全局代理仍失败，通常是节点服务端、TLS/传输参数、UDP/DNS 能力或当前网络的问题；
- 若只有智能/规则模式失败，恢复默认规则并检查直连域名、代理域名和 DNS 设置；
- TikTok、视频、评论和图片加载还依赖节点地区、带宽、UDP、IPv6、DNS 与服务端策略，节点测速可达不代表全部业务可用。

### 如何删除本机数据

- 长按节点或订阅并选择“删除”；
- 删除手动导出的 `.aurabackup` 文件；
- 在 iOS“设置 > VPN”中移除 AuraTunnel 配置；
- 删除 App 以移除 App 容器数据。

## 配置备份

“设置 > iCloud 与配置文件 > 备份到 iCloud Drive”会创建包含节点、订阅、规则和当前选择的备份文件。AuraTunnel 不会自动上传。备份含认证信息，只应保存到用户控制的位置。恢复前必须断开 VPN。

## 隐私与安全

AuraTunnel 的开发者不收集、记录、出售、使用或向第三方披露 VPN 流量数据。详细内容请参阅 AuraTunnel 隐私政策。报告安全问题时，请勿在邮件中直接附上真实节点密码、完整订阅 URL 或含凭据的备份。

## 联系支持

邮件：silas980729@gmail.com

为便于排查，请提供：

- AuraTunnel 版本和 Build；
- iOS 版本与设备型号；
- 使用的协议类型（不要提供密码或完整 URL）；
- 路由模式；
- “活动”页可公开的错误文字；
- 问题发生步骤。

开发者会在合理时间内尽快回复。节点账号、节点退款、服务器封锁或订阅内容问题应联系对应节点提供方。

---

# English Support

AuraTunnel is an iOS Packet Tunnel client. You must import a proxy node or HTTPS subscription that you are authorized to use. AuraTunnel does not sell, provide, or operate VPN nodes or subscription services. It is a paid App Store download with no in-app subscriptions or purchases.

## Getting Started

1. Read the VPN Data & Privacy Disclosure and choose Chinese or English.
2. Open Nodes and import using Scan or the system Paste button.
3. Review the source and node count before confirming.
4. Select a node and routing mode on Connect.
5. Tap Connect Secure Tunnel. iOS asks to add the VPN configuration on first use.
6. Wait for the system status to become Connected before testing another app.

TestFlight is not required for VPN configuration. A correctly signed on-device Xcode build, TestFlight build, or App Store build can ask iOS to install the configuration when the user explicitly connects.

## Permissions

- VPN configuration is requested only after an explicit connect or prepare action. Declining does not delete imported nodes.
- Camera access is requested only after Scan and an explanatory screen. Frames are not stored or uploaded.
- Clipboard is never read at launch or in the background. It is read only after the user taps the system Paste button.
- Local network access is used only when the user selects or tests a proxy node hosted on the LAN. AuraTunnel does not use Bonjour to discover devices.

## Troubleshooting

- For an offline subscription error after first launch or a network switch, keep the app foregrounded and retry after the path is ready.
- If a node cannot connect, test it, verify protocol and TLS/transport fields, change networks, review Activity diagnostics, and contact the node provider.
- Connection timeout can be set to 10, 15, 20, or 30 seconds under Settings > Connection Alerts. Failure and unexpected-disconnect alerts can be disabled independently.
- If Connected does not provide internet access, test Global Proxy first. Failures there usually indicate a node, server transport, DNS, UDP, IPv6, or current-network problem. Smart/Rules-only failures usually indicate routing or DNS rules.
- Reachability latency does not guarantee that streaming, comments, media images, UDP, or region-restricted services will work.

## Backup and Deletion

Settings > iCloud & Configuration Files exports a user-controlled backup containing nodes, subscriptions, rules, and credentials. AuraTunnel never uploads it automatically. Disconnect VPN before restoring.

Delete nodes or subscriptions in Nodes, delete exported backup files, remove the AuraTunnel VPN configuration in iOS Settings, and delete the app to remove its container data.

## Privacy and Contact

The developer does not collect, log, sell, use, or disclose VPN traffic data. Never email real node passwords, full subscription URLs, or credential-bearing backups.

Support email: silas980729@gmail.com  
Please include the app version/build, iOS version/device, protocol type without credentials, routing mode, public error text from Activity, and reproduction steps. The developer will respond as soon as reasonably possible.
