# hn-post-summarizer-2026

This repository contains an AI-generated summary of a public figure's **2026** activity on **Hacker News**, produced with a **LangGraph agent** and automated **GitHub operations via MCP tools**.

---

## What Was Analyzed

- **Platform:** Hacker News  
- **Account handle:** `pg`  
- **Sample:** Latest submissions (stories/comments) retrieved from the public Hacker News API  
- **Outputs:**
  - `summary.md` — Structured markdown report (Overview, Key Themes, Notable Posts, Summary Statistics)
  - `metadata.json` — Analysis metadata (handle, date range, count, top themes)
  - `x_search.py` — Example X API v2 script (included for the course exercise)

---

## How It Was Built

A **LangGraph agent** orchestrates:

- Retrieval tools (Hacker News API tools)
- GitHub repository operations via **GitHub MCP tools**:
  - create_repository
  - create_branch
  - create_or_update_file
  - create_pull_request
  - merge_pull_request

### Workflow

1. Retrieve recent items for a target account.
2. Generate a structured markdown summary using the LLM.
3. Commit artifacts (`summary.md`, `metadata.json`) to GitHub via MCP tools.
4. Create feature branches and open pull requests.
5. Maintain full automation from analysis to repository updates.

---

## How To Replicate This Project

### 1. Create a Python Virtual Environment

Windows:

    python -m venv .venv
    .venv\Scripts\activate

macOS / Linux:

    python -m venv .venv
    source .venv/bin/activate

---

### 2. Install Dependencies

    pip install requests langgraph langchain-core langchain-mcp-adapters typing_extensions

(Install any additional dependencies required by your environment.)

---

### 3. Hacker News Retrieval

Hacker News uses a public API (no authentication required).

You can retrieve:

- Top posts → `hn_top_posts`
- User submissions → `hn_user_posts`
- User profile → `get_user_profile`

---

### 4. Optional: X API Setup (Original Course Exercise)

The file `x_search.py` demonstrates clean X API v2 usage with environment variables.

Set your Bearer Token:

Windows (PowerShell):

    $env:X_BEARER_TOKEN="YOUR_TOKEN"

macOS / Linux:

    export X_BEARER_TOKEN="YOUR_TOKEN"

Then run:

    python x_search.py llm_wizard

Note: Access to X API endpoints depends on your X developer plan and app enrollment level.

---

## Repository Structure

- `summary.md` — AI-generated structured summary
- `metadata.json` — Analysis metadata
- `x_search.py` — Clean X API example script
- `README.md` — Project documentation

---

## License

MIT License (or update as appropriate).
