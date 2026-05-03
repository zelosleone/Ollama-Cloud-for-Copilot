# Ollama Cloud for Copilot

VS Code extension that puts Ollama Cloud models in Copilot Chat.

```
https://github.com/zelosleone/Ollama-Cloud-for-Copilot
```

## Use

1. Install the VSIX.
2. `Ollama Cloud: Set API Key`
3. Pick a model in Copilot Chat.

The key is stored in VS Code secret storage. You can also set `ollamaCloud.apiKey` or `OLLAMA_API_KEY`.

## How it works

Ships with a bundled model snapshot so the provider always has models to show. Without that VS Code hides providers with zero models in the picker.

When you open the provider dropdown for the first time, it prompts for an API key. Once you have a key, it fetches the live model list from `https://ollama.com/v1/models` in the background (throttled, so repeated picker queries don't spam the API). Falls back to `https://ollama.com/api/tags` if v1 is down.

Only models known to support thinking get configuration controls in the picker:

| Family | Controls | What it sends |
|---|---|---|
| DeepSeek V4 (flash/pro) | Off / High / Max | `thinking.type` + `reasoning_effort` |
| DeepSeek v3.1 | On / Off | `think` boolean |
| GLM | On / Off | `thinking.type` + `clear_thinking` |
| Kimi (k2.5, k2.6, k2-thinking) | On / Off | `thinking.type` |
| Qwen (3.5, 3-next, 3-coder, 3-vl) | Off / Low / Medium / High | `reasoning_effort` |
| GPT-OSS | Low / Medium / High | `think` level (cannot fully disable) |
| Cogito, Nemotron 3, Ministral | On / Off | `think` boolean |

Models without a schema (DeepSeek v3.2, Gemma, MiniMax, Mistral, RNJ, Devstral, etc.) still work — they just don't have thinking controls in the picker.

~40 live models (May 2026): DeepSeek, GLM, Kimi, Qwen, GPT-OSS, Gemma, Gemini, Mistral, Ministral, MiniMax, Nemotron, Devstral, Cogito, RNJ. List refreshes at startup, no extension update needed for new models.

## Commands

`Ollama Cloud: Set API Key` · `Clear API Key` · `Show Registered Models` · `Show Logs`

## Requires

VS Code 1.118+, GitHub Copilot, Ollama Cloud API key.

## License

MIT
