# FAQ

## A message will not send, or it spins forever

Check the model button under the input box first: is the current model unreachable? Then the balance: Settings → Account and balance; zero balance usually errors out.

If it only fails in one workspace, check that the workspace directory still exists; deleted or renamed directories fail to open.

## The AI says it has no permission, or cannot change files

Look at the access mode on the left of the input box:

- **仅可查看** (view only): read only.
- **工作区内修改** (modify within workspace): only files inside the current workspace.
- **完全权限** (full access): the whole disk.

A denied write usually means the mode is "view only", or the file is outside the workspace. Change the mode from the dropdown on the left of the input box.

## A write failed halfway, or the UI errors

Read the path in the error; confirm the directory exists and you can write to it. Writes can also fail when a file is locked (e.g. open in another program); retrying usually works.

Do not work around it with "full access"; first understand why it was denied.

## A panel or button is missing

Three usual causes:

1. The plugin is turned off. Check switches in **插件** in the sidebar.
2. That panel was added by a third-party plugin not installed on this machine.
3. A different version moved it. Trust the wording on your machine.

## Nothing changed after installing a plugin

Plugins usually need a DSH restart to fully take effect. In the plugin panel click **刷新** (refresh) to see whether it is recognized; if it still does not appear, quit DSH and reopen.

## An automation task did not run on time

Check whether the task is "已开启" (enabled), whether the schedule is right, and the time zone. Then the run records: a record means delivery happened; no result means the AI step failed, so open the linked chat.

A paused task does not replay runs missed while paused.

## The context keeps growing and replies slow down

The longer a chat, the more the model must read, so it gets slower and pricier. You can:

- Start a new chat for a new topic.
- Set work-step display to "简洁" (concise) to reduce on-screen content.
- Use a context-related plugin for compression if installed.

How compression works is up to the plugin's own docs.

## A chat is missing

Search titles with **搜索会话** in the sidebar first. Archived chats are hidden by default; show them via **视图选项 › 全部对话（显示已归档）**.

Deleted chats cannot be recovered.

## Will a chat survive a restart

Yes. Chats are stored on this machine and appear again after reopening DSH. An in-progress turn is interrupted; say it again after reopening.

## Where is my data

Chats, config, and plugins live in your user directory on this machine; they are local data and do not sync across machines. To move them, copy the corresponding directories manually.

## My UI looks different from someone's screenshot

Check whether either side has UI-changing plugins installed, then whether the versions match. DSH is still a preview: wording, positions, and button counts can change. When this guide and your UI disagree, trust your UI.
