# AuraTunnel 隐私政策 / Privacy Policy

生效日期 / Effective date：2026-08-29  
开发者 / Developer：Shaoli Huang  
联系邮箱 / Contact：silas980729@gmail.com

## 一、适用范围与核心承诺

本政策适用于 AuraTunnel iOS App 及其 Packet Tunnel 网络扩展。

AuraTunnel 是由用户自行导入和管理代理节点、订阅与路由规则的网络隧道工具。开发者不提供、运营或控制任何代理节点或订阅服务。

**开发者不会收集、记录、出售、使用或向第三方披露任何 VPN 流量数据，包括但不限于浏览历史、DNS 查询、流量内容、源 IP 地址、目的地址和连接日志。AuraTunnel 不包含账号系统、广告、行为埋点或第三方分析 SDK。**

## 二、网络数据如何处理

当用户主动建立 VPN 连接时，iOS 会启动 AuraTunnel 的 Packet Tunnel 网络扩展。网络扩展仅为执行用户选择的路由规则而在设备内存中实时处理数据包：

- 需要代理的流量会发送到用户自行导入并选择的代理节点；
- 设为直连的流量会直接发送到对应的网站或网络服务；
- 开发者不会接收或保留上述流量；
- 网络扩展不写入逐包日志，不将流量历史上传到开发者服务器。

用户自行选择的节点运营方、网络服务商和目标网站可能在提供服务时看到网络连接所必需的信息，并按其各自的隐私政策处理数据。请只导入和使用你信任且有权使用的节点。开发者不对第三方节点的可用性、安全性或数据处理行为作出保证。

## 三、在设备上保存的数据

AuraTunnel 将下列内容保存在用户设备上，用于提供 App 功能：

- 节点和订阅的认证信息：保存在 App 与 Packet Tunnel 共享的 iOS Keychain 访问组中；
- 节点列表、订阅列表、路由规则、偏好设置和低频运行状态：保存在 App 容器或 App Group 中；
- 节点测速结果：只在本机用于界面展示，不会上传。

这些本地数据不会发送给开发者。删除 AuraTunnel 会移除 App 容器数据；iOS Keychain 项可能由系统继续保留，以支持重新安装后的安全恢复。用户可在 App 内删除节点和订阅，或在“设置”中重置相关配置。

## 四、订阅下载

只有在用户主动导入或刷新订阅时，AuraTunnel 才会直接访问用户提供的 HTTPS 订阅地址。下载使用临时 URLSession，不使用开发者中转服务器。订阅服务提供方会收到完成该请求所需的网络信息，并可能按其政策处理数据。AuraTunnel 将解析出的节点配置保存在本机，不会将订阅内容上传给开发者。

## 五、相机

只有在用户点击“扫码”后，AuraTunnel 才会说明用途并请求相机权限。相机画面只用于实时识别节点或订阅二维码：

- 不拍照；
- 不保存视频或图像；
- 不上传相机画面；
- 识别完成或用户退出时立即停止相机会话。

拒绝相机权限不会阻止用户通过剪贴板、外部链接或手动方式导入配置。

## 六、剪贴板

AuraTunnel 不会在后台或启动时读取剪贴板。只有用户点击 iOS 提供的“粘贴”按钮后，App 才会读取用户选择粘贴的文本并在导入前显示确认。用户选择“复制地址”“复制 JSON”等操作时，App 会将对应内容写入剪贴板。节点链接和备份可能包含认证信息，请勿复制或分享给不受信任的人。

## 七、配置备份与 iCloud Drive

AuraTunnel 不会自动备份或上传配置。只有用户主动选择“备份到 iCloud Drive”时，App 才会生成备份文件，并由用户通过 iOS 文件选择器决定保存位置。备份可能包含节点与订阅认证信息，应仅存放在用户控制的安全位置。iCloud Drive 由 Apple 按 Apple 的条款和隐私政策提供。

