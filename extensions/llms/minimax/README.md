# MiniMax Extension for PandasAI

This extension integrates [MiniMax](https://www.minimaxi.com/) with PandasAI, providing MiniMax LLM support.

MiniMax offers powerful large language models with up to 204K context window through an OpenAI-compatible API.

## Installation

```bash
# Using pip
pip install pandasai-minimax

# Using poetry
poetry add pandasai-minimax
```

## Usage

```python
import pandasai as pai
from pandasai_minimax import MiniMax

llm = MiniMax(api_token="your-minimax-api-key")
# Or set MINIMAX_API_KEY environment variable

pai.config.set({"llm": llm})
```

## Supported Models

| Model | Context Window | Description |
|-------|---------------|-------------|
| `MiniMax-M2.5` (default) | 204K | Most capable model |
| `MiniMax-M2.5-highspeed` | 204K | Optimized for speed |

## Configuration

You can pass additional parameters:

```python
llm = MiniMax(
    api_token="your-minimax-api-key",
    model="MiniMax-M2.5-highspeed",
    temperature=0.3,
    max_tokens=2000,
)
```

## Environment Variables

| Variable | Description |
|----------|-------------|
| `MINIMAX_API_KEY` | Your MiniMax API key |
| `MINIMAX_API_BASE` | Custom API base URL (default: `https://api.minimax.io/v1`) |
