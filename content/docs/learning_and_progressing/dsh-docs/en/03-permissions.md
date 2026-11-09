# Permissions and approvals

Permissions decide whether the AI may change your files or run commands. The desktop app has several levels; the **访问模式** (access mode) button under the input box shows the current chat's level.

## Three levels

Click **访问模式** to open the menu:

- **仅可查看** (view only): read only; cannot change files or run commands.
- **工作区内修改** (modify within workspace): read and write inside the chat's workspace only; nothing outside. This is the default for new chats.
- **完全权限** (full access): read and write anywhere on disk, run any command. Choosing it confirms the risk first.

With the experimental "自动授权审查" (auto approval review) plugin on, an extra level **自动审查** appears with an EXP badge; it has the model judge each tool call, letting approved ones run and holding rejected ones for you. It is experimental; see [Plugins](07-plugins.md).

A level applies to the current chat only. Each chat keeps its own choice.

## Default for new chats

<!-- nav: settings,general -->
`Account menu › Settings › General › Permissions`

The subtitle is "选择新会话的默认权限模式" (default permission mode for new sessions); the default is **工作区内修改**. Changing it affects only chats created afterwards, not ones already open.

## Widening and narrowing

- Going from a wider level to a narrower one takes effect immediately; the next turn no longer has the wider access.
- Switching mid-run does not interrupt the current turn, but the next turn follows the new level.
- If unsure, keep **工作区内修改**: most reads and writes are inside the workspace; widen only when you really need system folders.

## Approval cards

When an action needs your consent (writing outside the workspace, running a command, network access), an approval card appears in the chat: it names the action, the target path or command, and the reason. The buttons are usually **允许本次** (allow this time) and **拒绝** (deny).

- **Allow this time** permits just this one action.
- For a whole class of actions, the card also offers broader scopes; the broader the scope, the more carefully you should read it.
- If you deny, the AI receives that result and usually tries another way or tells you it could not finish.

Approvals are recorded in the chat log and can be checked later via **更多操作 › 下载 Session 日志** (download session log) in the session header.

## Least-privilege advice

- Just asking questions or reading files: **仅可查看**.
- Writing code or changing a project: **工作区内修改**, and make sure the chat's workspace is the folder you want touched.
- Installing software, changing system settings, cleaning a disk: only then **完全权限**, and switch back afterwards.
