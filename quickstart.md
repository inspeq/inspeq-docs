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

from inspeq.client import InspeqEval


API_KEY = "your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data={
   "context": "Paris is the capital of France and its largest city.",
   "response":"Paris is the capital of France."
 }



results = inspeq_eval.factual_consistency(input_data= input_data, task_name="your_task_name")


print(results)


```

### Available Metrics 

You can use the following metrics evaluation functions provided by the Inspeq AI Python SDK:

- **Factual Consistency**: `factual_consistency(input_data)`
- **Answer Relevance**: `answer_relevance(input_data)`
- **Response Tone**: `response_tone(input_data)`
- **Do Not Use Keywords**: `do_not_use_keywords(input_data)`
- **Word Limit Test**: `word_limit_test(input_data)`
- **Conceptual Similarity**: `conceptual_similarity(input_data)`
- **Coherence**: `coherence(input_data)`
- **Readability**: `readability(input_data)`
- **Clarity**: `clarity(input_data)`
- **model_refusal**: `model_refusal(input_data)`
- **data_leakage**: `data_leakage(input_data)`
- **diversity**: `diversity(input_data)`
- **creativity**: `creativity(input_data)`
- **narrative_continuity**: `narrative_continuity(input_data)`


To use these functions, simply call the respective function with your input data.

