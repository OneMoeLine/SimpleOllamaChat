# Ollama Chatbot

This is a simple chatbot built using [LangChain](https://github.com/langchain-ai/langchain) and [Streamlit](https://streamlit.io/). The chatbot leverages Microsoft's [phi-3-mini-4k-instruct](https://huggingface.co/microsoft/Phi-3-mini-4k-instruct) model running on [Ollama](https://ollama.com/) for AI responses.

## Features

- **Simple User-friendly Interface**: Powered by Streamlit for a simple and interactive UI with streaming responses.
- **Self-hosted LLM**: Utilizes a locally hosted LLM via Ollama without the need for a live internet connection.
- **Chat History Context**: Leverages LangChain and Streamlit session storage for conversation management to ensure the AI has access to the chat history.

## Technologies Used

- [LangChain](https://github.com/langchain-ai/langchain)
- [Streamlit](https://streamlit.io/)
- [Ollama](https://ollama.com/)
- [Microsoft's Phi-3-mini-4k-instruct](https://huggingface.co/microsoft/Phi-3-mini-4k-instruct)

## Project Setup

### 1. Install Ollama

Download Ollama from [Ollama](https://ollama.com/). For Linux and WSL users, refer to the [manual install guide](https://github.com/ollama/ollama/blob/main/docs/linux.md).

### 2. Download Phi-3-mini Model

1. Download the [phi-3-mini-4k-instruct-q4.gguf](https://huggingface.co/microsoft/Phi-3-mini-4k-instruct-gguf/blob/main/Phi-3-mini-4k-instruct-q4.gguf) file.
2. Create a Phi-3-Modelfile:

    ```bash
    vi Phi-3-Modelfile
    ```

    Add the following content to the file:

    ```plaintext
    FROM /path/to/model/Phi-3-mini-4k-instruct-q4.gguf
    TEMPLATE """
    {{.Prompt}}
    """
    PARAMETER stop 
    PARAMETER num_ctx 4096
    ```

3. Setup the model:

    ```bash
    ollama create phi3mini -f <location of the file e.g., ./Phi-3-Modelfile>
    ```

    You can interact with the model directly via the terminal with:

    ```bash
    ollama run phi3mini
    ```

### 3. Setup Environment

1. Create a virtual environment:

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

2. Install prerequisites:

    ```bash
    pip install -r requirements.txt
    ```

## Usage

### 1. Run the Application

  ```bash
  streamlit run app.py
  ```

### 2. Access the Application

   Open your web browser and navigate to [http://localhost:8501](http://localhost:8501)
   
## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
