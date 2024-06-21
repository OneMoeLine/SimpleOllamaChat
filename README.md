# Ollama Chatbot

This is a simple chatbot build using using [LangChain](https://github.com/langchain-ai/langchain) and [Streamlit](https://streamlit.io/). The chatbot leverages Microsoft's [phi-3-mini-4k-instruct](https://huggingface.co/microsoft/Phi-3-mini-4k-instruct) model running on [Ollama](https://ollama.com/) for the AI responses.

## Features
- **Simple user-friendly interface**: Powered by Streamlit for a simple and interactive UI
- **Self-hosted LLM**: Utilizes a locally hosted LLM via Ollama without need for a live internet connection
- **Chat history context**: Leverages LangChain and Streamlit session storage for conversation management to ensure the AI has access to the chat history.
