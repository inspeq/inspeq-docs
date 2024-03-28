# Quickstart

## Inspeq Sdk

### Installation

### Create a virtual environment in Linux/Mac/Windows

### Linux OS / MAC OS
### Using venv (Python 3)

1. Open a terminal.
2. Navigate to the directory where you want to create the virtual environment.
3. Run the following command:

```bash
   python3 -m venv venv
```

#### Activate it

```bash
  source venv/bin/activate
```

### Windows

1. Open a terminal.
2. Navigate to the directory where you want to create the virtual environment.
3. Run the following command:

```bash
   python -m venv venv
```

#### Activate the virtual environment

```bash
venv\Scripts\activate
```

#### Make sure your environment is activated everytime you use package

### Python package installation

To install inspeqai python sdk, you can follow these steps:

```bash
pip install inspeqai
```

Get latest version from [Here](https://pypi.org/project/inspeqai/)

#### Get API keys

Get your API keys from [Here](https://app.inspeq.ai/)

#### Usage

Create a python file like main.py where you could use the functions provided by inspeq python sdk.

```python

from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "context": "Paris is the capital of France and its largest city.",
            "response": "Paris is the capital of France."
        }


print("Coherence:", inspeq_instance.coherence(input_data))


```

### Available Metrics 

You can use the following metrics evaluation functions provided by the Inspeq AI Python SDK:
"RESPONSE_TONE",
"DO_NOT_USE_KEYWORDS",
"ANSWER_RELEVANCE",
"WORD_LIMIT_TEST",
"FACTUAL_CONSISTENCY",
"CONCEPTUAL_SIMILARITY",
"READABILITY",
"COHERENCE",
"CLARITY",
"MODEL_REFUSAL",
"DATA_LEAKAGE",
"DIVERSITY",
"CREATIVITY",
"NARRATIVE_CONTINUITY"

To use these functions, simply call the respective function with your input data.

