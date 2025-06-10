# 🐍 LangChain SQL Chat Agent — Powered by Groq

Interact with your SQL databases using natural language! This project lets you **chat with SQLite or MySQL databases** via a conversational agent built using **LangChain**, **Streamlit**, and **Groq's ultra-fast LLMs** like **LLaMA3**. Ask questions like "What is the average student score?" or "List top 5 entries from the student table" — and let the agent do the rest.

---

## 📌 Project Overview

This app provides a Streamlit interface to query SQL databases using LLMs. It uses LangChain’s `create_sql_agent` to convert natural language into SQL, execute it, and return the result conversationally.

Key features include:
- 📊 Supports **SQLite** and **MySQL** databases
- ⚡ Uses **Groq LLMs** (like `Llama3-8b-8192`) for fast responses
- 🔧 Secure credential input and dynamic DB connections
- 🦜 Integrates **LangChain SQLDatabaseToolkit** and **AgentType.ZERO_SHOT_REACT_DESCRIPTION**

---

## 🚀 Features

- 🔗 Chat with your database like a human assistant
- 💬 Remembers chat history using Streamlit session state
- 💡 Supports both **local demo DB** (`student.db`) and **external MySQL**
- 🧠 Powered by Groq LLMs for lightning-fast LLM SQL generation
- 📦 Container-ready structure (minimal dependencies)

---

## 🏗️ Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/langchain-sql-groq.git
   cd langchain-sql-groq
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Add your Groq API Key:

   Either set it as an environment variable or input it via the UI:
   ```env
   GROQ_API_KEY=your-key-here
   ```

4. (Optional) Place your local SQLite database as `student.db` in the project root.

---

## 🧪 How to Use

1. Launch the Streamlit app:

   ```bash
   streamlit run app.py
   ```

2. Choose the database type from the sidebar:
   - Use **default SQLite** (`student.db`)
   - Or connect to your own **MySQL** instance

3. Enter your **Groq API Key**

4. Start chatting! Example prompts:
   - *"How many students are enrolled?"*
   - *"Show the names of students who scored above 80"*

---

## 🧠 How It Works

- **LLM Setup**: Uses `ChatGroq` from `langchain_groq` to call models like `llama3-8b-8192`
- **SQL Agent**: Built using LangChain's `create_sql_agent` with `SQLDatabaseToolkit`
- **Database Abstraction**: SQLite or MySQL handled via SQLAlchemy & LangChain's `SQLDatabase`
- **Conversational UI**: Streamlit-based chat with persistent history and callbacks

---

## 💡 LLM Details (Groq)

This project uses `ChatGroq`, a LangChain-compatible wrapper around **Groq’s hosted LLMs**. Supported models include:
- `llama3-8b-8192`
- `mixtral-8x7b-32768`
- `gemma-7b-it`

Groq offers **hardware-accelerated LLM serving** for ultra-low latency responses, ideal for real-time use cases like chat agents.

---

## ⚙️ Technology Stack

- 🐍 Python
- 🦜 LangChain
- ⚡ Groq LLMs (`langchain_groq.ChatGroq`)
- 🗃️ SQLAlchemy (for database interaction)
- 💬 Streamlit (for chat UI)
- 🛠️ AgentType: `ZERO_SHOT_REACT_DESCRIPTION`

---

## 🔒 Security Notes

- **Credentials**: MySQL credentials are taken via sidebar inputs.
- **API Key**: Entered securely in the sidebar. You can alternatively store in `.env`.

---

## 📈 Future Enhancements

- 📊 Add support for Postgres & other RDBMS
- 🧾 Log generated SQL queries
- 🤖 Allow agent to auto-explain SQL results
- 🌍 Deploy via HuggingFace Spaces or Streamlit Cloud
- 🧠 Add metadata introspection for smarter agents

---