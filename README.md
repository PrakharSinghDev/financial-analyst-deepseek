# 📈 MCP-powered Financial Analyst using Local Language Model Support

This project implements a financial analysis agent powered using a locally hosted language model (LLM) like Deepseek‑R1 model. It allows you to interactively query and analyze stock market data, with results displayed either:
- Inside Cursor IDE via MCP, or
- Directly in your terminal using a standalone Python MCP. inside Cursor IDE.

✨ Features:
- Multi‑agent orchestration
- Local LLM inference with Ollama and Deepseek‑R1
- MCP integration conversational analysis
- Data fetching and visualization using yfinance, pandas, and matplotlib

🛠️ Technologies Used:
- Ollama – serves the Deepseek-R1 model locally
- yfinance – stock market data
- pandas – data processing
- matplotlib – chart rendering
- MCP – conversational commands (Cursor IDE or terminal)

---
## Setup and installations

**Install Ollama**

```bash
# Setting up Ollama on linux
curl -fsSL https://ollama.com/install.sh | sh

# Pull the Deepseek-R1 model
ollama pull deepseek-r1
```

**Install Dependencies**

   Ensure you have Python 3.12 or later installed.

   You can use uv to directly install the required dependencies (recommended).
   ```bash
    uv sync
   ```

   Or you can also use pip to install the following dependencies to your local environment.
   ```bash
   pip install ollama mcp pydantic yfinance pandas matplotlib
   ```

---

## 🖥️ Running the project

You have two options for running the MCP server.

**Option A: Using Cursor IDE MCP**

Set up your MCP server as follows:
- Go to Cursor settings
- Select MCP 
- Add new global MCP server.

In the JSON file, add this:
```json
{
    "mcpServers": {
        "financial-analyst": {
         "command": "uv",
            "args": [
                "--directory",
                "absolute/path/to/project_root",
                "run",
                "server.py"
            ]
        }
    }
}
```

You should now be able to see the MCP server listed in the MCP settings.

In Cursor MCP settings make sure to toggle the button to connect the server to the host. Done! Your server is now up and running. 

You can now chat with Cursor and analyze stock market data. Simply provide the stock symbol and timeframe you want to analyze, and watch the magic unfold.

**Option B: Using Python MCP (standalone terminal)**

If you prefer not to use Cursor, simply run the server directly in your terminal:

```bash
python server.py
```
You will see a prompt asking for:
- Stock symbol
- Timeframe (e.g., 3mo, 1y)

Charts will be displayed in a window, and summaries printed in the terminal.

---
**📝Example queries**:
- "Show me Tesla's stock performance over the last 3 months"
- "Compare Apple and Microsoft stocks for the past year"
- "Analyze the trading volume of Amazon stock for the last month"
  
The agent will fetch data, run analysis, and render tables or charts inline.

---
## 🧩 Project Structure Overview
```bash
project_root/
├── server.py         # Main entry point for the agent
├── requirements.txt  # Optional, or use uv's pyproject.toml
└── README.md         # You are reading this!
```
---

**💡 Tips**
- Troubleshooting Ollama:
  Make sure the Ollama daemon is running (ollama serve) before you start the server.

- Customizing the prompt:
  You can easily edit server.py to adjust the prompt format or add more data processing.
  
  ---
## 🤝 Contribution

Contributions are welcome! Please fork the repository and submit a pull request with your improvements.
