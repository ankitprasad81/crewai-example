# Steps to try the crewai-groq-example

1. Open the VS Code editor and clone the repository from Github <br>
    - `git clone https://github.com/ankitprasad81/crewai-example.git`
2. If you already don't have the <b> poetry </b> installed, follow the instructions to install it in your system <br>
    - For Windows: <code>pip install poetry</code>
    - For Mac: <code>brew install poetry</code><br>
3. Install all dependencies using Poetry by executing the following command<br>
   <code>poetry install --no-root</code> and then create the virtual environment by running <code>poetry shell</code>.
4. Navigate to `https://console.groq.com/keys` to grab the <b> GROQ API Key </b>
5. Rename the <b> .env.example </b> to <b>.env</b>
6. Update the <b>"GROQ_API_KEY"</b> with the one you created in Groq Cloud in <b> .env </b> file
7. Execute <code>python main.py</code> to start the crew.


# Steps to try the crewai-Ollama-mixtral-example

1. Open the VS Code editor and clone the repository from Github <br>
    - `git clone https://github.com/ankitprasad81/crewai-example.git`
2. If you already don't have the <b> poetry </b> installed, follow the instructions to install it in your system <br>
    - For Windows: <code>pip install poetry</code>
    - For Mac: <code>brew install poetry</code><br>
3. Install all dependencies using Poetry by executing the following command<br>
   <code>poetry install --no-root</code> and then create the virtual environment by running <code>poetry shell</code>.
4. Download `Ollama` and install `mixtral-8x7B` model
    - Link to download Ollama: <a href="https://ollama.com/download"> Click here </a>
    - Install the mixtral model, run `ollama run mixtral`
5. Edit <code>agents.py</code>, un-comment <i>line 19</i> and comment <i>lines 9 to 12</i> to disable Groq and run Ollama-Mixtral
6. Execute <code>python main.py</code> to start the crew.


# Contributions

Contributions are always welcome! <br>
Please reach out to us at <a href="mailto:trywithninja@gmail.com">email</a> to contribute. 🌟