<div align="center">

# AiKey Labs

**让所有 AI 工具，共用同一个工作台。**

把 Claude、Codex、Kimi 的 KEY、账号与路由统一管理，
让团队在不中断工作的情况下切换额度、观察成本、
编排多模型生产力。

[English](README.md) · **中文**

<p>
  <a href="https://aikeylabs.com"><img alt="website" src="https://img.shields.io/badge/website-aikeylabs.com-0ea5e9?style=flat-square"></a>
  <a href="https://github.com/aikeylabs/launch/releases/latest"><img alt="latest release" src="https://img.shields.io/github/v/release/aikeylabs/launch?label=latest&style=flat-square"></a>
  <a href="https://github.com/aikeylabs/launch#install"><img alt="quickstart" src="https://img.shields.io/badge/quickstart-launch-2563eb?style=flat-square"></a>
  <img alt="platforms" src="https://img.shields.io/badge/platform-macOS%20%7C%20Linux%20%7C%20Windows-555?style=flat-square">
  <img alt="status" src="https://img.shields.io/badge/status-GA-22c55e?style=flat-square">
</p>

</div>

---

## 一行命令安装

**macOS / Linux**

```bash
curl -fsSL https://github.com/aikeylabs/launch/releases/latest/download/latest-install.sh | sh
```

**Windows（PowerShell 原生，无需 WSL）** —— 见 `launch` 仓库的
[Windows 安装说明](https://github.com/aikeylabs/launch#windows-specific)。

安装完成后打开新终端，执行 `aikey web` 即可添加第一个 KEY。

---

## 为什么选 AiKey？

<table>
<tr>
<td width="50%" valign="top">

### 一个 Vault 管所有 AI 凭证

把 Claude / Codex / Kimi 的 API KEY 和 OAuth 账号统一导入本地 Vault。
真实凭证留在 Vault 里，日常只分发可撤销的路由 token 或当前 active 绑定。

```bash
aikey add my-key
aikey auth login claude
aikey use
```

</td>
<td width="50%" valign="top">

### 用量与 token 成本实时可见

按 KEY、账号、协议查看用量趋势，结合 token 结构（cache 占比、请求量、provider 分布），
不必等账单出来才发现异常。

```bash
aikey web        # Vault · 用量 · Dashboard
```

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 多窗口、多应用、多账号并行

窗口 A 跑 Claude，窗口 B 跑 Codex，窗口 C 跑 Kimi ——
不同终端可以用不同账号，环境变量互不抢占。

```bash
aikey activate claude2   # 仅作用于当前终端
```

</td>
<td width="50%" valign="top">

### 额度用完，不打断思路

当前账号额度耗尽时，不必退出正在运行的 `claude` 会话，
切换 active 绑定后，下一次请求自动切到新账号。

```bash
aikey use backup-account
```

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 自定义路由 · 接入任意 AI 客户端

`aikey route` 输出的 `base_url` + `api_key` 可以粘贴到 Cursor、OpenCode、
Continue，或任何 OpenAI / Anthropic 兼容客户端。把多个 AI 账号编排成
一套可控路由。

```bash
aikey route                # 查看所有可用路由
aikey route my-key         # 复制指定 KEY 的 base_url + api_key
```

</td>
<td width="50%" valign="top">

### 无缝衔接第三方 Agent

**第三方 Agent 永远拿不到明文 KEY。** 真实的 provider 凭证始终留在 Vault；
每个 Agent 的访问权限都在你的掌控之中 —— 按 Agent 授予、按 Agent 撤销。

</td>
</tr>
</table>

完整操作走查与截图，见 **[launch · 快速开始 →](https://github.com/aikeylabs/launch/blob/main/README.zh.md)**。

---

## 子项目

| 仓库 | 介绍 |
|---|---|
| **[launch](https://github.com/aikeylabs/launch)** | 跨平台安装脚本、发布包、macOS / Linux / Windows 快速开始。**新用户从这里开始。** |
| **[aikey-cli](https://github.com/aikeylabs/aikey-cli)** | `aikey` / `ak` 命令行工具 —— Vault、OAuth 登录、KEY 切换、路由、健康检查。Rust 实现。 |
| **[aikey-proxy](https://github.com/aikeylabs/aikey-proxy)** | 本地代理 —— 按 virtual key 路由 Claude / Codex / Kimi 流量，采集用量与成本。Go 实现。 |

> 其他子项目（VS Code 插件、浏览器插件、团队版控制台）将在 GA 后陆续开源。

---

## 常用命令

```bash
aikey list              # 查看 Vault 中的所有 KEY
aikey use               # 切换当前激活的 KEY
aikey route             # 查看 base_url + api_key（接入第三方客户端用）
aikey web               # 打开本地控制台（Vault / 用量 / Dashboard）
aikey doctor            # 一键健康检查
aikey test --all        # 探测 Vault 中的每一个凭证
```

CLI 也响应短别名 `ak`（`ak use`、`ak env`、`ak doctor` 均可）。

---

## 文档

- [快速开始](https://github.com/aikeylabs/launch/blob/main/README.zh.md#aikey-快速开始) —— 个人版端到端流程
- [常用命令](https://github.com/aikeylabs/launch/blob/main/README.zh.md#常用命令) —— 完整命令清单
- [第三方客户端接入](https://github.com/aikeylabs/launch/blob/main/README.zh.md#高级用法在第三方-ai-客户端中使用-key) —— Cursor / OpenCode / Continue
- [故障排查](https://github.com/aikeylabs/launch/blob/main/README.zh.md#故障排查) —— 常见问题处理

---

## 社区

- **Issue 与需求** —— 请到对应子项目仓库提交
- **安全披露** —— 请走私有渠道，详见各仓库的 `SECURITY.md`
- **欢迎贡献** —— 请遵循各项目的贡献指南

<div align="center">
  <sub>AiKey Labs —— 敏感凭证集中保管，工作入口自由分发。</sub>
</div>
