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
| GLM | On / Off | `thinking.type` + `clear_thinking` |
| Kimi (k2.6, k2.7-code, k3) | On / Off | `thinking.type` |
| Qwen 3.5 | Off / Low / Medium / High | `reasoning_effort` |
| GPT-OSS | Low / Medium / High | `think` level (cannot fully disable) |
| Gemma 4, Nemotron 3, MiniMax | On / Off | `thinking.type` / `think` boolean |

Models without a schema (Mistral Large 3, etc.) still work — they just don't have thinking controls in the picker.

## Commands

`Ollama Cloud: Set API Key` · `Clear API Key` · `Show Registered Models` · `Show Logs`

## License

MIT
