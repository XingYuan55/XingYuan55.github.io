# Sidebar, chats, and workspaces

The left column is the sidebar: entries and tools at the top, workspaces and chats below.

## Sidebar top

- **新建会话** (new chat): the button under the brand mark; opens a blank chat.
- **收起侧边栏** (collapse sidebar): the icon in the brand row; collapsing widens the window. Click again to expand.
- **插件** (plugins), **自动化任务** (automation), **更多** (more): global panels. See [Plugins](07-plugins.md) and [Automation](06-automation.md). **更多** may gain plugin entries.

## Workspaces

The middle of the sidebar lists workspaces: the folder the AI works in, usually a project directory. Chats belong to a workspace; switch workspaces and the chat list follows.

- **搜索会话** (search chats): the magnifier, see below.
- **视图选项** (view options): adjust how the list is displayed.
- **添加工作区** (add workspace): pick a directory to register. It opens a new chat whose folder is that directory.

A workspace is just a directory on disk. "Modify within workspace" means exactly the files in that directory. Registering a workspace copies or moves nothing; only the path is recorded. If the directory is deleted or renamed, opening the workspace reports an error and you must add it again.

### View options

The **视图选项** menu has three parts:

- **分类方式** (grouping): **按工作区** (by workspace, default; one section per workspace), **按工作区树** (by workspace tree; workspaces with parent/child directories nest), **单列表** (single list; all chats in one column).
- **排序方式** (sorting): **手动排序** (manual, drag to reorder) or **最近更新** (recently updated, default).
- **筛选会话** (filter chats): **隐藏已归档** (hide archived), **全部对话（显示已归档）** (all, including archived), **仅显示已归档** (archived only).

## Chat rows

Each workspace lists its chats, one per row:

- The title, with relative time on the right, e.g. "2 小时" (2 hours), "1 天" (1 day).
- Chats that are running show "进行中" (running) with a spinning icon.
- The selected row is highlighted.
- Hovering scrolls a long title to its end so you can read it all.

Click a row to open the chat. Right-click a row or open the row menu for **重命名** (rename), **置顶** (pin), **归档** (archive), **删除** (delete). Common rules:

- **Rename**: changes the display name only, not the chat's content.
- **Pin**: pinned chats sort to the top of the workspace.
- **Archive**: removes it from the default list without deleting the record. Find it again via **视图选项 › 全部对话（显示已归档）**.
- **Delete**: removes the chat record; cannot be undone. Files in the working directory are not affected.

## Search chats

Click the magnifier, then type words from a title or content. Results are grouped by workspace; click one to open it. Search covers only the chats on this machine; nothing is sent online.

## Account menu at the bottom

The bottom of the sidebar is the account button, showing a masked phone number, e.g. `186*****61`. Opening it gives:

- **设置** (settings): see [Settings](08-settings.md).
- **意见反馈** (feedback): take an issue to the feedback page.
- **退出登录** (sign out): signs out of the DeepSeek account. Account-required models stop working afterwards, but chats and files remain.

## Session header

Once a chat is open, the header shows the chat title, the **标准模式** (standard mode) tag, and a group of icons. See [Window, menus, and shortcuts](11-window-menu.md). The window title also becomes "chat title — DeepSeek Harness".
