# 🦞 OpenClaw — 个人AI助手

> 💡 **协作邀请**  
> 目前我正在深入研究 **MolBot（ClawBot）** 的架构，致力于优化其对国产环境的支持。当前版本主要适配国际主流工具，在微信、钉钉、QQ 等国内平台的兼容性上仍有不足。  
> 同时对使用deepseek等国内API的朋友们来说不太友好！
> 我的目标是打造一个**全面适配国产生态**的 Bot 框架，真正实现「开箱即用」！
> 将会持续开展研发**并承诺完全开源免费，不引入商业化！**
>  
> 🤝 **诚邀伙伴加入共建！**  
> 如果你对该项目感兴趣，欢迎扫码加入我们的 QQ 群，一起交流、开发、完善 MolBot！  
>   
> <img width="321" height="339" alt="QQ_1769606675643" src="https://github.com/user-attachments/assets/1b0c9992-1104-4626-ace8-f8b29c21773f" />

> ### Todo List
> - [ ] 1. 接入 QQ API
> - [ ] 2. 完成汉化脚本：翻译 UI 和各种平台 APP 源码中硬编码的英文单词
> - [ ] 3. 接入钉钉 API
> - [ ] 4. 接入微信 API
> - [ ] 5. 整合飞书 API

<p align="center">
    <picture>
        <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/openclaw/openclaw/main/docs/assets/openclaw-logo-text-dark.png">
        <img src="https://raw.githubusercontent.com/openclaw/openclaw/main/docs/assets/openclaw-logo-text.png" alt="OpenClaw" width="500">
    </picture>
</p>

<p align="center">
  <strong>去角质！去角质！</strong>
</p>

<p align="center">
  <a href="https://github.com/openclaw/openclaw/actions/workflows/ci.yml?branch=main"><img src="https://img.shields.io/github/actions/workflow/status/openclaw/openclaw/ci.yml?branch=main&style=for-the-badge" alt="CI 状态"></a>
  <a href="https://github.com/openclaw/openclaw/releases"><img src="https://img.shields.io/github/v/release/openclaw/openclaw?include_prereleases&style=for-the-badge" alt="GitHub 发布版本"></a>
  <a href="https://discord.gg/clawd"><img src="https://img.shields.io/discord/1456350064065904867?label=Discord&logo=discord&logoColor=white&color=5865F2&style=for-the-badge" alt="Discord"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge" alt="MIT 许可证"></a>
</p>

**OpenClaw** 是一个你可以在自己的设备上运行的*个人AI助手*。
它会在你已经使用的渠道（WhatsApp、Telegram、Slack、Discord、Google Chat、Signal、iMessage、Microsoft Teams、WebChat）上回复你，并且支持扩展渠道如BlueBubbles、Matrix、Zalo和Zalo Personal。它可以在macOS/iOS/Android上进行语音识别和语音合成，并可以渲染一个你可以控制的实时画布。网关只是一个控制平面——产品是助手。

如果你想要一个个人的、单用户的助手，感觉就像本地运行一样，快速且总是在线，这就是它。

