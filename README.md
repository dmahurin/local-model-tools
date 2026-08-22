# Local Model Tools

This repository contains a small set of helper scripts for running
local language model servers and clients from the command line.

## Tools

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
