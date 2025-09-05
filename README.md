# claude-mcp-historical-weather
Demonstration of how to use MCP to connect Claude with a historical weather API

<a target="_blank" href="https://colab.research.google.com/github/tylere/claude-mcp-historical-weather/blob/main/demo.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

## Quick overview of what the demo does and why it's compelling

This notebook demonstrates how to use an MCP tool to allow Claude to access, analyze, and chart historical weather data. 

> "Everybody Talks About the Weather, But Nobody Does Anything About It"

The demo is compelling for a wide range of people because it deals with a relatable topic that everyone has experience with. And with a simple modifications (updating the variable 'my_locations'), a user can explore data that is relevant to their own experience.

## Setup and running instructions

The demo is a Jupyter notebook that can be run in:

- Online using Google Colab using this GitHub link [TODO]
- Locally by cloning the repository and using uv

## Technical approach and key architectural decisions

In order to make this demo run in Google Colab, the entire demo is contained in a single file. However, I authored the Jupyter notebooks in VSCode/Cursor with the Claude Code extension (primarily because of VSCode's git integration and debugging tools). 

Technical Approach:
- Develop Python classes and functions for retrieving, aggregating, and plotting weather data.
- Create a MCP Client class that:
  - registers tools (to provide access to the Python classes/functions)
  - chats with a Claude model.
- Demonstrate the MCP client intergration for a series of weather queries.

Other decisions
- Use the [Open(-Meteo](https://open-meteo.com/) API for access to historical weather data
- Use [caching](https://requests-cache.readthedocs.io/)) to be kind to the free external API
- Use [Vega/Altair](https://altair-viz.github.io/) for creating charts (which is good for exploratory data analysis)
- Use [Pydantic](https://docs.pydantic.dev/) for data validation
- Use [pandas](https://pandas.pydata.org/) for time series analysis

## Why you chose this particular demonstration

There exists a large corpuses of highly relevant data that are not easily accessible on the internet, but rather are "hidden" behind APIs. Relatively few people know how to access these datasets, but by demonstrating how MCP tools I hope to inspire developers to build MCP servers that expand access to these datasets. 

## How this helps developers understand Claude's potential

This demonstration shows how Claude's native ability to respond to data analysis questions can be enhanced by building tools to access data APIs.

## What would make other builders want to learn more

- Clear examples that can be easily modified to provide results for areas that they are personally familiar with.
- Provide links to concepts that are demonstrated, but are not fully explained.

## How you used Claude in creating this demo (prompts, iterations, insights)

I used Claude in a variety of ways:
- Within the VS Code extension, asking Claude Code to draft sections of functionality
  - example: ""
- Research while writing the explanatory text for the notebook.

## What you would add or improve given more time 

- Determine how to support queries that use units that are different than the underlying data. Currently, sunshine duration has to be specified in seconds, rather than the more natural unit of ours.
- Include some mermaid diagrams that illustrate the data flow.
- Relax the requirement of specifying exactly two locations for comparison, so that the tool can be used to display charts for a single location or to compare a longer list (>=3) of locations.
- Separate the MCP Server logic into a stand-only server that can be run outside the notebook, so that other MCP clients can be used to access the functionality.


# Prompts used

## Initial Prompt (to establish the notebook sections)

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