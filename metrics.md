# Metrics

This document provides an overview of the metrics available in the Inspeq AI SDK, along with their definitions and usage examples.

#### Available Metrics

* RESPONSE_TONE
* ANSWER_RELEVANCE
* FACTUAL_CONSISTENCY
* CONCEPTUAL_SIMILARITY
* READABILITY
* COHERENCE
* CLARITY
* DIVERSITY
* CREATIVITY
* DATA_LEAKAGE
* DO_NOT_USE_KEYWORDS
* MODEL_REFUSAL
* NARRATIVE_CONTINUITY
* WORD_COUNT_LIMIT
* INSECURE_OUTPUT
* ANSWER_FLUENCY
* GRAMMATICAL_CORRECTNESS

## Metric Definitions and Usage

### General Usage Pattern

For all metrics, use the following pattern:


```python
from inspeq.client import InspeqEval

# Initialize the client
INSPEQ_API_KEY = "your_inspeq_sdk_key"
INSPEQ_PROJECT_ID = "your_project_id"
INSPEQ_API_URL = "your_inspeq_backend_url"  # Required only for on-prem customers

inspeq_eval = InspeqEval(inspeq_api_key=INSPEQ_API_KEY, inspeq_project_id=INSPEQ_PROJECT_ID)

# Prepare input data
input_data = [{
    "prompt": "Your prompt here",
    "response": "Your response here",
    "context": "Your context here (if applicable)"
}]

# Define the metric to evaluate
metrics_list = ["METRIC_NAME"]

try:
    results = inspeq_eval.evaluate_llm_task(
        metrics_list=metrics_list,
        input_data=input_data,
        task_name="your_task_name"
    )
    print(results)
except Exception as e:
    print(f"An error occurred: {str(e)}")

```

Replace __METRIC_NAME__ with the specific metric you want to evaluate. 

### Below are examples for each metric:

* __RESPONSE_TONE__
Assess the tone and style of the generated response.
Usage

python

```python
metrics_list = ["RESPONSE_TONE"]

input_data = [{
    "response": "Paris is the capital of France."
}]

```

* __ANSWER_RELEVANCE__
Determine the relevance of the generated text in the context of a given query.
Usage
```python
metrics_list = ["ANSWER_RELEVANCE"]

input_data = [{
    "prompt": "What is the capital of France?",
    "response": "Paris is the capital of France."
}]
```

* __FACTUAL_CONSISTENCY__ 
Checks if the generated text is consistent with known facts.
Usage
```python
metrics_list = ["FACTUAL_CONSISTENCY"]

input_data = [{
    "context": "Paris is the capital of France and its largest city.",
    "response": "Paris is the capital of France."
}]
```

* __CONCEPTUAL_SIMILARITY__

Measure how closely the generated text aligns with the intended conceptual content.
Usage
```python
metrics_list = ["CONCEPTUAL_SIMILARITY"]

input_data = [{
    "context": "Paris is the capital of France and its largest city.",
    "response": "Paris is the capital of France."
}]
```

* __READABILITY__
Evaluates how easy it is to read and understand the LLM output.
Usage
```python
metrics_list = ["READABILITY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```

* __COHERENCE__
Evaluates how well the model generates coherent and logical responses that align with the context of the question.
Usage

```python
metrics_list = ["COHERENCE"]

input_data = [{
    "context": "Paris is the capital of France and its largest city.",
    "response": "Paris is the capital of France."
}]

```

* __CLARITY__

Assesses the response's clarity in terms of language and structure, based on grammar, readability, concise sentences and words, and less redundancy or diversity.
Usage

```python
metrics_list = ["CLARITY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```

* __DIVERSITY__
Assesses the diversity of vocabulary used in a piece of text.
Usage

```python
metrics_list = ["DIVERSITY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```

* __CREATIVITY__
Evaluates the creativity of AI-generated content using a combination of lexical diversity score, contextual similarity score, and hallucination score.
Usage

```python
metrics_list = ["CREATIVITY"]

input_data = [{
    "response": "Paris is the capital of France.",
    "context": "Paris is the capital of France and its largest city."
}]
```

* __DATA_LEAKAGE__
Detects whether the model response contains any personal information such as credit card numbers, phone numbers, emails, URLs, etc.
Usage
```python
metrics_list = ["DATA_LEAKAGE"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```

* __DO_NOT_USE_KEYWORDS__

Identify and evaluate the use of specific keywords or phrases.
Usage
```python
metrics_list = ["DO_NOT_USE_KEYWORDS"]

input_data = [{
    "response": "Paris is the capital of France."
}]

```

* __MODEL_REFUSAL__

Detecting whether the model responds with a refusal response or not.
Usage
```python
metrics_list = ["MODEL_REFUSAL"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```

* __NARRATIVE_CONTINUITY__

Evaluates whether a generated response maintains coherence and logical flow with the preceding narrative, without introducing abrupt or illogical shifts.
Usage
```python
metrics_list = ["NARRATIVE_CONTINUITY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```

* __WORD_COUNT_LIMIT__

Check if the generated text adheres to specified word limits.
Usage

```python
metrics_list = ["WORD_COUNT_LIMIT"]

input_data = [{
    "prompt": "What is the capital of France?",
    "response": "Paris is the capital of France."
}]
```

* __INSECURE_OUTPUT__

Detects whether the code provided by LLM in response is a malicious/insecure code which can give users unintended access or not.
Usage
```python
metrics_list = ["INSECURE_OUTPUT"]

input_data = [{
    "response": "import os\nprint(os.getcwd())"
}]
```


* __ANSWER_FLUENCY__

Evaluates the fluency and naturalness of the generated answer.
Usage

```python
metrics_list = ["ANSWER_FLUENCY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```

* __GRAMMATICAL_CORRECTNESS__

Assesses the grammatical correctness of the generated text.
Usage

```python
metrics_list = ["GRAMMATICAL_CORRECTNESS"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```

Note on Configuration

The SDK uses default configurations for each metric. You can override these defaults by providing your own config_input parameter when calling evaluate_llm_task.
