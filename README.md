# Healthcare-ChatBot

# Healthcare Chatbot on Azure

An AI-powered healthcare chatbot built using **Azure**, **Python**, **LangGraph**, and **CopilotKit**.  
This project uses a **multi-agent workflow** to handle healthcare conversations safely and intelligently, including intent classification, emergency detection, care guidance, clarification handling, and fallback error management.

## Features

- Multi-agent healthcare chatbot using **LangGraph**
- Built with **Python**
- Integrated with **Azure OpenAI**
- UI/copilot integration using **CopilotKit**
- Observability and tracing with **Langfuse**
- Emergency-aware healthcare routing
- Clarification-based conversation flow
- Safe fallback with error handling
- Modular and extensible architecture

## Architecture

The chatbot is implemented as a **graph-based agent workflow** where each node is responsible for a specific task.

### Agents

#### 1. Welcome Agent
Handles the initial greeting and starts the conversation flow.

#### 2. Intent Classifier Agent
Classifies the user query and decides which agent should handle the request next.

#### 3. Medical Emergency Agent
Detects emergency symptoms or high-risk medical scenarios and responds with urgent safety guidance.

#### 4. Care Navigator Agent
Guides the user to the most appropriate care option based on symptoms or request type.

#### 5. Ask Clarification Agent
Requests more details when the user input is vague, incomplete, or ambiguous.

#### 6. Error Handler Agent
Handles unexpected issues, failures, or invalid states in the workflow.

## Tech Stack

- **Cloud:** Azure
- **Language:** Python
- **LLM Orchestration:** LangGraph
- **Copilot UI:** CopilotKit
- **Model Provider:** Azure OpenAI
- **Observability:** Langfuse
- **Backend:** FastAPI
- **Deployment:** Azure App Service / Azure Container Apps / AKS

## Observability

This project uses **Langfuse** for end-to-end LLM observability.

Langfuse helps with:

- Tracing agent execution paths
- Monitoring prompt and response quality
- Tracking latency and token usage
- Debugging node-level failures
- Evaluating workflow performance

## Project Structure

```bash
healthcare-chatbot/
│
├── app/
│   ├── agents/
│   │   ├── welcome_agent.py
│   │   ├── intent_classifier.py
│   │   ├── medical_emergency_agent.py
│   │   ├── care_navigator_agent.py
│   │   ├── ask_clarification_agent.py
│   │   └── error_handler_agent.py
│   │
│   ├── graph/
│   │   └── healthcare_graph.py
│   │
│   ├── services/
│   │   ├── azure_openai_service.py
│   │   └── langfuse_service.py
│   │
│   ├── api/
│   │   └── routes.py
│   │
│   └── main.py
│
├── frontend/
│   └── copilotkit-ui/
│
├── requirements.txt
├── .env.example
└── README.md
```

