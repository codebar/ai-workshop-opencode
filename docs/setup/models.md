# Models — free opencode zen vs. GPT / Claude

opencode itself does not ship a proprietary model. It routes to **75+ LLM providers** via [Models.dev](https://models.dev/). The fastest way to try opencode without a credit card is **opencode zen** — opencode's hosted gateway with a rotating free tier alongside paid models.

This page focuses on the **free zen models** because the workshop is about _trying the tool_. We compare them to the dominant paid models from OpenAI and Anthropic so you know when it is worth reaching for a paid key.

## Free opencode zen models

| Model | Best for |
| --- | --- |
| **Big Pickle** | General agentic coding — good default first pick |
| **DeepSeek V4 Flash Free** | Fast iteration, lightweight edits |
| **MiMo V2.5 Free** | Reasoning-heavy refactors |
| **North Mini Code Free** | Snappy code-completion-style tasks |
| **Nemotron 3 Ultra Free** | Long-context analysis when latency is not critical |

> The free roster rotates. Always confirm what is currently free at <https://opencode.ai/docs/zen/> before the workshop.

## Free zen vs. GPT / Claude — at a glance

| Dimension | Free zen models | GPT-5.x | Claude 4.x (Opus / Sonnet) |
| --- | --- | --- | --- |
| **Cost** | $0 (rate-limited, may change) | ~$1.25–$10 / 1M in, ~$10–$30 / 1M out | ~$3–$15 / 1M in, ~$15–$75 / 1M out |
| **Code quality** | Good for everyday edits; weaker on subtle refactors | Excellent across breadth | Excellent, especially on multi-file refactors |
| **Tool-use reliability** | Usable but expect occasional retries | Very reliable | Very reliable |
| **Context window** | Varies per model (typically 32k–128k) | 200k+ | 200k+ |
| **Latency** | Fast (DeepSeek Flash) to slower (Nemotron Ultra) | Medium | Medium–slow on Opus, medium on Sonnet |
| **Privacy** | Hosted by opencode zen | Hosted by OpenAI | Hosted by Anthropic |
| **Local option** | Pair with [Ollama](https://ollama.com/) / [LM Studio](https://lmstudio.ai/) for fully-local runs | No | No |

## How to switch

Two ways to change model from inside opencode:

- Press `f2` (recent) or `<leader>m` (`ctrl+x` then `m`) to open the picker. See [`commands.md`](commands.md).
- Set a default in `opencode.json`:

```json
{
  "model": "opencode-zen/big-pickle"
}
```

Format is always `provider_id/model_id`. To pin a paid model you would write, for example, `"anthropic/claude-sonnet-4-5"` or `"openai/gpt-5"`.

## Workshop guidance

- **Start free.** Use `big-pickle` for the challenge to feel the loop without burning a paid quota.
- **Compare deliberately.** During challenge development, run the same prompt on different free models — read both diffs, discuss.
- **Watch the rate limits.** Free tiers throttle quickly with multiple students hitting them. Have one paid key ready as a backup.
