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
