# AI Travel Planner with Multi-Agent Orchestration

Traditional AI systems often rely on a single model to handle multiple tasks, which can lead to increased complexity, reduced accuracy, and limited scalability. This project demonstrates a modern alternative: a **multi-agent architecture** powered by **Agent-to-Agent (A2A) collaboration**, where specialized agents work together through structured communication protocols.

---

## Overview

This project implements an **AI-powered travel planner** using:

- **Python**
- **Google Gemini**
- **Agent Development Kit (ADK)**

Instead of a monolithic model, the system is composed of multiple **specialized agents**, each responsible for a specific domain:

- Flights  
- Hotels  
- Attractions  
- Weather  

Each agent integrates with external data sources (e.g., OpenWeatherMap or mock datasets) and operates independently while collaborating with others.

---

## Architecture

At the core of the system is a **root coordinator agent** that orchestrates communication between all agents using the **A2A protocol**.

### Key Design Principles

- **Modularity**: Each agent is independently developed and replaceable  
- **Scalability**: New agents can be added without affecting existing ones  
- **Reliability**: Task distribution improves accuracy and fault isolation  
- **Maintainability**: Clear separation of concerns across agents  

### How It Works

1. The user interacts via a command-line interface (CLI)
2. The root agent interprets the request
3. It delegates subtasks to relevant specialized agents
4. Agents communicate via structured A2A protocols
5. Results are aggregated and returned to the user

### Features

* Multi-agent orchestration using A2A communication
* Agent capability definitions via agent cards
* Integration with external APIs and mock datasets
* Distributed task execution across domain-specific agents
* CLI-based interaction for end-to-end travel planning

## Use Cases

While this project focuses on travel planning, the architecture is applicable to:

* AI assistants for enterprise workflows
* Healthcare data coordination systems
* Customer support automation
* Any complex system requiring coordinated decision-making across multiple agents

## Summary

This project demonstrates how multi-agent collaboration can outperform traditional single-agent systems in real-world AI applications by improving scalability, modularity, and reliability.

## Running the Project

This project uses a multi-agent setup with CLI, web UI, and API server components. Follow the steps below to run everything locally.

### Prerequisites
- Python 3.10+
- OpenWeatherMap API key
- Gemini API key

### Step-by-Step Instructions

Replace your API keys in .env and agents/weather_agent/.env files.

You’ll need 3 separate terminals running simultaneously.

* Terminal 1 — Run CLI Interface

  Start the command-line interface:
  
  `python cli.py`
  
  This allows you to interact with the travel planner via terminal.

* Terminal 2 — Start ADK Web UI

  Launch the web interface:
  
  `adk web`
  
  Opens a browser-based UI for interacting with agents
  Useful for visualizing agent workflows and debugging

* Terminal 3 — Start API Server (A2A Enabled)

  Run the agent API server with Agent-to-Agent (A2A) communication:
  
  `adk api_server --a2a --port 8001 --host 0.0.0.0 agents`
  
  Enables multi-agent orchestration
  Hosts agents under the agents/ directory
  Exposes APIs at: http://localhost:8001

### Verifying Setup

Once all services are running:

* CLI should accept queries
* Web UI should be accessible (typically http://localhost:3000 or similar)
* API server should respond on port 8001

### Testing

* Start by typing queries such as:
    * Plan me a trip going from New York to London in March for 2 days.
    * Plan me a 3-day trip to Paris.
    * What hotels are available in Rome under $100?
    * Show me flights from New York to London on October 10.
    * What will the weather be like in Paris next week?
    * Plan me a trip going from New York to London starting from 01-01 and then returning on 01-04.
* The CLI will display responses from the root agent that combine information from the relevant sub-agents.
* Type exit or quit to close the CLI session.
