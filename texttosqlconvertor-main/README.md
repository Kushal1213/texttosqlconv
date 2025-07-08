# 🌟 IntelliSQL: Intelligent SQL Querying with LLMs Using Gemini Pro

IntelliSQL is a powerful and intuitive application that bridges the gap between natural language and SQL. It empowers users—whether SQL novices or seasoned analysts—to generate, optimize, and execute SQL queries using natural language input, all powered by Google's Gemini Pro LLM and a sleek Streamlit-based interface.


## Features
### Intelligent Query Assistance
- Converts natural language questions into SQL queries.

- Offers suggestions and syntax help.

- Optimizes queries for better performance.

### Data Exploration and Insights
- Enables users to query databases conversationally.

- Reveals hidden trends, patterns, and summaries.

- Perfect for analysts and data scientists.

## Tech Stack
- Frontend: Streamlit (UI)

- Backend: Python, Google Gemini Pro API, SQLite3

- Database: sqlite3 with data.db for demonstration

## Project Flow
1. User inputs a question via the UI.

2. Input is sent to the backend via Google API Key.

3. Gemini Pro model processes the input and generates SQL.

4. SQL is executed on a SQLite3 database.

5. Results are displayed to the user on the UI.

## Project Structure
```
IntelliSQL/
|
|-app.py       #Main application file (streamlit UI + model interface)
|-sql.py       #Script to create and populate the demo SQLite database
|-.env         #Stores Google API key securely 
|-requirements.txt  #python dependencies
|-data.db       #SQLite demo database

```
## Prerequisites
You should be familiar with the following:

- Basics of Generative AI and NLP

- Streamlit web apps

- SQL and relational databases

- Google Gemini API

- Python and SQLite3


Setup Instructions
### 1. Clone the repository:
```
git clone https://github.com/your-username/IntelliSQL.git
cd IntelliSQL
```
### 2. Install Dependencies:
```
pip install -r requirements.txt
```
### 3. Configure Environmnet:
Create a  `.env` file and add your Google API key:
```
GOOGLE_API_KEY=your_api_key_here
```
Generate an API key from: [here](https://aistudio.google.com/app/apikey).
### 4. Initialize Database:
```
python sql.py
```

### 5.Launch the App:
```
streamlit run app.py
```
## How it Works
### Prompting Genimi Pro
The model is instructed using a carefully constructed prompt to English questions like:
- *"How many students are there?"*
- *"list all the students working at INFOSYS."*
```
SELECT COUNT(*) FROM STUDENTS;
SELECT * FROM STUDENTS WHERE COMPANY="INFOSYS";
```
### Functions
- `get_response(que, prompt)` - interacts with Gemini to generate SQL
- `read_query(sql, db) ` - Executes SQL on the database and returns the result
 
## Resources and References
[Gemini API Docs](https://ai.google.dev/gemini-api/docs/get-started/python)
[Streamlit Docs](https://docs.streamlit.io/)
[SQLite Docs](https://www.sqlite.org/docs.html)

