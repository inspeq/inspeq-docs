# Inspeq Metrics

This document provides an overview of the metrics available in the Inspeq AI SDK, along with their definitions and usage examples.

#### Available Metrics
<details> <summary>RESPONSE_TONE</summary>

Assess the tone and style of the generated response.

Usage

```python
metrics_list = ["RESPONSE_TONE"]

input_data = [{
    "response": "Paris is the capital of France."
}]

```
</details>

<details>
<summary>ANSWER_RELEVANCE</summary>

Measures the degree to which the generated content directly addresses and pertains to the specific question or prompt provided by the user.


Usage
```python
metrics_list = ["ANSWER_RELEVANCE"]

input_data = [{
    "prompt": "What is the capital of France?",
    "response": "Paris is the capital of France."
}]
```
</details>
 <details>
<summary>FACTUAL_CONSISTENCY</summary>

Measures the extent of the model hallucinating i.e. model is making up a response based on its imagination or response is grounded in the context supplied


Usage
```python
metrics_list = ["FACTUAL_CONSISTENCY"]

input_data = [{
    "context": "Paris is the capital of France and its largest city.",
    "response": "Paris is the capital of France."
}]
```
</details>
<details>
<summary>CONCEPTUAL_SIMILARITY</summary>

</details> 
<details>
<summary>READABILITY</summary>
</details> <details>
<summary>COHERENCE</summary>
</details> <details>
<summary>CLARITY</summary>
</details> <details>
<summary>DIVERSITY</summary>
</details> <details>
<summary>CREATIVITY</summary>
</details>
<!-- * DATA_LEAKAGE -->
<!-- * DO_NOT_USE_KEYWORDS -->
<!-- * MODEL_REFUSAL -->
<details>
<summary>NARRATIVE_CONTINUITY</summary>
</details>
<!-- * WORD_COUNT_LIMIT -->
<!-- * INSECURE_OUTPUT -->
<!-- * ANSWER_FLUENCY -->
<details>
<summary>GRAMMATICAL_CORRECTNESS</summary>
</details>

# Metric Definitions and Usage

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

## Below are examples for each metric:

__CONCEPTUAL_SIMILARITY__

Measures the extent to which the model response aligns with and reflects the underlying ideas or concepts present in the provided context or prompt.

Usage
```python
metrics_list = ["CONCEPTUAL_SIMILARITY"]

input_data = [{
    "context": "Paris is the capital of France and its largest city.",
    "response": "Paris is the capital of France."
}]
```

 __READABILITY__

Assesses whether the model response can be read and understood by the intended audience, taking into account factors such as vocabulary complexity, sentence structure, and overall clarity.

Usage
```python
metrics_list = ["READABILITY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```

__COHERENCE__

Evaluates how well the model generates coherent and logical responses that align with the context of the question.

Usage

```python
metrics_list = ["COHERENCE"]

input_data = [{
    "context": "Paris is the capital of France and its largest city.",
    "response": "Paris is the capital of France."
}]

```

__CLARITY__

Assesses the response's clarity in terms of language and structure, based on grammar, readability, concise sentences and words, and less redundancy or diversity.

Usage

```python
metrics_list = ["CLARITY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```
__DIVERSITY__

Assesses the diversity of vocabulary used in a piece of text.

Usage

```python
metrics_list = ["DIVERSITY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```

__CREATIVITY__

Assesses the ability of the model to generate imaginative, and novel responses that extend beyond standard or expected answers.

Usage

```python
metrics_list = ["CREATIVITY"]

input_data = [{
    "response": "Paris is the capital of France.",
    "context": "Paris is the capital of France and its largest city."
}]
```
<!-- 
__DATA_LEAKAGE__

Detects whether the model response contains any personal information such as credit card numbers, phone numbers, emails, URLs, etc.

Usage

```python
metrics_list = ["DATA_LEAKAGE"]

input_data = [{
    "response": "Paris is the capital of France."
}]
``` -->

<!-- __DO_NOT_USE_KEYWORDS__

Identifies and evaluate the use of specific keywords or phrases.

Usage

```python
metrics_list = ["DO_NOT_USE_KEYWORDS"]

input_data = [{
    "response": "Paris is the capital of France."
}]

``` -->

<!-- __MODEL_REFUSAL__

Identifies rejections in the model responses.

Usage

```python
metrics_list = ["MODEL_REFUSAL"]

input_data = [{
    "response": "Paris is the capital of France."
}] -->
<!-- ``` -->

__NARRATIVE_CONTINUITY__

Measures the consistency and logical flow of the response throughout the generated text, ensuring that the progression of events remains coherent and connected. 

Usage
```python
metrics_list = ["NARRATIVE_CONTINUITY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```


<!-- __WORD_COUNT_LIMIT__

Checks if the generated text adheres to specified word limits.

Usage

```python
metrics_list = ["WORD_COUNT_LIMIT"]

input_data = [{
    "prompt": "What is the capital of France?",
    "response": "Paris is the capital of France."
}]
``` -->

<!-- __INSECURE_OUTPUT__

 Detects any potentially harmful responses that could lead to system vulnerabilities. Eg. detects any  mallicious code, Javascript or Markdown generated by the model that could result in XSS.

Usage
```python
metrics_list = ["INSECURE_OUTPUT"]

input_data = [{
    "response": "import os\nprint(os.getcwd())"
}]
```  -->


<!-- __ANSWER_FLUENCY__

Assesses the smoothness and coherence with which the model generates language that is easily understandable and grammatically correct.

Usage

```python
metrics_list = ["ANSWER_FLUENCY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
``` -->


__GRAMMATICAL_CORRECTNESS__

Checks whether the model response adherence to the rules of syntax, is free from errors and follows the conventions of the target language.

Usage

```python
metrics_list = ["GRAMMATICAL_CORRECTNESS"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```

__Note on Configuration__

The SDK uses default configurations for each metric. You can override these defaults by providing your own config_input parameter when calling evaluate_llm_task.
