# Models and reasoning effort

Use a DeepSeek account or an API key, or connect any OpenAI-compatible service. Credentials are kept by the app in this machine's `.dsh\.credentials.yaml`, never in chat content; models and keys are configured in Settings, see "The model page in Settings" below.

## Switching model and reasoning effort

Click **选择模型** (select model) under the input box to open the "模型与推理等级" popup:

- At the top is **搜索模型…** (search models); type a name to filter.
- Models are grouped by provider, e.g. **DeepSeek 账号**, **DeepSeek**, **Third-Party**. The dot marks the current model.
- Click a model to switch immediately and close the popup.
- The bottom row is **推理等级** (reasoning effort) with the current level, e.g. `High`. Click to pick a level; which levels exist depends on the provider and model.

The button under the box shows the current state, e.g. `DeepSeek-V4.1-Flash High`: model first, effort after. Switching affects only this chat's next generations; earlier content is not rewritten.

## Reasoning effort

Reasoning effort decides how long the model thinks before answering. Typical levels:

- **No thinking**: answer directly, fastest. Only appears if the model can turn thinking off.
- **Low / Medium / High**: higher means longer thinking, usually slower and more expensive.
- **Higher tiers** (e.g. `xhigh`, `max`): only some models offer them.

There is no universal rule: code, math, and long analysis want higher; chat, rewriting, or looking up a name want lower or no thinking. When unsure, keep the default.

## Defaults for new chats

A new chat opens with the default model from configuration (`agent-default-model`). Changing the model inside a chat affects that chat only; to change the default for all new chats, edit the config file and restart the app. See "Open config file" in [Settings](08-settings.md).

## The model page in Settings

<!-- nav: settings,models -->
`Account menu › Settings › Models`

The page opens with "填入各提供商的 API 密钥即可使用其模型。" (fill in each provider's API key to use its models), then lists providers:

- **DeepSeek 账号**: when signed in, shows a green dot and "已登录". Uses the account directly, no key needed.
- **DeepSeek**: API key for DeepSeek's open platform. **Edit** changes the key.
- **Third-Party**: providers from config or that you added, marked "自定义" (custom), with **Edit** and **Delete**.
- **+ 添加模型提供商** (add model provider): add a provider with name, API URL, API key, then pick or type model IDs.

Deleting a provider removes its models from the picker at once. Chats using it must switch models to continue.

## Where models and credentials live

Configuration is in the profile directory, not the install directory: `package.json` and `cordis.patch.yml` under `%USERPROFILE%\.dsh\profiles\desktop\`, with API keys in `.dsh\.credentials.yaml`. Quit the app before editing these files and restart afterwards; editing while it runs can leave the app unable to read its config.

If you forget which providers you added, check the live config via "Open config file" in [Settings](08-settings.md).