## 八、购买与付款

AuraTunnel 采用 App Store 付费下载方式，不包含订阅、消耗型项目或非消耗型 App 内购买。购买、付款、收据和退款由 Apple 处理；开发者不会从 App 内接收银行卡、支付账号或其他付款信息。

## 九、权限与系统配置

AuraTunnel 仅在用户使用对应功能时请求：

- 相机权限：扫描二维码；
- 本地网络权限：仅在用户选择或测试位于局域网内的代理节点时访问该节点；
- 系统 VPN 配置权限：在用户点击连接或准备系统 VPN 时，由 iOS 安装 Packet Tunnel 配置。

App 不请求位置、通讯录、照片、麦克风、蓝牙、健康、追踪或通知权限。VPN 配置、相机和本地网络权限均可在 iOS“设置”中管理。

## 十、数据收集、追踪与第三方 SDK

开发者不通过 AuraTunnel 收集个人数据或设备数据，不进行跨 App 或跨网站追踪，也不使用广告 SDK、分析 SDK、崩溃上报 SDK或开发者后端。项目集成的 Leaf 转发核心在 Packet Tunnel 进程内执行协议转发，不向开发者发送遥测数据。

如果未来版本的数据处理方式发生变化，开发者会在功能启用前更新 App 内披露、App Store 隐私标签和本政策，并在法律要求时取得用户同意。

## 十一、数据保留与删除

开发者没有 AuraTunnel 用户账号或服务器端用户数据库，因此没有可供开发者远程删除的 App 使用数据。用户可以：

1. 在节点库中删除单个节点或整个订阅；
2. 删除主动导出的备份文件；
3. 在 iOS 设置中移除 AuraTunnel 的 VPN 配置；
4. 删除 App 以移除其本地容器数据。

用户通过电子邮件主动提交的支持信息，仅用于回复和处理该请求，并在不再需要时删除，法律要求保留的情况除外。

## 十二、儿童隐私

AuraTunnel 不面向儿童提供账号、社交、广告或个性化服务，也不会有意收集儿童个人信息。未成年人应在监护人指导下使用网络工具和第三方代理服务。

## 十三、法律与地区可用性

用户应遵守所在国家或地区适用的法律以及所使用节点服务的条款。开发者会按照上架地区的适用要求提供必要信息，但本政策不构成任何特定地区的许可声明。

## 十四、政策更新与联系

本政策更新时会修改生效日期；重大变化会通过 App 内说明或 App Store 版本说明告知用户。如对隐私或数据处理有疑问，请发送邮件至：silas980729@gmail.com。

---

# English Privacy Policy

## 1. Scope and Core Commitment

This policy applies to the AuraTunnel iOS app and its Packet Tunnel extension.

AuraTunnel is a network tunnel utility in which users import and manage their own proxy nodes, subscriptions, and routing rules. The developer does not provide, operate, or control proxy nodes or subscription services.

**The developer does not collect, log, sell, use, or disclose any VPN traffic data to third parties for any purpose. This includes browsing history, DNS queries, traffic content, source IP addresses, destination addresses, and connection logs. AuraTunnel has no accounts, advertising, telemetry, or third-party analytics SDKs.**

## 2. Network Data Processing

When a user starts a VPN connection, iOS launches AuraTunnel's Packet Tunnel extension. The extension processes packets transiently in device memory only to apply the routing selected by the user:

- Traffic that requires a proxy is sent to the proxy node imported and selected by the user.
- Direct traffic is sent to the destination website or network service.
- The developer does not receive or retain that traffic.
- The extension does not write per-packet logs or upload traffic history.

User-selected node operators, network providers, and destination services may receive information necessary to provide their services and may process it under their own policies. Use only nodes you trust and are authorized to use. The developer does not warrant the availability, security, or privacy practices of third-party nodes.

## 3. Data Stored on the Device

