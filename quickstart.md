# Quickstart

### Inspeqai Python SDK

Get started by simple example for evaluation of metrics.

### Create a Virtual Environment in Linux or Windows

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

### windows

1. Open a terminal.
2. Navigate to the directory where you want to create the virtual environment.
3. Run the following command:

```bash
   python -m venv venv
```

#### Activate it

```bash
venv\Scripts\activate
```

#### Make sure your environment is activated everytime you use package

### SDK Installation

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
            "context": "your_llm_context",
            "response": "your_llm_response"

        }


print("Coherence:", inspeq_instance.coherence(input_data))


```

### Available Metrics 

You can use the following metrics evaluation functions provided by the Inspeq AI Python SDK:

- **Factual Consistency**: `factual_consistency(input_data)`
- **Answer Relevance**: `answer_relevance(input_data)`
- **Response Tone**: `response_tone(input_data)`
- **Grammatical Correctness**: `grammatical_correctness(input_data)`
- **Fluency**: `fluency(input_data)`
- **Do Not Use Keywords**: `do_not_use_keywords(input_data)`
- **Word Limit Test**: `word_limit_test(input_data)`
- **Conceptual Similarity**: `conceptual_similarity(input_data)`
- **Coherence**: `coherence(input_data)`
- **Readability**: `readability(input_data)`
- **Clarity**: `clarity(input_data)`
- **Get all metrics**: `get_all_metrics(input_data)`

To use these functions, simply call the respective function with your input data.

