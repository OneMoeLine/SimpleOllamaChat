# Ollama Chatbot

This is a simple chatbot build using using [LangChain](https://github.com/langchain-ai/langchain) and [Streamlit](https://streamlit.io/). The chatbot leverages Microsoft's [phi-3-mini-4k-instruct](https://huggingface.co/microsoft/Phi-3-mini-4k-instruct) model running on [Ollama](https://ollama.com/) for the AI responses.

## Features
- **Simple user-friendly interface**: Powered by Streamlit for a simple and interactive UI with streaming responses
- **Self-hosted LLM**: Utilizes a locally hosted LLM via Ollama without need for a live internet connection
- **Chat history context**: Leverages LangChain and Streamlit session storage for conversation management to ensure the AI has access to the chat history.

## Project Setup
1. **Install Ollama**
  The download link is accessible at [Ollama](https://ollama.com/). For Linux and WSL users, the [manual install](https://github.com/ollama/ollama/blob/main/docs/linux.md) is recommended
2. **Download the Phi-3-mini**
   1. Download the phi-3-mini-4k-instruct-q4.gguf file(https://huggingface.co/microsoft/Phi-3-mini-4k-instruct-gguf/blob/main/Phi-3-mini-4k-instruct-q4.gguf).
   2. Create a Phi-3-Modelfile
      ```
      vi Phi-3-Modelfile
      ```
      ```
      FROM /path/to/model/Phi-3-mini-4k-instruct-q4.gguf
      TEMPLATE """<|user|>
      {{.Prompt}}<|end|>
      <|assistant|>"""
      PARAMETER stop <|end|>
      PARAMETER num_ctx 4096
      ```
  3. Setup the model
     ```
     ollama create phi3mini -f <location of the file>
     ```
     You can interact with the model directly via the terminal through:
     ```
     ollama run phi3mini
     ```


