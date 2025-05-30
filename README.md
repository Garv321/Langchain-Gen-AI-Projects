# Langchain Demo with LLAMA2 and Google GEMMA API

An API server built with FastAPI that integrates multiple LLMs using Langchain.  
Includes a Streamlit frontend to generate essays and poems using Google GEMMA and LLAMA2 models.

---

## Features

- FastAPI backend serving endpoints powered by Langchain with:
  - Google Generative AI (`gemma-3-12b-it` model)
  - Groq-powered ChatGroq model (`gemma2-9b-it`)
  - Ollama Llama2 model
- Streamlit frontend to:
  - Generate essays on a given topic via Google GEMMA API
  - Generate poems on a given topic via Ollama Llama2
- Environment variables support using `.env` file
- Tracing enabled with Langchain (`LANGCHAIN_TRACING_V2`)

---

## Getting Started

### Prerequisites

- Python 3.8+
- `pip` package manager

### Installation

1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/langchain-demo.git
   cd langchain-demo
   ```

2. Create and activate a virtual environment (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate     # Windows
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Create a `.env` file in the root folder with your API keys:
   ```
   LANGCHAIN_API_KEY=your_langchain_api_key_here
   GROQ_API_KEY=your_groq_api_key_here
   GOOGLE_API_KEY=your_google_api_key_here
   PORT=8000
   ```

---

## Running the Backend (FastAPI)

Run the FastAPI server with Uvicorn:

```bash
uvicorn backend:app --host 0.0.0.0 --port 8000 --reload
```

This will start the server at `http://localhost:8000`

---

## Running the Frontend (Streamlit)

In a separate terminal, run the Streamlit app:

```bash
streamlit run frontend.py
```

This will open a web interface in your browser where you can:

- Write a topic to generate an essay via `/essay` endpoint using Google GEMMA
- Write a topic to generate a poem via `/poem` endpoint using Ollama Llama2

---

## API Endpoints

| Path       | Method | Description                     |
|------------|--------|---------------------------------|
| `/genai`   | POST   | GoogleGenerativeAI model endpoint |
| `/essay`   | POST   | Generate essay using ChatGroq    |
| `/poem`    | POST   | Generate poem using Ollama Llama2|

---

## Project Structure

```
├── backend.py          # FastAPI backend server
├── frontend.py         # Streamlit frontend app
├── .env                # Environment variables for API keys
├── requirements.txt    # Python dependencies
├── README.md           # This documentation
```

---

## Dependencies

- fastapi
- uvicorn
- langchain
- langchain_groq
- langchain_google_genai
- langchain_community (for Ollama)
- langserve
- python-dotenv
- requests
- streamlit

---

## Notes

- Make sure your API keys are valid and have the necessary permissions.
- The backend and frontend are designed to run locally; adjust URLs if deploying remotely.
- The Langchain tracing environment variable `LANGCHAIN_TRACING_V2` is enabled for debugging purposes.

---

## License

MIT License

---

## Contact

For questions or suggestions, please open an issue or contact [garvsharma835@gmail.com].

---



---
