# claude-mcp-historical-weather
Demonstration of how to use Model Context Protocol (MCP) to connect Claude with historical weather data

## Video Demonstrating the Tutorial

[![Demo Video](https://img.youtube.com/vi/iR_9Tk1elyY/0.jpg)](https://www.youtube.com/watch?v=iR_9Tk1elyY)

https://www.youtube.com/watch?v=iR_9Tk1elyY

## Quick overview of what the demo does

This notebook demonstrates how to use an MCP tool to allow Claude to access, analyze, and chart historical weather data. 

> "Everybody Talks About the Weather, But Nobody Does Anything About It"

The demo is compelling for a wide range of people because it deals with a relatable topic that everyone has experience with. With a simple modification to a Claude query, users can explore data from locations they are familiar with.

## Setup and Running Instructions

The demo is a Jupyter notebook that can be run in two ways:

### Option 1: Google Colab (Recommended for beginners)
<a target="_blank" href="https://colab.research.google.com/github/tylere/claude-mcp-historical-weather/blob/main/demo.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

- No setup required - runs entirely in your browser
- Automatically installs all dependencies
- Requires an Anthropic API key

### Option 2: Local Development
1. Clone the repository:
   ```bash
   git clone https://github.com/tylere/claude-mcp-historical-weather.git
   cd claude-mcp-historical-weather
   ```
2. Install dependencies using `uv`:
   ```bash
   uv sync
   ```
3. Set your Anthropic API key as an environment variable:
   ```bash
   export ANTHROPIC_API_KEY=your_api_key_here
   ```
4. Start VS Code:
   ```bash
   code .
   ```
5. Open the notebook `demo.ipynb` and click "Run All"


## Technical approach and key architectural decisions

In order to make this demo run in Google Colab, the entire demo is contained in a single file.

**Technical Approach:**
- Develop Python classes and functions for retrieving, aggregating, and plotting weather data (this code does not involve the Anthropic API or MCP)
- Create an MCP Client class that:
  - Registers tools to provide access to the Python classes/functions
  - Chats with a Claude model using the registered tools
- Demonstrate the MCP client integration for a series of weather queries

![LLM-MCP Architecture](LLM-MCP.svg)


**Key Technology Choices:**
- Use the [Open-Meteo](https://open-meteo.com/) API for access to historical weather data
  - Use [caching](https://requests-cache.readthedocs.io/) to be kind to the free external API
- Use [Vega/Altair](https://altair-viz.github.io/) for creating charts (which I like for exploratory data analysis)
- Use [Pydantic](https://docs.pydantic.dev/) for data validation
- Use [pandas](https://pandas.pydata.org/) for time series analysis
- Add an option for displaying additional information (`verbose == True`) to help with debugging issues.
