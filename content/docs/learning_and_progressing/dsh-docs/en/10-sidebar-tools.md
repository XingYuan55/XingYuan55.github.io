# Sidebar and right tools

The DSH window has three parts: the sidebar for chats, the chat in the middle, and a tools area on the right that opens on demand. This chapter covers the sidebar and the right tools.

## Sidebar top

From top to bottom:

- Brand area: shows DeepSeek Harness; clicking it also starts a new chat.
- **新建会话** (new chat).
- Three global entries: **插件** (plugins), **自动化任务** (automation), **更多** (more).

**更多** holds other global panels, e.g. browse more plugins, create your own plugin. The exact items vary by version and plugin.

## Workspaces

A workspace is a local folder the AI reads and writes. Next to the "工作区" heading are three buttons: **搜索会话** (search chats), **视图选项** (view options), **添加工作区** (add workspace).

- **Add workspace**: pick a local directory, register it as a workspace, and open its chat list.
- **Search chats**: search by title across workspaces.
- **View options**: grouping and sorting, see [Appearance and display](09-appearance.md).

Below the workspaces is the chat list, grouped. Each workspace holds its chats with relative times. Click a chat to switch.

## Chat rows

One row per chat. Hovering a title scrolls long titles to the end; leaving returns to the start.

A row supports rename, pin, archive, delete. Archived chats remain and can be restored; deleting is permanent.

Running chats carry a "进行中" (running) mark. The selected chat is highlighted.

## Account menu

At the bottom of the sidebar is the account button with the masked phone number. It opens **设置** (settings), **意见反馈** (feedback), **退出登录** (sign out).

**Sign out** clears the sign-in state on this machine; you will need to sign in again next time.

## Right tools area

Click **打开右侧边栏** (open right sidebar) in the header; a column titled "开始" (start) appears on the right with four entries:

- **工作区文件** (workspace files, Ctrl+P): browse the current workspace; open a file to view it.
- **新建终端** (new terminal, Ctrl+\`): a terminal in the chat's working directory.
- **浏览器** (browser, Ctrl+T): an in-app browser; the AI's web lookups can show up here.
- **更多工具** (more tools): browse more plugins, create your own plugin.

The area does not steal focus, so you can read files on the right while chatting on the left. Click the header button again to close it.

## Header

The session header, left to right: session path, current preset tag (e.g. "标准模式"), view tabs (chat, trace, context, and "more session views"), then on the right **用文件资源管理器打开** (open in File Explorer), **更多打开方式** (more ways to open), **更多操作** (more actions), **打开右侧边栏** (open right sidebar).

**更多操作** contains copying the chat as Markdown, downloading the session log, and feedback. **用文件资源管理器打开** opens the current workspace folder directly.

## When the window is narrow

On narrow windows both the sidebar and the right tools area can be collapsed. With both closed, only the chat remains, which suits small screens or split view.
