# mmTVAdapters 路线

本仓不做客厅壳或物理遥控；只交付可独立安装的第三方适配 App。

## 已交付

- **BiliTVMac 0.1.x**：上游拉取、Electron 运行时、全屏启动参数、与 mmTV Bundle ID 契约。

## 下一步

1. 电视实机：登录持久化、音频、与 mmTV Remote Profile 联调。
2. 按需加固 smoke（有／无图形会话）。
3. 下一款适配器仅在真实客厅需求出现后新增（同 Bundle ID + 独立 App 模式）。

## 不做

- 嵌入 mmTV 进程或 WebView 冒充集成。
- 通用插件市场、动态下载未审计二进制绕过 Gatekeeper。
- 替代 mmTV Remote 的 HID／Profile 职责。
