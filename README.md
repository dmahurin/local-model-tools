# Local Model Tools

This repository contains a small set of helper scripts for running
local language model servers and clients from the command line.

## Tools

### `local-model-config`
Interactively configures the models used by the local tools. Its menu shows the
current LLM server, LLM, and VLM selections and opens a selection screen for
each category. Settings are saved as `NAME=VALUE` entries in
`~/.local-model-config.env`.

```bash
local-model-config
```

### `local-codex`
Executes the `@openai/codex` CLI against the local LLM server.

Run interactively:
```bash
local-codex
```

Run non-interactively:
```bash
local-codex 'Generate and commit a README.md for this project'
```

### `start-llm-server`
Starts the LLM server via `llama-server`. Uses gpt-oss-20b by default.

Usage:
```bash
start-llm-server
```

To update only the server model selection in `~/.local-model-config.env`:
```bash
start-llm-server -config
```

The server selection is stored as a comma-separated `LLM_SERVER_MODELS` value
containing full model identifiers. All tools default to
`unsloth/gemma-3-4b-it-GGUF:Q4_K_M` when no configuration has been saved.

### `local-llm`
Convenience wrapper around `llama-cli`. Uses gpt-oss-20b by default.

Run interactively:
```bash
local-llm
```

Run non-interactively:
```bash
local-llm "How far away is the Moon?"
```

### `local-vlm`
Run VLM model using `llama-mtmd`. Uses gemma-3-4b-it by default.

Run non-interactively:
```bash
local-vlm image.jpg "Describe this image."
```

### `image2image`
Edits an existing image based on a text prompt. Uses `mflux` with the `flux2-klein-4b-mlx-4bit` model to perform image-to-image generation.
Requires `imagemagick` (`identify` and `convert`) and `mflux-generate-flux2-edit`.

Usage:
```bash
image2image "A futuristic cyberpunk version of this cat" cat.png
```
