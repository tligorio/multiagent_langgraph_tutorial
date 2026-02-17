# Multi-Agent Research Assistant with LangGraph
#### Tiziana Ligorio for *AI Agents - CSCI 395.32* taught at Hunter College of The City University of New York

In this tutorial, we build a research assistant that uses multiple agents to streamline the process of finding and filtering academic research papers. This demonstrates a multi-agent system using the LangGraph framework.

## System Architecture

The system consists of four specialized agents:

1. **Search Agent** — Queries Google Scholar and/or arXiv to find academic papers matching the user's query
2. **Filter Agent** — Evaluates the relevance of retrieved papers and adds relevant ones to the filtered papers list in the state
3. **Query Refinement Agent** — Refines the search query to improve results when the current query yields insufficient relevant papers
4. **Supervisor Agent** — Decides whether the workflow should finalize (enough relevant papers found) or continue refining the query

## Workflow

<img src="./images/multiagent.png" alt="Multiagent System - local" width="50%">

## Stopping Criteria

The Supervisor Agent finalizes the workflow when:
- At least **3 papers** have been identified with a **relevance score ≥ 0.7**

Otherwise, the Query Refinement Agent generates an improved query and the search process iterates.

## Getting Started

### Option 1: Run in Google Colab (Recommended for quick start)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tligorio/multiagent_langgraph_tutorial/blob/main/Multiagent_LangChain.ipynb)

Click the badge above to open the notebook directly in Google Colab.

### Option 2: Run Locally

For local installation, clone this repository and follow the instructions in [SETUP.md](SETUP.md).