AuraTunnel stores the following locally to provide app functionality:

- Node and subscription credentials in an iOS Keychain access group shared by the app and Packet Tunnel extension.
- Node lists, subscriptions, routing rules, preferences, and low-frequency runtime state in the app container or App Group.
- Node test results on the device for display in the app.

This local data is not sent to the developer. Deleting the app removes app-container data. iOS may retain Keychain items to support secure restoration after reinstallation. Users can delete nodes and subscriptions in the app.

## 4. Subscription Downloads

AuraTunnel connects directly to a user-provided HTTPS subscription URL only when the user imports or refreshes that subscription. It uses an ephemeral URLSession and no developer relay server. The subscription provider receives network information required to service the request and may process it under its own policy. Parsed node configuration remains on the device and is not uploaded to the developer.

## 5. Camera

AuraTunnel explains the purpose and requests camera access only after the user chooses Scan. Camera frames are used solely for live recognition of node or subscription QR codes. The app does not take photos, store images or video, or upload camera frames. The capture session stops after recognition or when the user exits. Denying camera access does not prevent clipboard, external-link, or manual import.

## 6. Clipboard

AuraTunnel does not read the clipboard at launch or in the background. It reads text only after the user taps the system Paste button and shows a confirmation before import. When the user chooses actions such as Copy URL or Copy JSON, the selected content is written to the clipboard. Node links and backups may contain credentials and should not be shared with untrusted parties.

## 7. Configuration Backups and iCloud Drive

AuraTunnel never backs up or uploads configuration automatically. When the user explicitly selects Back Up to iCloud Drive, the app creates a backup and the user chooses the destination through the iOS document picker. A backup may contain node and subscription credentials and should be kept only in a secure location controlled by the user. iCloud Drive is provided by Apple under Apple's terms and privacy policy.

## 8. Purchase and Payment

AuraTunnel is sold as a paid App Store download and has no subscriptions, consumable purchases, or non-consumable in-app purchases. Apple handles payment, receipts, and refunds. The developer does not receive payment-card or payment-account information through the app.

## 9. Permissions and System Configuration

AuraTunnel requests only the following when the user uses the relevant feature:

- Camera access for QR scanning.
- Local network access only when the user selects or tests a proxy node hosted on the LAN.
- System VPN configuration authorization when the user chooses to connect or explicitly prepare the Packet Tunnel configuration.

The app does not request location, contacts, photos, microphone, Bluetooth, health, tracking, or notification permission. Camera, local network, and VPN configuration can be managed in iOS Settings.

## 10. Collection, Tracking, and Third-Party SDKs

The developer does not collect personal or device data through AuraTunnel, does not track users across apps or websites, and does not use advertising, analytics, crash-reporting, or developer-backend services. The embedded Leaf forwarding core performs protocol forwarding inside the Packet Tunnel process and sends no telemetry to the developer.

If a future version changes these practices, the developer will update the in-app disclosure, App Store privacy label, and this policy before enabling the change, and will request consent when required by law.

## 11. Retention and Deletion

The developer has no AuraTunnel user account system or server-side user database. Users can delete individual nodes or subscriptions, delete exported backups, remove the AuraTunnel VPN configuration in iOS Settings, and delete the app to remove its container data.

Information voluntarily sent by email for support is used only to respond to the request and is deleted when no longer needed, unless retention is legally required.

## 12. Children

AuraTunnel does not offer accounts, social features, advertising, or personalized services to children and does not knowingly collect children's personal information. Minors should use network tools and third-party proxy services with guidance from a guardian.

## 13. Law and Regional Availability

Users are responsible for applicable local law and the terms of any node service they use. The developer will provide information required for each distribution territory, but this policy is not a claim that a license exists in any particular territory.

## 14. Changes and Contact

The effective date will change when this policy is updated. Material changes will be disclosed in the app or App Store release notes. Privacy questions may be sent to silas980729@gmail.com.
