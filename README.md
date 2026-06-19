# Awesome LLM API 🤖

> A curated list of awesome Large Language Model APIs (Updated June 2026)
> Pricing, benchmarks, and comparison for GPT-5.5, Claude Opus 4.8, Gemini 3.5 Pro, DeepSeek V4-Pro and more.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![Updated](https://img.shields.io/badge/Updated-June%202026-blue)]()

## 📊 Quick Comparison (June 2026)

| Model | Provider | Context | Input ($/1M) | Output ($/1M) | Best For |
|-------|----------|---------|--------------|---------------|----------|
| **GPT-5.5** | OpenAI | 1M | $5 | $30 | Frontier reasoning, coding |
| **GPT-5.4** | OpenAI | 256K | $3 | $15 | General purpose |
| **GPT-5.4-mini** | OpenAI | 128K | $0.15 | $0.60 | Fast, cheap |
| **Claude Opus 4.8** | Anthropic | 1M | $5 | $25 | Complex analysis, writing |
| **Claude Sonnet 4.6** | Anthropic | 300K | $3 | $15 | Balanced |
| **Claude Haiku 4.5** | Anthropic | 200K | $1 | $5 | Fast, affordable |
| **Gemini 3.5 Pro** | Google | 2M | ~$15 | ~$60 | Long context, multimodal |
| **Gemini 3.5 Flash** | Google | 1M | $1.5 | $9 | Fast multimodal |
| **DeepSeek V4-Pro** | DeepSeek | 1M | $0.435 | $0.87 | Best value, coding |
| **DeepSeek V4-Flash** | DeepSeek | 1M | $0.14 | $0.28 | Ultra-cheap |

## 🏆 Best Model by Use Case

| Use Case | Recommended Model | Why |
|----------|-------------------|-----|
| **Complex reasoning** | GPT-5.5 / Claude Opus 4.8 | Top benchmarks |
| **Coding** | GPT-5.5 / DeepSeek V4-Pro | Best code generation |
| **Long documents** | Gemini 3.5 Pro | 2M token context |
| **Multimodal (image/video)** | Gemini 3.5 Pro / GPT-5.5 | Native multimodal |
| **Budget / high volume** | DeepSeek V4-Flash | 36x cheaper than GPT-5.5 |
| **Fast responses** | Claude Haiku 4.5 / GPT-5.4-mini | Low latency |
| **Chinese language** | DeepSeek V4-Pro | Best Chinese capability |

## 💰 Cost Optimization Tips

1. **Use the cheapest model that works** — Don't use GPT-5.5 for simple tasks
2. **Enable context caching** — Save 90% on repeated prompts
3. **Use a unified API** — [EnlyAI](https://enlyai.com) lets you switch models with one key
4. **Batch requests** — Reduce per-request overhead
5. **Set max_tokens** — Avoid over-generating

## 🔌 API Providers

### Direct Providers

| Provider | Models | API Format | Docs |
|----------|--------|------------|------|
| [OpenAI](https://platform.openai.com) | GPT-5.5, GPT-5.4, GPT-5.4-mini | OpenAI | [docs](https://platform.openai.com/docs) |
| [Anthropic](https://console.anthropic.com) | Claude Opus 4.8, Sonnet 4.6, Haiku 4.5 | Anthropic / OpenAI | [docs](https://docs.anthropic.com) |
| [Google AI](https://aistudio.google.com) | Gemini 3.5 Pro, Flash | Google / OpenAI | [docs](https://ai.google.dev) |
| [DeepSeek](https://platform.deepseek.com) | V4-Pro, V4-Flash | OpenAI / Anthropic | [docs](https://api-docs.deepseek.com) |

### Unified / Aggregation Platforms

| Platform | Models | API Format | Free Credits |
|----------|--------|------------|--------------|
| **[EnlyAI](https://enlyai.com)** ⭐ | GPT-5.5, Claude, Gemini, DeepSeek + 100 more | OpenAI | ✅ Yes |
| OpenRouter | 200+ models | OpenAI | ❌ |
| Together AI | Open source models | OpenAI | $5 |

> 💡 **Recommendation**: [EnlyAI](https://enlyai.com) offers one API key for all models with OpenAI-compatible interface. [Get free credits →](https://enlyai.com)

## 📝 Code Examples

### Python (OpenAI SDK)

```python
from openai import OpenAI

# Direct OpenAI
client = OpenAI(api_key="sk-xxx")

# Via EnlyAI (unified, all models)
client = OpenAI(
    api_key="your-enlyai-key",
    base_url="https://api.enlyai.com/v1"
)

# Same code, just change model name!
for model in ["gpt-5.5", "claude-opus-4-8", "gemini-3.5-pro", "deepseek-v4-pro"]:
    resp = client.chat.completions.create(
        model=model,
        messages=[{"role": "user", "content": "Hello!"}]
    )
    print(f"{model}: {resp.choices[0].message.content}")
```

### cURL

```bash
# Direct OpenAI
curl https://api.openai.com/v1/chat/completions \
  -H "Authorization: Bearer sk-xxx" \
  -d '{"model": "gpt-5.5", "messages": [{"role": "user", "content": "Hi"}]}'

# Via EnlyAI (unified)
curl https://api.enlyai.com/v1/chat/completions \
  -H "Authorization: Bearer your-enlyai-key" \
  -d '{"model": "gpt-5.5", "messages": [{"role": "user", "content": "Hi"}]}'
```

## 📚 Learning Resources

- [EnlyAI Blog](https://enlyai.com/blog/) — 30+ tutorials on LLM API usage
- [EnlyAI Quickstart](https://github.com/LancerXiao/enlyai-quickstart) — Code examples
- [OpenAI Cookbook](https://cookbook.openai.com) — Official examples
- [Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook) — Claude examples

## 🔄 Migration Guides

### OpenAI → EnlyAI (2 lines)

```python
# Before
client = OpenAI(api_key="sk-openai-xxx")

# After (access ALL models)
client = OpenAI(
    api_key="your-enlyai-key",
    base_url="https://api.enlyai.com/v1"
)
```

### DeepSeek → EnlyAI

```python
# Before
client = OpenAI(api_key="deepseek-xxx", base_url="https://api.deepseek.com")

# After
client = OpenAI(api_key="your-enlyai-key", base_url="https://api.enlyai.com/v1")
```

## 📈 Benchmarks (June 2026)

| Benchmark | GPT-5.5 | Claude Opus 4.8 | Gemini 3.5 Pro | DeepSeek V4-Pro |
|-----------|---------|-----------------|----------------|-----------------|
| MMLU | 92.1% | 91.8% | 90.5% | 88.3% |
| HumanEval | 94.2% | 93.1% | 89.7% | 80.6% |
| MATH-500 | 96.8% | 95.2% | 93.1% | 97.3% |
| GPQA | 78.5% | 76.2% | 72.8% | 68.4% |

## 🤝 Contributing

Contributions welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

## ⭐ Star History

If this list helps you, please give it a star!

---

<p align="center">
  Maintained by <a href="https://enlyai.com">EnlyAI</a> — One API key for all LLMs<br>
  <a href="https://enlyai.com">Get started →</a>
</p>
