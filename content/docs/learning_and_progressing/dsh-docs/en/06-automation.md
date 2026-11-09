# Automation tasks

An automation task lets the AI run on a schedule: summarize news every morning, report project status weekly, remind you at a set time. Tasks are delivered into a chat in the background; delivery is not the same as successful execution, so check the chat for results.

## Open the task panel

Click **自动化任务** (automation) in the sidebar. The page has a title and **+ 新建** (new) button, then tabs:

- **已开启** (enabled): running on schedule.
- **已暂停** (paused): paused but kept.
- **已结束** (ended): finished one-off tasks, or stopped tasks.
- **全部** (all).

Below is **搜索自动化任务** (search tasks). With no tasks, the page shows "没有已开启的自动化任务" (no enabled automation tasks) and a **新建自动化任务** (new automation task) button.

## Create a task

Click **+ 新建** (or the button in the empty state). You return to a new chat whose input box is prefilled with "请根据需求创建一个自动化任务。" (create an automation task from the requirement). Say three things plainly:

1. What to do, e.g. "summarize new articles in my reading list with their links".
2. When to do it, e.g. "every day at 9am".
3. Which chat to run it in: keep this chat, or open a new one each time.

Send it; the AI confirms through the usual approval flow and creates the task.

## Task details

Click a task to open its details. Rules on the left, run records on the right:

- **自动化任务名称** (task name): what the list shows, e.g. "每日阅读摘要" (daily reading digest).
- **自动化任务内容** (task content): the instruction the AI runs each time.
- **关联会话** (linked chat): where the task runs; the link opens that chat.
- **执行位置** (where it runs): **新建会话并复用** (open once, reuse) or **每次新建会话** (a new chat each run). Manually created tasks default to the former.
- **时间规则** (schedule): **仅一次** (once), **每分钟** (every minute), **每小时** (hourly), **每天** (daily), **每周** (weekly), **每月** (monthly), or **自定义** (custom).

Custom accepts a two-line RRULE or a five-field Cron with an explicit time zone. Save when done; with an invalid rule the save button stays disabled and points at the field to fix. Times follow the time zone you choose, which matters around time-zone or daylight-saving changes.

## Run records

**任务运行记录** (run records) loads 20 per page, newest first. Each record shows the delivery time and the instruction saved at that time; long instructions expand. Records only prove a delivery was sent, not that the AI succeeded; open the chat from a record to see the outcome.

Old records are pruned automatically; the retention rule is shown near the bottom, e.g. "keep the latest M records within the last N days per task".

## Pause, resume, run now, delete

- **暂停** (pause): keeps the task, stops scheduled runs.
- **恢复** (resume): continues on the original schedule; missed runs during the pause are not replayed.
- **立即执行** (run now): delivers once immediately. Just after a run, before the minimum interval passes, this item is unavailable and the hint says when it becomes available.
- **删除** (delete): removes the task and its records but keeps chats and delivered messages. Deletion asks for confirmation, and the confirm dialog focuses **取消** (cancel) first to avoid accidental confirmation.

With unsaved changes, save or discard before pausing, resuming, running now, or deleting. While a task is queued or executing, those buttons are disabled; manage that run in the chat instead.

## Tasks and chats

A task is not a separate thing: everything it does happens in a chat, with steps, approvals, and results. When a task misbehaves, check the linked chat first, then whether the run record timestamps line up.
