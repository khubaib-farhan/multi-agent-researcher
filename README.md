# Multi-Agent AI Content Researcher

A multi-agent AI pipeline that uses **CrewAI** and **Google Gemini 2.5 Flash** to automatically plan, write, and edit high-quality blog articles on any topic — end to end, with no human intervention.

---

## 📖 Description

This notebook demonstrates how to build a collaborative multi-agent system where three specialized AI agents work together in sequence to produce a publication-ready blog post. Given just a topic, the crew researches, writes, and edits a full article autonomously.

The example run in this notebook generates a comprehensive article on **"AI in Industrial Safety Monitoring"**.

---

## How It Works

The pipeline consists of three agents, each with a distinct role:

| Agent | Role | Responsibility |
|---|---|---|
| **Content Planner** | Strategist | Researches the topic, identifies trends, defines the target audience, builds a structured outline, and selects SEO keywords |
| **Content Writer** | Writer | Uses the planner's outline to draft a compelling, well-structured blog post in Markdown |
| **Content Editor** | Editor | Proofreads for grammar, ensures journalistic balance, removes controversial content, and polishes the final output |

The agents are orchestrated sequentially using CrewAI's `Crew` and `Task` abstractions. Each agent passes its output to the next, forming a clean production pipeline.

---

## Tech Stack

- **[CrewAI](https://github.com/joaomdmoura/crewAI)** — Multi-agent orchestration framework
- **Google Gemini 2.5 Flash** — LLM powering all three agents
- **Python 3** — Runtime environment
- **Google Colab** — Notebook execution environment

---

## Getting Started

### Prerequisites

- A **Google Gemini API key** (get one at [Google AI Studio](https://aistudio.google.com/))
- Python 3.8+
- Google Colab (recommended) or a local Jupyter environment

### Installation

```bash
pip install "crewai[google-genai]"
```

### Setup

1. Store your Gemini API key as a Colab secret named `GEMINI_API_KEY`, or set it as an environment variable:

```python
import os
os.environ["GEMINI_API_KEY"] = "your-api-key-here"
```

2. Open the notebook and run all cells in order.

### Usage

To generate an article on a custom topic, change the `inputs` parameter in the final cell:

```python
result = crew.kickoff(inputs={"topic": "Your Topic Here"})
```

The final output is a fully formatted Markdown blog post, rendered directly in the notebook.

---

## Project Structure

```
multi_agent_researcher.ipynb
│
├── 1. Install dependencies
├── 2. Configure Gemini LLM
├── 3. Define Agents
│   ├── Content Planner
│   ├── Content Writer
│   └── Content Editor
├── 4. Define Tasks
│   ├── Plan Task
│   ├── Write Task
│   └── Edit Task
├── 5. Assemble the Crew
└── 6. Run & Display Output
```

---

## Example Output

The notebook includes a full sample run generating a detailed article on **"AI in Industrial Safety Monitoring"**, covering:
- Predictive maintenance and hazard detection
- Computer vision for PPE compliance
- AI-powered wearables and autonomous inspection drones
- Ethical considerations and future outlook

---

## 📝 License

This project is open for personal and educational use. Feel free to fork and adapt it for your own multi-agent workflows.
