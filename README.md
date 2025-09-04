# claude-mcp-historical-weather
Demonstration of how to use MCP to connect Claude with a historical weather API

# Prompts

## Initial Prompt

Create a Jupyter notebook (`index.ipynb`) that allows users to compare annual weather statistics for two locations. The notebook should work both when using Colab or when using a local jupyter server.
- Notebook sections
  - Overview
  - Setup
    - Environment Setup - Set up the Jupyter environment with the necessary dependencies so that it will run within Google Colab.
    - Python Package Imports
    - Anthropic API Key - define a helper function that retrieves a user's Anthropic API key. Order of preference for retrieval:
      - API key stored as an environment variable
      - API key stored as a Colab secret
      - prompts the user to enter their key in a safe manner that doesn't store the key in the notebook.
  - Motivation - Do we actually need to extend LLMs? Let's try a simple weather comparison query comparing two locations, **without specifying any tools** that could be used to answer the query.
    - Include code to demonstrate this.
  - Analysis
    - (placeholder)
  - MCP
    - (placeholder)
  - Chat Examples
    - (placeholder)
  - Summary
    - (placeholder)