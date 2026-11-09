# Window and menus

DSH is a desktop app: besides the buttons in the UI, there is a menu bar at the top of the window. This chapter covers the menus, window behavior, and shortcuts.

## Application menu

Click **应用** (application) at top left:

- **关于 DeepSeek Harness** (about): version and description.
- **检查更新…** (check for updates…).
- **管理 dsh 命令…** (manage dsh commands…): the command-line entry points.
- **开发者工具** (developer tools), Ctrl+Shift+I. For debugging; you will not need it normally.
- **退出** (quit): closes DSH.

**Quit** ends the DSH process. Running tasks are interrupted; unsent text usually stays as a draft in the input box and may be there next time.

## Edit menu

- **撤销** Ctrl+Z
- **重做** Ctrl+Y
- **剪切** Ctrl+X
- **复制** Ctrl+C
- **粘贴** Ctrl+V
- **删除** (delete)
- **全选** Ctrl+A

These are editing operations for the input box and text areas, the usual Windows set.

## Window

- The three top-right buttons: minimize, maximize, close.
- Closing the window does not quit the process; reopening restores the state.
- Window size and position are remembered.

## Shortcuts

Common ones:

- **Ctrl+P**: open workspace files.
- **Ctrl+\`**: new terminal.
- **Ctrl+T**: open the in-app browser.
- **Ctrl+Shift+I**: developer tools.
- **Esc**: close popups, cancel input. Press Esc twice in the input box to stop generation.

Shortcuts are editable: Settings → General → **编辑快捷键** (edit shortcuts). Changes are stored on this machine.

Shortcuts can change between versions; what **编辑快捷键** lists is authoritative.

## View

**更多会话视图** (more session views) expands the tab list. **用文件资源管理器打开** (open in File Explorer) opens the workspace folder. **更多打开方式** (more ways to open) opens the same file or folder in another editor. **更多操作** (more actions) is chat-level: copy as Markdown, download session log, feedback.

## Appearance

Whether the window follows the system theme or stays light/dark is set under Settings → General → **外观** (appearance). Both the sidebar and the right tools area collapse and expand; see [Appearance and display](09-appearance.md).
