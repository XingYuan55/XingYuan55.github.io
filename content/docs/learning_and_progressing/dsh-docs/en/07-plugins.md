# Plugins

The plugin panel handles three things: which built-in features are on, which experimental features to try, and which third-party plugins are installed. Click **插件** (plugins) in the sidebar; the header has **刷新** (refresh) and **添加插件** (add plugin).

The page can change with version and installed plugins. Unknown groups, switches, or tabs are usually added by a third-party plugin, not built in.

## Built-in plugin configuration

DSH's own configurable capabilities:

- **子智能体** (subagents): whether the AI may delegate subtasks; sets depth and count.
- **网页搜索** (web search): which search provider DeepSeek uses when the AI looks things up.
- **Agent 循环** (agent loop): how long the AI keeps going, i.e. its tool-calling style.
- **终端** (terminal): limits on how long a command may run and how much output it may produce.

Open one to change it. The first two matter most: deep subagents make tasks slower and pricier; a wrong search provider makes the AI say it cannot find anything.

## Experimental plugins

Still being tested, off by default, marked **实验性** (experimental). Turn them on yourself; no stability guarantee, and they may change or disappear in later versions.

Common ones:

- **智能体团队** (agent teams): the AI splits work among named teammates and tracks progress on a shared task list.
- **语音输入** (voice input): system speech-to-text on mobile; the first use installs dependencies.
- **自定义插件索引** (custom plugin index): adds a "Discover" tab to the plugin page for your own index.
- **自动授权审查** (auto approval review): before each tool call the model checks your requirements; approved calls run immediately, rejected ones wait for you.
- **变更请求与工作表** (PRs and worksheet): follow linked GitHub PRs in the session sidebar: checks, review comments, diffs.

**更多** (more) holds further experimental items. Experimental switches apply immediately; no restart.

## Installed plugins

Every installed plugin, each with a name, a one-line description, and a switch. Turning one off stops it loading, and anything it contributed (skills, commands, panels) disappears with it.

- **刷新** (refresh): re-read plugin state; use it after installing something outside the app.
- **添加插件** (add plugin): install by name or source.

Installing changes this profile's dependencies and config, and usually needs a restart of DSH before every surface updates. Before installing, understand what the plugin does and whose it is: a plugin can change your interface, read your chats, and call your tools.

## What comes from third parties

Third-party plugins can add entries: an extra page in Settings, a panel in the sidebar, a button above the input box, a tab in the session. Those do not belong in DSH's own docs, because they vanish on another profile or after uninstalling.

How to tell: uninstall or disable the plugin and see whether the entry disappears. Keep this in mind for screenshots, tutorials, and questions, so you do not treat a plugin's UI as the app's own.
