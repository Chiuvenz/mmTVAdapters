# mmTVAdapters 状态

更新日期：2026-10-28。

## 角色

本仓只放**第三方独立 macOS App 适配器**。 [mmTV](https://github.com/Chiuvenz/mmTV) 按 Bundle ID 检测并启动；物理遥控在 [mmTV Remote](https://github.com/Chiuvenz/mmTVRemote)。不嵌入 `com.mmtv.mac`。

边界说明亦见 mmTV 仓内 `Integrations/README.md` 指针。

## 当前适配器

| 适配器 | Bundle ID | 版本／产物 | 上游 |
|---|---|---|---|
| BiliTVMac | `com.mmtv.bilitv` | 0.1.0 arm64（Electron） | [bili-webos](https://github.com/asdf17128/bili-webos) v2.5.1 |

启动契约：mmTV 传入 `--tv-fullscreen`；状态目录在适配器私有 Application Support。

## 已完成

- 自 mmTV `Integrations/BiliTV*` 与 `Scripts/*-bilitv.sh` 迁入（`git filter-repo` 保留历史）；`main` 合并 PR #1。
- fetch／build／smoke 脚本可用；`MMTV_SKIP_BILITV_SMOKE=1` 支持无图形会话打包。
- Mac mini 上曾安装 `/Applications/BiliTVMac.app`；mmTV 候选入口 download 指向本仓。

## 仍待人工／后续

- 客厅电视：从 mmTV「看点什么」全屏启动、二维码登录与账号持久化、可听音频、Remote 在 `com.mmtv.bilitv` 前台手感。
- 烟测在无 GUI／无显示会话下的稳定性。
- 未来其他第三方适配器按同模式新增目录，不进 mmTV 源码树。

## 构建速查

```sh
./Scripts/build-bilitv.sh
# or: MMTV_SKIP_BILITV_SMOKE=1 ./Scripts/build-bilitv.sh
```

详见根目录 [README.md](../README.md)。
