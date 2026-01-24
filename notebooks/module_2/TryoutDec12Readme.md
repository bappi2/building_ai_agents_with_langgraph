building_ai_agents_with_langgraph % ollama list
NAME             ID              SIZE      MODIFIED     
llama3:latest    365c0bd3c000    4.7 GB    26 hours ago    

If it doesn’t show llama3.1:70b, pull it:

ollama pull llama3.1:70b
# optional faster version:
# ollama pull llama3.1:8b

Because PyCharm uses its own virtual environment for the project.

So run these only inside PyCharm’s terminal:

python -m pip install --upgrade pip
python -m pip install jupyter jupyterlab
python -m pip install langgraph langchain langchain_openai
python -m pip install python-dotenv openai


Why?
Because PyCharm will install them into the interpreter for this project, 
and your notebook inside PyCharm will automatically use those packages.

Run Ollama commands ALWAYS in the macOS Terminal, not in PyCharm.

✅ Correct answer:
👉 Run ollama run llama3.1:8b in the macOS Terminal

NOT in the PyCharm terminal.

❓ Why?

Because:

Ollama is a system service, not a Python package.

PyCharm’s terminal runs inside your virtual environment, which is only for Python.

Ollama runs globally on your Mac and listens at http://localhost:11434.

So use macOS Terminal for:

ollama pull llama3.1:8b
ollama run llama3.1:8b
ollama list
ollama serve