[网站](https://openclaw.ai) · [文档](https://docs.openclaw.ai) · [DeepWiki](https://deepwiki.com/openclaw/openclaw) · [开始使用](https://docs.openclaw.ai/start/getting-started) · [更新](https://docs.openclaw.ai/install/updating) · [展示](https://docs.openclaw.ai/start/showcase) · [常见问题](https://docs.openclaw.ai/start/faq) · [向导](https://docs.openclaw.ai/start/wizard) · [Nix](https://github.com/openclaw/nix-clawdbot) · [Docker](https://docs.openclaw.ai/install/docker) · [Discord](https://discord.gg/clawd)

推荐设置：运行入站向导 (`openclaw onboard`)。它会引导你完成网关、工作区、渠道和技能的设置。CLI 向导是推荐的方式，并且适用于**macOS、Linux 和 Windows（通过 WSL2；强烈推荐）**。
支持 npm、pnpm 或 bun。
新安装？从这里开始：[开始使用](https://docs.openclaw.ai/start/getting-started)

**订阅（OAuth）：**
- **[Anthropic](https://www.anthropic.com/)** (Claude Pro/Max)
- **[OpenAI](https://openai.com/)** (ChatGPT/Codex)

模型说明：虽然支持任何模型，但我强烈推荐**Anthropic Pro/Max (100/200) + Opus 4.5**以获得更好的长上下文处理能力和更好的提示注入抵抗能力。详见[入站设置](https://docs.openclaw.ai/start/onboarding)。

## 模型（选择 + 认证）

- 模型配置 + CLI: [模型](https://docs.openclaw.ai/concepts/models)
- 认证配置轮换（OAuth vs API 密钥）+ 备用方案: [模型故障转移](https://docs.openclaw.ai/concepts/model-failover)

## 安装（推荐）

运行时环境：**Node ≥22**。

```bash
npm install -g openclaw@latest
# 或者: pnpm add -g openclaw@latest

openclaw onboard --install-daemon
```

向导会安装网关守护进程（launchd/systemd 用户服务），使其保持运行。

## 快速开始（简要说明）

运行时环境：**Node ≥22**。

完整初学者指南（认证、配对、渠道）：[开始使用](https://docs.openclaw.ai/start/getting-started)

```bash
openclaw onboard --install-daemon

openclaw gateway --port 18789 --verbose

# 发送消息
openclaw message send --to +1234567890 --message "来自 OpenClaw 的问候"

# 与助手对话（可选：将回复发送到任何已连接的渠道：WhatsApp/Telegram/Slack/Discord/Google Chat/Signal/iMessage/BlueBubbles/Microsoft Teams/Matrix/Zalo/Zalo Personal/WebChat）
openclaw agent --message "航行检查清单" --thinking high
```

升级？请参阅[升级指南](https://docs.openclaw.ai/install/updating)（并运行 `openclaw doctor`）。

## 开发渠道

- **stable**: 标签版本 (`vYYYY.M.D` 或 `vYYYY.M.D-<patch>`)，npm 发行标签 `latest`。
- **beta**: 预发布标签 (`vYYYY.M.D-beta.N`)，npm 发行标签 `beta`（macOS 应用可能缺失）。
- **dev**: 主分支的最新提交，npm 发行标签 `dev`（当发布时）。

切换渠道（git + npm）：`openclaw update --channel stable|beta|dev`。
详情：[开发渠道](https://docs.openclaw.ai/install/development-channels)。

## 从源代码安装（开发）

建议使用 `pnpm` 进行源代码构建。Bun 可选，用于直接运行 TypeScript。

```bash
git clone https://github.com/openclaw/openclaw.git
cd openclaw

pnpm install
pnpm ui:build # 第一次运行时自动安装 UI 依赖
pnpm build

pnpm openclaw onboard --install-daemon

# 开发循环（TypeScript 更改时自动重新加载）
pnpm gateway:watch
```

注意：`pnpm openclaw ...` 直接运行 TypeScript（通过 `tsx`）。`pnpm build` 生成 `dist/` 以便通过 Node 或打包后的 `openclaw` 二进制文件运行。

## 安全默认设置（私信访问）

OpenClaw 连接到真实的通信平台。将传入的私信视为**不受信任的输入**。

完整安全指南：[安全](https://docs.openclaw.ai/gateway/security)

Telegram/WhatsApp/Signal/iMessage/Microsoft Teams/Discord/Google Chat/Slack 上的默认行为：
- **私信配对** (`dmPolicy="pairing"` / `channels.discord.dm.policy="pairing"` / `channels.slack.dm.policy="pairing"`): 未知发送者会收到一个短配对码，机器人不会处理他们的消息。
- 批准方式：`openclaw pairing approve <渠道> <代码>`（然后发送者会被添加到本地允许列表存储中）。
- 公开传入的私信需要显式同意：设置 `dmPolicy="open"` 并在渠道允许列表中包含 `"*"` (`allowFrom` / `channels.discord.dm.allowFrom` / `channels.slack.dm.allowFrom`)。

运行 `openclaw doctor` 以显示有风险或配置错误的私信策略。

## 突出特点

- **[本地优先网关](https://docs.openclaw.ai/gateway)** — 会话、渠道、工具和事件的单一控制平面。
- **[多渠道收件箱](https://docs.openclaw.ai/channels)** — WhatsApp、Telegram、Slack、Discord、Google Chat、Signal、iMessage、BlueBubbles、Microsoft Teams、Matrix、Zalo、Zalo Personal、WebChat、macOS、iOS/Android。
- **[多代理路由](https://docs.openclaw.ai/gateway/configuration)** — 将传入的渠道/账户/对等点路由到隔离的代理（工作区 + 每个代理的会话）。
- **[语音唤醒](https://docs.openclaw.ai/nodes/voicewake) + [对话模式](https://docs.openclaw.ai/nodes/talk)** — 在 macOS/iOS/Android 上持续的语音支持，使用 ElevenLabs。
- **[实时画布](https://docs.openclaw.ai/platforms/mac/canvas)** — 代理驱动的视觉工作区，使用 [A2UI](https://docs.openclaw.ai/platforms/mac/canvas#canvas-a2ui)。
- **[一等工具](https://docs.openclaw.ai/tools)** — 浏览器、画布、节点、cron、会话和 Discord/Slack 动作。
- **[配套应用](https://docs.openclaw.ai/platforms/macos)** — macOS 菜单栏应用 + iOS/Android [节点](https://docs.openclaw.ai/nodes)。
- **[入站设置](https://docs.openclaw.ai/start/wizard) + [技能](https://docs.openclaw.ai/tools/skills)** — 向导驱动的设置，带有捆绑/管理/工作区技能。

## 星星历史

[![星星历史图](https://api.star-history.com/svg?repos=openclaw/openclaw&type=date&legend=top-left)](https://www.star-history.com/#openclaw/openclaw&type=date&legend=top-left)

## 我们迄今为止构建的一切

### 核心平台
- [网关 WS 控制平面](https://docs.openclaw.ai/gateway)，包括会话、在线状态、配置、cron、Webhook、[控制界面](https://docs.openclaw.ai/web) 和 [画布主机](https://docs.openclaw.ai/platforms/mac/canvas#canvas-a2ui)。
- [CLI 表面](https://docs.openclaw.ai/tools/agent-send)：网关、代理、发送、[向导](https://docs.openclaw.ai/start/wizard) 和 [医生](https://docs.openclaw.ai/gateway/doctor)。
- [Pi 代理运行时](https://docs.openclaw.ai/concepts/agent) 在 RPC 模式下，带有工具流和块流。
- [会话模型](https://docs.openclaw.ai/concepts/session)：`main` 用于直接聊天，群组隔离，激活模式，队列模式，回复。群组规则：[群组](https://docs.openclaw.ai/concepts/groups)。
- [媒体管道](https://docs.openclaw.ai/nodes/images)：图像/音频/视频，转录钩子，大小限制，临时文件生命周期。音频详情：[音频](https://docs.openclaw.ai/nodes/audio)。

### 渠道
- [渠道](https://docs.openclaw.ai/channels)：[WhatsApp](https://docs.openclaw.ai/channels/whatsapp) (Baileys)，[Telegram](https://docs.openclaw.ai/channels/telegram) (grammY)，[Slack](https://docs.openclaw.ai/channels/slack) (Bolt)，[Discord](https://docs.openclaw.ai/channels/discord) (discord.js)，[Google Chat](https://docs.openclaw.ai/channels/googlechat) (Chat API)，[Signal](https://docs.openclaw.ai/channels/signal) (signal-cli)，[iMessage](https://docs.openclaw.ai/channels/imessage) (imsg)，[BlueBubbles](https://docs.openclaw.ai/channels/bluebubbles) (扩展)，[Microsoft Teams](https://docs.openclaw.ai/channels/msteams) (扩展)，[Matrix](https://docs.openclaw.ai/channels/matrix) (扩展)，[Zalo](https://docs.openclaw.ai/channels/zalo) (扩展)，[Zalo Personal](https://docs.openclaw.ai/channels/zalouser) (扩展)，[WebChat](https://docs.openclaw.ai/web/webchat)。
- [群组路由](https://docs.openclaw.ai/concepts/group-messages)：提及门控，回复标签，每个渠道分块和路由。渠道规则：[渠道](https://docs.openclaw.ai/channels)。

### 应用程序 + 节点
- [macOS 应用](https://docs.openclaw.ai/platforms/macos)：菜单栏控制平面，[语音唤醒](https://docs.openclaw.ai/nodes/voicewake)/PTT，[对话模式](https://docs.openclaw.ai/nodes/talk) 覆盖层，[WebChat](https://docs.openclaw.ai/web/webchat)，调试工具，[远程网关](https://docs.openclaw.ai/gateway/remote) 控制。
- [iOS 节点](https://docs.openclaw.ai/platforms/ios)：[画布](https://docs.openclaw.ai/platforms/mac/canvas)，[语音唤醒](https://docs.openclaw.ai/nodes/voicewake)，[对话模式](https://docs.openclaw.ai/nodes/talk)，相机，屏幕录制，Bonjour 配对。
- [Android 节点](https://docs.openclaw.ai/platforms/android)：[画布](https://docs.openclaw.ai/platforms/mac/canvas)，[对话模式](https://docs.openclaw.ai/nodes/talk)，相机，屏幕录制，可选短信。
- [macOS 节点模式](https://docs.openclaw.ai/nodes)：system.run/notify + canvas/camera 暴露。

### 工具 + 自动化
- [浏览器控制](https://docs.openclaw.ai/tools/browser)：专用的 openclaw Chrome/Chromium，快照，操作，上传，配置文件。
- [画布](https://docs.openclaw.ai/platforms/mac/canvas)：[A2UI](https://docs.openclaw.ai/platforms/mac/canvas#canvas-a2ui) 推送/重置，评估，快照。
- [节点](https://docs.openclaw.ai/nodes)：相机快照/片段，屏幕录制，[location.get](https://docs.openclaw.ai/nodes/location-command)，通知。
- [Cron + 唤醒](https://docs.openclaw.ai/automation/cron-jobs)；[Webhook](https://docs.openclaw.ai/automation/webhook)；[Gmail Pub/Sub](https://docs.openclaw.ai/automation/gmail-pubsub)。
- [技能平台](https://docs.openclaw.ai/tools/skills)：捆绑、管理和工作区技能，带有安装门控 + UI。

### 运行时 + 安全
- [渠道路由](https://docs.openclaw.ai/concepts/channel-routing)，[重试策略](https://docs.openclaw.ai/concepts/retry)，以及[流式/分块](https://docs.openclaw.ai/concepts/streaming)。
- [在线状态](https://docs.openclaw.ai/concepts/presence)，[正在输入指示符](https://docs.openclaw.ai/concepts/typing-indicators)，以及[使用跟踪](https://docs.openclaw.ai/concepts/usage-tracking)。
- [模型](https://docs.openclaw.ai/concepts/models)，[模型故障转移](https://docs.openclaw.ai/concepts/model-failover)，以及[会话修剪](https://docs.openclaw.ai/concepts/session-pruning)。
- [安全](https://docs.openclaw.ai/gateway/security) 和[故障排除](https://docs.openclaw.ai/channels/troubleshooting)。

### 运维 + 打包
- [控制界面](https://docs.openclaw.ai/web) + [WebChat](https://docs.openclaw.ai/web/webchat) 直接从网关提供。
- [Tailscale Serve/Funnel](https://docs.openclaw.ai/gateway/tailscale) 或 [SSH 隧道](https://docs.openclaw.ai/gateway/remote) 带有令牌/密码验证。
- [Nix 模式](https://docs.openclaw.ai/install/nix) 用于声明式配置；基于 [Docker](https://docs.openclaw.ai/install/docker) 的安装。
- [医生](https://docs.openclaw.ai/gateway/doctor) 迁移，[日志](https://docs.openclaw.ai/logging)。

## 如何工作（简要）

```
WhatsApp / Telegram / Slack / Discord / Google Chat / Signal / iMessage / BlueBubbles / Microsoft Teams / Matrix / Zalo / Zalo Personal / WebChat
               │
               ▼
┌───────────────────────────────┐
│            网关            │
│       (控制平面)         │
│     ws://127.0.0.1:18789      │
└──────────────┬────────────────┘
               │
               ├─ Pi 代理 (RPC)
               ├─ CLI (openclaw …)
               ├─ WebChat 界面
               ├─ macOS 应用
               └─ iOS / Android 节点
```

## 关键子系统

- **[网关 WebSocket 网络](https://docs.openclaw.ai/concepts/architecture)** — 客户端、工具和事件的单一 WS 控制平面（运维：[网关手册](https://docs.openclaw.ai/gateway)）。
- **[Tailscale 暴露](https://docs.openclaw.ai/gateway/tailscale)** — 网关仪表板 + WS 的 Serve/Funnel（远程访问：[远程](https://docs.openclaw.ai/gateway/remote)）。
- **[浏览器控制](https://docs.openclaw.ai/tools/browser)** — openclaw 管理的 Chrome/Chromium 带有 CDP 控制。
- **[画布 + A2UI](https://docs.openclaw.ai/platforms/mac/canvas)** — 代理驱动的视觉工作区（A2UI 主机：[画布/A2UI](https://docs.openclaw.ai/platforms/mac/canvas#canvas-a2ui)）。
- **[语音唤醒](https://docs.openclaw.ai/nodes/voicewake) + [对话模式](https://docs.openclaw.ai/nodes/talk)** — 持续的语音和对话。
- **[节点](https://docs.openclaw.ai/nodes)** — 画布，相机快照/片段，屏幕录制，`location.get`，通知，以及仅限 macOS 的 `system.run`/`system.notify`。

## Tailscale 访问（网关仪表板）

OpenClaw 可以自动配置 Tailscale **Serve**（仅限尾网）或 **Funnel**（公开），同时网关绑定到回环地址。配置 `gateway.tailscale.mode`：

- `off`: 无 Tailscale 自动化（默认）。
- `serve`: 仅限尾网的 HTTPS 通过 `tailscale serve`（默认使用 Tailscale 身份头）。
- `funnel`: 公开的 HTTPS 通过 `tailscale funnel`（需要共享密码验证）。

注意事项：
- 当启用 Serve/Funnel 时，`gateway.bind` 必须保持为 `loopback`（OpenClaw 强制执行此设置）。
- 可以通过设置 `gateway.auth.mode: "password"` 或 `gateway.auth.allowTailscale: false` 强制 Serve 需要密码。
- 如果未设置 `gateway.auth.mode: "password"`，Funnel 将拒绝启动。
- 可选：`gateway.tailscale.resetOnExit` 在关闭时撤销 Serve/Funnel。

详情：[Tailscale 指南](https://docs.openclaw.ai/gateway/tailscale) · [Web 表面](https://docs.openclaw.ai/web)

## 远程网关（Linux 很棒）

完全可以在小型 Linux 实例上运行网关。客户端（macOS 应用、CLI、WebChat）可以通过 **Tailscale Serve/Funnel** 或 **SSH 隧道** 连接，仍然可以配对设备节点（macOS/iOS/Android）以在需要时执行设备本地操作。

- **网关主机** 默认运行 exec 工具和通道连接。
- **设备节点** 通过 `node.invoke` 运行设备本地操作（`system.run`，相机，屏幕录制，通知）。
简而言之：exec 运行在网关所在的地方；设备操作运行在设备所在的地方。

详情：[远程访问](https://docs.openclaw.ai/gateway/remote) · [节点](https://docs.openclaw.ai/nodes) · [安全](https://docs.openclaw.ai/gateway/security)

## macOS 权限通过网关协议

macOS 应用可以在 **节点模式** 下运行，并通过网关 WebSocket 广告其功能 + 权限映射（`node.list` / `node.describe`）。客户端然后可以通过 `node.invoke` 执行本地操作：

- `system.run` 运行本地命令并返回 stdout/stderr/退出代码；设置 `needsScreenRecording: true` 以要求屏幕录制权限（否则你会得到 `PERMISSION_MISSING`）。
- `system.notify` 发布用户通知并在通知被拒绝时失败。
- `canvas.*`，`camera.*`，`screen.record` 和 `location.get` 也通过 `node.invoke` 路由并遵循 TCC 权限状态。

提升的 bash（主机权限）与 macOS TCC 分开：

- 使用 `/elevated on|off` 在启用和白名单的情况下切换每个会话的提升访问。
- 网关通过 `sessions.patch`（WS 方法）持久化每个会话的切换，与 `thinkingLevel`，`verboseLevel`，`model`，`sendPolicy` 和 `groupActivation` 一起保存。

详情：[节点](https://docs.openclaw.ai/nodes) · [macOS 应用](https://docs.openclaw.ai/platforms/macos) · [网关协议](https://docs.openclaw.ai/concepts/architecture)

## 代理到代理（sessions_* 工具）

- 使用这些工具可以在不跳转聊天界面的情况下协调多个会话的工作。
- `sessions_list` — 发现活动会话（代理）及其元数据。
- `sessions_history` — 获取某个会话的对话记录日志。
- `sessions_send` — 向另一个会话发送消息；可选回复-pong 和公告步骤（`REPLY_SKIP`，`ANNOUNCE_SKIP`）。

详情：[会话工具](https://docs.openclaw.ai/concepts/session-tool)

## 技能注册表（ClawHub）

ClawHub 是一个最小的技能注册表。启用 ClawHub 后，代理可以自动搜索技能并根据需要拉取新的技能。

[ClawHub](https://clawhub.com)

## 聊天命令

在 WhatsApp/Telegram/Slack/Google Chat/Microsoft Teams/WebChat 中发送这些命令（群组命令仅限所有者）：

- `/status` — 紧凑的会话状态（模型 + 代币，可用时显示费用）
- `/new` 或 `/reset` — 重置会话
- `/compact` — 紧凑的会话上下文（摘要）
- `/think <级别>` — off|minimal|low|medium|high|xhigh（仅 GPT-5.2 + Codex 模型）
- `/verbose on|off`
- `/usage off|tokens|full` — 每个响应的使用情况页脚
- `/restart` — 重启网关（群组中仅限所有者）
- `/activation mention|always` — 群组激活切换（仅限群组）

## 应用程序（可选）

网关本身就能提供很好的体验。所有应用程序都是可选的，添加额外的功能。

如果你计划构建/运行配套应用程序，请参考以下平台手册。

### macOS (OpenClaw.app) （可选）

- 网关和健康状况的菜单栏控制。
- 语音唤醒 + 按住讲话覆盖层。
- WebChat + 调试工具。
- 通过 SSH 远程网关控制。

注意：macOS 权限需要签名构建才能在重建后保持不变（参见 `docs/mac/permissions.md`）。

### iOS 节点（可选）

- 通过桥接配对为节点。
- 语音触发转发 + 画布表面。
- 通过 `openclaw nodes …` 控制。

手册：[iOS 连接](https://docs.openclaw.ai/platforms/ios)。

### Android 节点（可选）

- 通过相同的桥接 + 配对流程与 iOS 配对。
- 暴露画布、相机和屏幕捕获命令。
- 手册：[Android 连接](https://docs.openclaw.ai/platforms/android)。

## 代理工作区 + 技能

- 工作区根目录：`~/.openclaw/workspace`（通过 `agents.defaults.workspace` 配置）。
- 注入的提示文件：`AGENTS.md`，`SOUL.md`，`TOOLS.md`。
- 技能：`~/.openclaw/workspace/skills/<技能>/SKILL.md`。

## 配置

最小的 `~/.openclaw/openclaw.json`（模型 + 默认设置）：

```json5
{
  agent: {
    model: "anthropic/claude-opus-4-5"
  }
}
```

[完整的配置参考（所有键 + 示例）](https://docs.openclaw.ai/gateway/configuration)

## 安全模型（重要）

- **默认**：工具在主机上运行 **主** 会话，因此当你单独使用时，代理拥有完全访问权限。
- **群组/频道安全**：设置 `agents.defaults.sandbox.mode: "non-main"` 以在每个会话的 Docker 沙盒中运行 **非主会话**（群组/频道）；对于这些会话，bash 在 Docker 中运行。
- **沙盒默认**：允许 `bash`，`process`，`read`，`write`，`edit`，`sessions_list`，`sessions_history`，`sessions_send`，`sessions_spawn`；禁止 `browser`，`canvas`，`nodes`，`cron`，`discord`，`gateway`。

详情：[安全指南](https://docs.openclaw.ai/gateway/security) · [Docker + 沙盒](https://docs.openclaw.ai/install/docker) · [沙盒配置](https://docs.openclaw.ai/gateway/configuration)

### [WhatsApp](https://docs.openclaw.ai/channels/whatsapp)

- 链接设备：`pnpm openclaw channels login`（凭据存储在 `~/.openclaw/credentials`）。
- 通过 `channels.whatsapp.allowFrom` 允许谁可以与助手对话。
- 如果设置了 `channels.whatsapp.groups`，它将成为群组允许列表；包含 `"*"` 以允许所有人。

### [Telegram](https://docs.openclaw.ai/channels/telegram)

- 设置 `TELEGRAM_BOT_TOKEN` 或 `channels.telegram.botToken`（环境变量优先）。
- 可选：设置 `channels.telegram.groups`（与 `channels.telegram.groups."*".requireMention` 一起）；设置后，它成为群组允许列表（包含 `"*"` 以允许所有人）。也可以根据需要设置 `channels.telegram.allowFrom` 或 `channels.telegram.webhookUrl`。

```json5
{
  channels: {
    telegram: {
      botToken: "123456:ABCDEF"
    }
  }
}
```

### [Slack](https://docs.openclaw.ai/channels/slack)

- 设置 `SLACK_BOT_TOKEN` + `SLACK_APP_TOKEN`（或 `channels.slack.botToken` + `channels.slack.appToken`）。

### [Discord](https://docs.openclaw.ai/channels/discord)

- 设置 `DISCORD_BOT_TOKEN` 或 `channels.discord.token`（环境变量优先）。
- 可选：设置 `commands.native`，`commands.text`，或 `commands.useAccessGroups`，以及根据需要设置 `channels.discord.dm.allowFrom`，`channels.discord.guilds`，或 `channels.discord.mediaMaxMb`。

```json5
{
  channels: {
    discord: {
      token: "1234abcd"
    }
  }
}
```

### [Signal](https://docs.openclaw.ai/channels/signal)

- 需要 `signal-cli` 和 `channels.signal` 配置部分。

### [iMessage](https://docs.openclaw.ai/channels/imessage)

- 仅限 macOS；Messages 必须已登录。
- 如果设置了 `channels.imessage.groups`，它将成为群组允许列表；包含 `"*"` 以允许所有人。

### [Microsoft Teams](https://docs.openclaw.ai/channels/msteams)

- 配置 Teams 应用 + Bot Framework，然后添加 `msteams` 配置部分。
- 通过 `msteams.allowFrom` 允许谁可以对话；群组访问通过 `msteams.groupAllowFrom` 或 `msteams.groupPolicy: "open"`。

### [WebChat](https://docs.openclaw.ai/web/webchat)

- 使用网关 WebSocket；无需单独的 WebChat 端口/配置。

浏览器控制（可选）：

```json5
{
  browser: {
    enabled: true,
    color: "#FF4500"
  }
}
```

## 文档

当你已经完成了入站流程并且想要更深入的参考时使用这些文档。
- [从文档索引开始导航和了解“哪里是什么”。](https://docs.openclaw.ai)
- [阅读网关 + 协议模型的架构概述。](https://docs.openclaw.ai/concepts/architecture)
- [在需要每个键和示例时使用完整的配置参考。](https://docs.openclaw.ai/gateway/configuration)
- [按照操作手册运行网关。](https://docs.openclaw.ai/gateway)
- [了解控制界面/Web 表面的工作方式以及如何安全地暴露它们。](https://docs.openclaw.ai/web)
- [了解通过 SSH 隧道或尾网的远程访问。](https://docs.openclaw.ai/gateway/remote)
- [跟随入站向导流程进行引导设置。](https://docs.openclaw.ai/start/wizard)
- [通过 webhook 表面连接外部触发器。](https://docs.openclaw.ai/automation/webhook)
- [设置 Gmail Pub/Sub 触发器。](https://docs.openclaw.ai/automation/gmail-pubsub)
- [了解 macOS 菜单栏配套应用的详细信息。](https://docs.openclaw.ai/platforms/mac/menu-bar)
- [平台指南：Windows (WSL2)](https://docs.openclaw.ai/platforms/windows)，[Linux](https://docs.openclaw.ai/platforms/linux)，[macOS](https://docs.openclaw.ai/platforms/macos)，[iOS](https://docs.openclaw.ai/platforms/ios)，[Android](https://docs.openclaw.ai/platforms/android)
- [使用故障排除指南调试常见故障。](https://docs.openclaw.ai/channels/troubleshooting)
- [在暴露任何内容之前查看安全指导。](https://docs.openclaw.ai/gateway/security)

## 高级文档（发现 + 控制）

- [发现 + 传输](https://docs.openclaw.ai/gateway/discovery)
- [Bonjour/mDNS](https://docs.openclaw.ai/gateway/bonjour)
- [网关配对](https://docs.openclaw.ai/gateway/pairing)
- [远程网关 README](https://docs.openclaw.ai/gateway/remote-gateway-readme)
- [控制界面](https://docs.openclaw.ai/web/control-ui)
- [仪表板](https://docs.openclaw.ai/web/dashboard)

## 运营 & 故障排除

- [健康检查](https://docs.openclaw.ai/gateway/health)
- [网关锁定](https://docs.openclaw.ai/gateway/gateway-lock)
- [后台进程](https://docs.openclaw.ai/gateway/background-process)
- [浏览器故障排除（Linux）](https://docs.openclaw.ai/tools/browser-linux-troubleshooting)
- [日志](https://docs.openclaw.ai/logging)

## 深度解析

- [代理循环](https://docs.openclaw.ai/concepts/agent-loop)
- [在线状态](https://docs.openclaw.ai/concepts/presence)
- [TypeBox 模式](https://docs.openclaw.ai/concepts/typebox)
- [RPC 适配器](https://docs.openclaw.ai/reference/rpc)
- [队列](https://docs.openclaw.ai/concepts/queue)

## 工作区 & 技能

- [技能配置](https://docs.openclaw.ai/tools/skills-config)
- [默认 AGENTS](https://docs.openclaw.ai/reference/AGENTS.default)
- [模板: AGENTS](https://docs.openclaw.ai/reference/templates/AGENTS)
- [模板: BOOTSTRAP](https://docs.openclaw.ai/reference/templates/BOOTSTRAP)
- [模板: IDENTITY](https://docs.openclaw.ai/reference/templates/IDENTITY)
- [模板: SOUL](https://docs.openclaw.ai/reference/templates/SOUL)
- [模板: TOOLS](https://docs.openclaw.ai/reference/templates/TOOLS)
- [模板: USER](https://docs.openclaw.ai/reference/templates/USER)

## 平台内部

- [macOS 开发设置](https://docs.openclaw.ai/platforms/mac/dev-setup)
- [macOS 菜单栏](https://docs.openclaw.ai/platforms/mac/menu-bar)
- [macOS 语音唤醒](https://docs.openclaw.ai/platforms/mac/voicewake)
- [iOS 节点](https://docs.openclaw.ai/platforms/ios)
- [Android 节点](https://docs.openclaw.ai/platforms/android)
- [Windows (WSL2)](https://docs.openclaw.ai/platforms/windows)
- [Linux 应用](https://docs.openclaw.ai/platforms/linux)

## 邮件钩子（Gmail）

- [docs.openclaw.ai/gmail-pubsub](https://docs.openclaw.ai/automation/gmail-pubsub)

## Molty

OpenClaw 是为 **Molty** 构建的，一个太空龙虾 AI 助手。🦞
作者：Peter Steinberger 和社区。

- [openclaw.ai](https://openclaw.ai)
- [soul.md](https://soul.md)
- [steipete.me](https://steipete.me)
- [@openclaw](https://x.com/openclaw)

## 社区

参阅 [CONTRIBUTING.md](CONTRIBUTING.md) 了解贡献指南、维护者以及如何提交 PR。
欢迎提交 AI/氛围编码的 PR！🤖

特别感谢 [Mario Zechner](https://mariozechner.at/) 的支持和
[pi-mono](https://github.com/badlogic/pi-mono)。
特别感谢 Adam Doppelt 的 lobster.bot。

感谢所有 clawtributors：
