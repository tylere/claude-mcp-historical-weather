# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a demonstration project showing how to use MCP (Model Context Protocol) to connect Claude with a historical weather API. The main deliverable is a Jupyter notebook (`index.ipynb`) that allows users to compare annual weather statistics for two locations.

## Project Structure

- `index.ipynb` - Jupyter notebook (currently empty) that will contain the weather comparison demo
- `pyproject.toml` - Python project configuration using uv package manager
- `uv.lock` - Lock file for uv dependencies

## Development Commands

This project uses uv as the package manager. Common commands:

```bash
# Install dependencies
uv sync

# Run the main Python script
uv run python main.py

# Start Jupyter notebook server
uv run jupyter lab
# or
uv run jupyter notebook
```

## Notebook Requirements

The `index.ipynb` notebook should be designed to work in both Google Colab and local Jupyter environments. According to the README, it should include these sections:

1. **Overview** - Project introduction
2. **Setup** 
   - Environment Setup (Colab-compatible)
   - Python Package Imports
   - Anthropic API Key helper function (env var → Colab secret → user prompt)
3. **Motivation** - Demonstration of weather queries without MCP tools
4. **Analysis** - (placeholder)
5. **MCP** - (placeholder) 
6. **Chat Examples** - (placeholder)
7. **Summary** - (placeholder)

## Technical Constraints

- Use Altair for visualizations (not matplotlib)
- Use Pydantic for data validation
  - make data visualizations “aesthetically pleasing”
- Do not use the FastMCP package
- Requires Python 3.10+
- Must work in both Colab and local Jupyter environments

## Code style

- Python
  - Indent with 4 spaces
- Markdown blocks
  - Minimize the use of emojis
  - Use mermaid diagrams for describing data flow

# Security
- Read API keys and other sensitive data from environment variables or Colab secrets
