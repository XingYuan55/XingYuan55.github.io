# Work steps and trace

The AI does not just give an answer: in between it thinks, reads files, runs commands, edits code. The desktop app shows this as one-line work steps, and the trace view is the same record as a timeline.

## Work steps in the chat

The small lines above an answer are the steps, one per line:

- **思考** (thinking): the model is thinking; expand to read the reasoning.
- **已调用工具并读取文件** (called a tool and read a file), **查看了屏幕** (looked at the screen): tool calls, with the tool name or target in the line.
- **正在操作** (working): running now, followed by an ellipsis.
- Lines marked **已完成** at the end are finished.

Click a line to expand its details: the command, arguments, output, and screenshots for that step. Click again to fold.

When a turn has many steps they fold into a one-line summary, e.g. "使用了 4 个工具 · 已完成" (used 4 tools · done). Expanding still shows everything.

How much is shown is set by three dropdowns in **Settings › General**:

- **工作步骤展示** (step detail): **简洁** (concise), **标准** (standard), **详细** (detailed), **完全展开** (fully expanded). Default is **详细**.
- **工作步骤收起时机** (when to fold): **回答结束后** (after the answer) or **下次有新消息时** (on the next message).
- **收起后显示的回复** (replies kept after folding): **全部回复** (all) or **仅最终回答** (final only).

With **完全展开**, steps no longer fold automatically, which suits checking what the AI did step by step.

## Trace view

Click **轨迹** in the session header; the chat area is replaced by the trace:

- Top toolbar: **使用实际时长** (use actual duration; off shows accumulated time), **收起所有轮次** (fold all turns), **收起所有调用** (fold all calls), **收起所有子调用** (fold all sub-calls), **搜索轨迹** (search trace).
- In the middle, the **轨迹时间线** (trace timeline): events in time order. Drag horizontally to focus a moment; scroll to the top and click **加载更早的历史** (load earlier history) for older events.
- Events are grouped by turn, one per line, e.g. "请求 50 · 助手" (request 50 · assistant), "工具调用 · Read" (tool call · Read).
- Click an event to open **事件详情** (event details) on the right.

## Event details

Five tabs on the right:

- **概述** (overview): summary, model, and status of the request or call.
- **参数** (arguments): what was sent, as JSON.
- **结果** (result): what came back.
- **Schema**: the tool's argument schema.
- **计时** (timing): start, end, duration.

The top-right corner can **关闭详情** (close details), and you can drag the edge to resize.

Use the trace to answer "why did it answer that", "which step got stuck", "did it actually read this file". For daily use you rarely need it; the step summary in the chat view is usually enough.

## Turn navigation

Next to the timeline you can jump by turn: click **第 N 轮** (turn N) to jump to that turn's start. For long histories, click **加载并跳转到第 N 轮** (load and jump to turn N) first.
