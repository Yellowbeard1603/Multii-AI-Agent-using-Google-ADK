# Multi Agent AI Manager

This project is a modular multi-agent system built in Python, designed to delegate and manage tasks across specialized AI agents. Each agent is responsible for a specific domain, such as stock analysis, news summarization, or generating nerdy jokes. The system leverages the [google-adk](https://pypi.org/project/google-adk/) framework for agent orchestration and tool integration.

## Project Structure

```
manager/
├── agent.py            # Root manager agent definition
├── .env                # Environment variables (API keys, etc.)
├── tools/
│   └── tools.py        # Shared utility tools (e.g., get_current_time)
└── sub_agents/
    ├── funny_nerd/
    │   └── agent.py    # Funny nerd joke agent
    ├── news_analyst/
    │   └── agent.py    # News analysis agent
    └── stock_analyst/
        └── agent.py    # Stock price analysis agent
requirements.txt        # Python dependencies
README.md               # Project documentation
.gitignore              # Git ignore file
```

## Agents

- **Manager Agent** (`manager/agent.py`):  
  Delegates tasks to sub-agents and manages tool access.

- **Stock Analyst** (`manager/sub_agents/stock_analyst/agent.py`):  
  Retrieves and reports current stock prices using Yahoo Finance.

- **News Analyst** (`manager/sub_agents/news_analyst/agent.py`):  
  Searches and summarizes news articles using Google Search.

- **Funny Nerd** (`manager/sub_agents/funny_nerd/agent.py`):  
  Tells nerdy jokes about programming, science, and more.

## Tools

- **get_current_time** (`manager/tools/tools
  Returns the current date and time.

- **google_search**:  
  Provided by `google.adk.tools` for searching news.

## Setup

1. **Clone the repository**  
   ```sh
   git clone <repo-url>
   cd Multi Agent

2. **Installl dependencies**
   ```sh
   pip install -r requirements.txt


3. Configure environment variables
  Edit manager/.env and set your Google API key:
```sh
    GOOGLE_GENAI_USE_VERTEXAI=0
    GOOGLE_API_KEY=your-google-api-key
```
Running the Agent System
Once setup is complete, you can run the system using the ADK CLI:

▶️ Run with ADK CLI
    cd manager
    adk run agent
    
🌐 Run with ADK Developer UI (optional)

Launch a browser-based interface to interact with and visualize the agent workflow:

adk web

This opens the ADK Dev UI in your browser.

Select your agent and start a conversation (e.g., "Tell me a nerdy joke" or "What’s the latest in the stock market?").


Usage
Import and instantiate the root_agent from manager/agent.py in your application.
Interact with the manager agent; it will delegate tasks to the appropriate sub-agent or tool.
Extending


To add a new agent:

Create a new folder under manager/sub_agents/.
Implement your agent logic in agent.py.
Register the agent in manager/agent.py as a sub-agent or tool.

Note: This project uses the google-adk framework and requires a valid Google API key for some features.
