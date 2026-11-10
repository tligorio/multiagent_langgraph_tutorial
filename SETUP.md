Local Setup Instructions (uv + Jupyter / VS Code)

Follow these setup instructions if you are running this notebook locally.
Running locally avoids notebook instability and allows proper inspection of agent behavior.

1. Prerequisites

Before starting, make sure you have:

Python 3.12+

uv
Install instructions: https://docs.astral.sh/uv/

If you are using VS Code:

* [Install the Python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

* [Install the Jupyter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)

2. Clone the Repository

git clone https://github.com/tligorio/multiagent_langgraph_tutorial.git
cd multiagent_langgraph_tutorial

3. Create the Environment and Install Dependencies

uv sync

This creates a project-local virtual environment (.venv) and installs the dependencies listed in pyproject.toml, including Jupyter support.

Do not use pip install -U.
Version upgrades are managed by uv to keep the environment stable.

4. Add Your API Key

Create a .env file in the project folder containing:

OPENROUTER_API_KEY=your_openrouter_key_here

You can get an API key at https://openrouter.ai/settings/keys

.env is listed in .gitignore. Never paste keys into notebook cells or commit them.

5. Register the Environment as a Jupyter Kernel

uv run python -m ipykernel install \
  --user \
  --name multiagent-langgraph \
  --display-name "Python (multiagent-langgraph)"

6. If using VS Code, select the Kernel:

Open Multiagent_LangGraph.ipynb

Click Select Kernel (top right)

Choose:

Python (multiagent-langgraph)

This ensures the notebook runs inside the correct environment.

7. Start the Notebook (Terminal Option)

If you are not using VS Code, you may also start Jupyter from the terminal:

uv run jupyter notebook Multiagent_LangGraph.ipynb

When running locally, skip the first `!pip install` cell; `uv sync` already installed everything.
