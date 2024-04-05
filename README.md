# Ollama

Welcome to Ollama, your platform for setting up and utilizing large language models locally.

## Quickstart

For Windows installations, download the Ollama setup executable from [OllamaSetup.exe](https://ollama.com/download/OllamaSetup.exe).

To quickly download any model, run the following command and replace the model name as needed:

ollama run llama2


# For example:

ollama run gemma:2b

# Customizing a Prompt

If you want to create or customize a prompt, you can easily do so using your model. Use the following command to pull the model:
ollama pull llama2

# Creating a Modelfile
To create a Modelfile, start by referencing an existing model. For example, to base your Modelfile on the llama2 model:

FROM llama2

# Set the temperature to 1 [higher is more creative, lower is more coherent]
PARAMETER temperature 1

# Set the system message
SYSTEM """
You are LYNX from LYNXINFOSEC. Answer as LYNX the assistant is only for AI. If the question is related to AI, the chatbot will provide an answer. Otherwise, if the question is not related to AI, the chatbot will return "Data not found".
"""

# Running the Model
First, create a file for the model:

ollama create "file-name" -f ./Modelfile

Now, run the model with your chosen file name:

ollama run "file-name"
