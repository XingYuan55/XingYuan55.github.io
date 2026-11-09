# Settings

The Settings window holds global options: account, appearance, models, plugins, Agent presets. Open it from the account button at the bottom of the sidebar, then **设置**. The top-right corner has **打开配置文件** (open config file) and **关闭** (close).

The left column lists groups:

- **账号与余额** (account and balance)
- **通用设置** (general)
- **模型** (models)
- **内置插件** (built-in plugins)
- **电脑操控** (computer control), present only when a plugin provides it
- **Agent 预设** (agent presets)

Extra groups are usually added by third-party plugins and may not exist on another machine.

## Account and balance

At the top: **已登录 DeepSeek** (signed in), the masked phone number, and **更多账号信息** (more account info).

Below that, money: **充值余额** (balance) shows the amount, **查询用量** (usage) opens usage, **充值** (top up) goes to payment. When the balance runs out, chats fail; top up here.

## General

From top to bottom:

- **权限** (permissions): default level for new chats: **仅可查看**, **工作区内修改**, or **完全权限**. Affects new chats only; running ones keep their level.
- **语言** (language): Chinese or English.
- **外观** (appearance): **浅色** (light), **深色** (dark), **跟随系统** (follow system).
- **字号大小** (font size): only chat content; **增大字号** / **减小字号**, plus **更多字体设置** (more font settings) for finer control.
- **工作步骤展示** (step detail): **简洁**, **标准**, **详细**, **完全展开**.
- **工作步骤收起时机** (when to fold): **回答结束后** (after the answer) or **下次有新消息时** (on the next message).
- **收起后显示的回复** (replies kept after folding): **全部回复** or **仅最终回答**.
- **显示代码工作视图** (code working view): shows this turn's code diff in the trace, and allows switching full Agent presets.
- **快捷键** (shortcuts): **编辑快捷键** (edit shortcuts) to view and change key bindings.

Scrolling further you may find **性能与用量** (performance and usage: concise or detailed) and **网页链接默认打开方式** (open links in the in-app sidebar or the default browser). Their position can move between versions.

## Models

Which providers the AI can use. One row per provider:

- **DeepSeek 账号**: green dot means signed in; uses the account's quota.
- **DeepSeek**: API key against DeepSeek's official API.
- **Third-Party**: a custom provider with **编辑** (edit) and **删除** (delete).

Click a row to edit; **+ 添加模型提供商** adds one. This page controls which models exist; which one a chat uses is picked under the input box.

## Built-in plugins

The same capabilities as the **插件** panel's configuration area, listed here as session-plugin cards: persona, workspace instructions, time awareness, command tools, file tools, background jobs, task scheduling, local skill loading. Each card has its own switch.

A **插件列表** tab at the top may be added by a plugin, not required.

## Agent presets

A preset decides which tools a chat's AI has and how it works. Four built-in cards:

- **标准模式** (standard, default): code, files, and research; suits most tasks.
- **PTC 模式**: adds batch scheduling on top of standard, good for batch tool calls followed by filtering and summarizing.
- **极简模式** (minimal): only terminal and image-reading tools, with context compression; good for tests or comparisons.
- **创造模式** (creative): for customizing DSH; can add features or UI.

Each card has **模式说明** (description) and **如何使用** (how to use). At the bottom, **让 Agent 帮我创建预设模式** (let the Agent create a preset) builds a custom preset from your description. Self-made presets appear here too.

Changing a preset affects new chats only; the tag in the session header shows which preset the current chat uses.

## Open config file

**打开配置文件** opens this profile's config file. It has a strict format; a bad edit can keep DSH from starting. Back it up first if unsure, and after editing, quit and reopen to verify.

## About "Computer control"

That group appears only when a computer-control plugin is installed (e.g. one that lets the AI see the screen, click, type). It is not built in; the plugin's own docs govern switches and risks. On machines without such a plugin, there is no such entry.
