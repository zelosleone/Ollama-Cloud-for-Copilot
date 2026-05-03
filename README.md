# Ollama Cloud for Copilot

VS Code extension that puts Ollama Cloud models in Copilot Chat.

```
https://github.com/zelosleone/Ollama-Cloud-for-Copilot
```

## Use

1. Install the VSIX.
2. `Ollama Cloud: Set API Key`
3. Pick a model in Copilot Chat.

The key is stored in VS Code secret storage.

## How it works

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

## Commands

`Ollama Cloud: Set API Key` · `Clear API Key` · `Show Registered Models` · `Show Logs`

## License

MIT
