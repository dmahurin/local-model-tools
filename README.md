# Local Model Tools

This repository contains a small set of helper scripts for running
local language model servers and clients from the command line.

## Tools

### `run-codex-cli`
Launches the local LLM server (if it isn't already running) and then
executes the `@openai/codex` CLI against it.

Run interactively:
```bash
run-codex-cli
```

Run non-interactively:
```bash
run-codex-cli 'Generate and commit a README.md for this project'
```

### `start-llm-server`
Starts the LLM server via `llama-server`. Uses gpt-oss-20b by default.

Usage:
```bash
start-llm-server
```

### `run-llm-cli`
Convenience wrapper around `llama-cli`. Uses gpt-oss-20b by default.

Run interactively:
```bash
run-llm-cli
```

Run non-interactively:
```bash
run-llm-cli "How far away is the Moon?"
```

### `run-vlm-cli`
Run VLM model using `llama-mtmd`. Uses gemma-3-4b-it by default.

Run non-interactively:
```bash
run-vlm-cli image.jpg "Describe this image."
```
