# Chat

Ask questions, hand work to the AI, and watch what it does step by step. A chat belongs to the current workspace: switch workspaces and the list shows that workspace's chats.

## Input box

The box at the bottom of the window says "发消息或创建任务, / 调用指令, @ 文件或对话" (send a message or create a task, / for commands, @ for files or chats). Type and press the send key. While the AI is generating, the send button becomes **Stop**; click it to end the turn.

The **+** on the left is "添加文件或调用指令" (add a file or invoke a command). Drag files or folders into the window, pick files from disk, or open the command list here.

Two buttons under the box each control one thing:

- **Access mode**: whether this chat is "仅可查看" (view only), "工作区内修改" (modify within workspace), or "完全权限" (full access). Click to switch. See [Permissions and approvals](03-permissions.md).
- **Select model**: shows the current model and reasoning effort, e.g. `DeepSeek-V4.1-Flash High`. Click to switch. See [Models and reasoning effort](02-models.md).

## Commands and references

Type `/` in the box to open the command list, `@` to reference a file or another chat. Commands come from the plugins and settings you have; the popup lists everything available.

## Views: chat, trace, and more

**对话** (chat) and **轨迹** (trace) tabs under the session header switch this chat's view:

- **对话**: your messages, the AI's replies, and its work steps.
- **轨迹**: every request, tool call, and event in time order, for digging into details. See [Work steps and trace](04-work-steps.md).

The **⋯** to the right is "更多会话视图" (more session views); views added by plugins also live there.

## Status line

A small line under the input box summarizes the chat, left to right:

- **9 轮 101 步 · 240 tok/s**: turns so far, steps the AI took, generation speed.
- **6.8M tok · 缓存命中 82%**: tokens used by this chat, and the share served from cache.
- **上下文已用 11%**: how much of the context window is used.

Clicking the context figure opens the context view. That view is supplied by a plugin, not built in; without the plugin the button is gone.

## Work steps

While the AI works, each step appears as a small line above the answer, e.g. "思考" (thinking), "已调用工具并读取文件" (called a tool and read a file), "正在操作" (working), "查看了屏幕" (looked at the screen). Finished steps are marked **已完成**. Click a line to expand its details, including the step's description and screenshots.

When there are many steps they fold automatically and only the result stays. What folds and when is set in [Settings › General settings](08-settings.md):

- **工作步骤展示** (how much to show): 简洁 (concise) / 标准 (standard) / 详细 (detailed) / 完全展开 (fully expanded).
- **工作步骤收起时机** (when to fold): 回答结束后 (after the answer) / 下次有新消息时 (on the next message).
- **收起后显示的回复** (replies kept after folding): 全部回复 (all replies) / 仅最终回答 (final answer only).

## Session header

From left to right:

- **会话层级** (session path): breadcrumb showing workspace and chat; click a parent to go back.
- **标准模式**: the Agent preset this chat uses. See [Settings › Agent preset](08-settings.md).
- Icons on the right: **用文件资源管理器打开** (open the chat's folder in File Explorer), **更多打开方式** (more ways to open), **更多操作** (more actions), **打开右侧边栏** (open the right sidebar). See [Sidebar and right tools](10-sidebar-tools.md).

**更多操作** contains **复制会话为 Markdown** (copy chat as Markdown), **下载 Session 日志** (download session log), and **反馈** (feedback). Copy and download happen locally and send nothing out; feedback takes you to the official feedback page.

## While generating

- The send button becomes **Stop**; one click ends the turn.
- Work step lines keep appearing; click "正在操作 ▾" for live detail.
- The turn's elapsed time and speed show under the steps, e.g. "深度求索中，用时 2分8秒".

After stopping, the answer and steps produced so far stay in the chat and you can keep asking.
