Local Setup Instructions (uv + Jupyter / VS Code)

Follow these setup instructions if you are running this notebook locally.
Running locally avoids notebook instability and allows proper inspection of agent behavior.

1. Prerequisites

Before starting, make sure you have:

Python 3.10+

uv
Install instructions: https://docs.astral.sh/uv/

If you are using VS Code :

* [Install the Python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

* [Install the Jupyter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)

2. Clone the Repository
git clone https://github.com/tligorio/multiagent_langgraph_tutorial.git
cd multiagent_langgraph_tutorial

3. Create the Virtual Environment

Create a project-local virtual environment using uv:

uv venv


Activate it:

source .venv/bin/activate


On Windows (PowerShell):

.venv\Scripts\activate


4. Install Project Dependencies

Install the project dependencies defined in pyproject.toml:

uv pip install -e .


Do not use pip install -U.
Version upgrades are managed by uv to keep the environment stable.

5. Install Jupyter Kernel Support

To run notebooks inside this environment, install Jupyter support:

uv pip install ipykernel jupyter


Then register the environment as a Jupyter kernel:

python -m ipykernel install \
  --user \
  --name multiagent-langgraph \
  --display-name "Python (multiagent-langgraph)"

6. Configure your API Key

Create a .env file (or edit the existing one) and add your OpenRouter API key:

OPENROUTER_API_KEY=your_actual_key_here


You can get an API key at https://openrouter.ai/settings/keys

7. If using VS Code, select the Kernel:

Open Multiagent_LangChain.ipynb

Click Select Kernel (top right)

Choose:

Python (multiagent-langgraph)


This ensures the notebook runs inside the correct environment.


8. Start the Notebook (Terminal Option)

If you are not using vscode, you may also start Jupyter from the terminal:

jupyter notebook Multiagent_LangChain.ipynb
