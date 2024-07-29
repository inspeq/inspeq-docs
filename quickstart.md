# QuickstartQuickstart Guide for Inspeq AI SDK

### Installation

#### Activate the python environment
```bash
  source venv/bin/activate
```

### Inspeq Python package installation

To install inspeqai python sdk, you can follow these steps:

Get latest version from [Here](https://pypi.org/project/inspeqai/)

```bash
pip install inspeqai
```
Install dotenv package if not installed already

Get latest version from [Here](https://pypi.org/project/python-dotenv/)
```bash
pip install python-dotenv
```

#### Get API keys

Get your API keys from [Here](https://platform.inspeq.ai/)

#### Usage

Create a python file like main.py where you could use the functions provided by inspeq python sdk.

```python

from inspeq.client import InspeqEval

# Initialize the client
INSPEQ_API_KEY = "your_inspeq_sdk_key"
INSPEQ_PROJECT_ID = "your_project_id"
INSPEQ_API_URL = "your_inspeq_backend_url" #  NOTE : Required only for our on-prem customers


inspeq_eval = InspeqEval(inspeq_api_key=INSPEQ_API_KEY, inspeq_project_id=INSPEQ_PROJECT_ID)


# Prepare input data
input_data = [{
    "prompt": "What is the capital of France?",
    "response": "Paris is the capital of France.",
    "context": "The user is asking about European capitals."
}]
# You can pass multiple set of input data object

# Define metrics to evaluate
metrics_list = ["RESPONSE_TONE", "FACTUAL_CONSISTENCY", "ANSWER_RELEVANCE"]

try:
    results = inspeq_eval.evaluate_llm_task(
        metrics_list=metrics_list,
        input_data=input_data,
        task_name="capital_question"
    )
    print(results)
except Exception as e:
    print(f"An error occurred: {str(e)}")
    
```

### Available Metrics 
```
metrics_list = [
    "RESPONSE_TONE",
    "ANSWER_RELEVANCE",
    "FACTUAL_CONSISTENCY",
    "CONCEPTUAL_SIMILARITY",
    "READABILITY",
    "COHERENCE",
    "CLARITY",
    "DIVERSITY",
    "CREATIVITY",
    <!-- "DATA_LEAKAGE", -->
    <!-- "DO_NOT_USE_KEYWORDS", -->
    <!-- "MODEL_REFUSAL", -->
    "NARRATIVE_CONTINUITY",
    <!-- "WORD_COUNT_LIMIT", -->
    <!-- "INSECURE_OUTPUT", -->
    <!-- "ANSWER_FLUENCY", -->
    "GRAMMATICAL_CORRECTNESS"
]

```
To use these metrics, simply pass the respective metrics name with your metrics_list.

