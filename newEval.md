## Example using custom configs

```python 
from inspeq.client import InspeqEval

input_data = [
   {
       "prompt":"What is the capital of France?",
       "response": "Paris is the capital of France",
       "context" : "Paris is the capital of France and its largest city"
   },
   {
       "prompt":"What is the capital of France?",
       "response": "Paris is the capital of France",
       "context" : "Paris is the capital of France and its largest city"
   }
]

metrics_list = [ "RESPONSE_TONE"]

inspeq_api_key= "your_inspeq_api_key"

inspeq_eval = InspeqEval(inspeq_api_key= inspeq_api_key)

results = inspeq_eval.evaluate_llm_task(data= input_data , metrics_list= metrics_list, task_name = "your_task_name")


print(results)

```
## Example using custom config file


```python
from inspeq.client import InspeqEval

input_data = [
   {
       "prompt":"What is the capital of France?",
       "response": "Paris is the capital of France",
       "context" : "Paris is the capital of France and its largest city"
   },
   {
       "prompt":"What is the capital of France?",
       "response": "Paris is the capital of France",
       "context" : "Paris is the capital of France and its largest city"
   }
]

metrics_list = [ "RESPONSE_TONE", "CLARITY"]

inspeq_api_key= "your_inspeq_api_key"

inspeq_eval = InspeqEval(inspeq_api_key= inspeq_api_key, config_file= '/path/to/your/config')

metrics_config = {
   "response_tone_config": {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1", "custom_label_2"],
       "label_thresholds": [0,0.5,1]
   },
   "clarity_config": {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1", "custom_label_2"],
       "label_thresholds": [0,0.5,1]
   },

}

results = inspeq_eval.evaluate_llm_task(data= input_data , metrics_list= metrics_list, metrics_config = metrics_config, task_name = "your_task_name")

print(results)

```

When configuring metrics, it's important to note that each metric can be customized individually. If specific configurations are not provided, the system will default to predetermined values.

- "threshold"- float value should be not more than 1 in between 0 to 1 including 0 and 1
- "custom_labels"- custom string values to label threshold you will be defining. example: ["bad","average","good"]
- "label_thresholds"- custom values for custom labels should be in ascending order range example: [0,0.5,1]

#### Note : number of label_thresholds must be equal to number of custom_labels.

#### Values metrics_list can take as metric names
You can give number of metric names as provided below. metrics_list can take multiple values and values provided will be considered
as metric names which needs to be evaluate if you did not provide the custom configurations for the metrcs defined in the list than
we will evaluate them on our default cnofigurations.


For each metric, metric_config can be given as under:

- "RESPONSE_TONE"

```python
metrics_config = {
    "response_tone_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
    }}
```

- DO_NOT_USE_KEYWORDS: This metric that has binary output.

```python
metrics_config = {
    "do_not_use_keywords_config": {
        "threshold": 0.5,
        "custom_labels": ["bad", "good"],
        "label_thresholds": [0,1]
    }}
```

- "ANSWER_RELEVANCE"

```python
metrics_config = {
    "answer_relevance_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
    }}
```

- WORD_LIMIT_TEST: This metric that has binary output.

```python
metrics_config = {
    "word_limit_test_config": {
        "threshold": 0.5,
        "custom_labels": ["bad", "good"],
        "label_thresholds": [0,1]
    }}
```

- "FACTUAL_CONSISTENCY"

```python
metrics_config = {
    "factual_consistency_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
    }}
```

- "CONCEPTUAL_SIMILARITY"

```python
metrics_config = {
    "conceptual_similarity_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
    }}
```

- "READABILITY"

```python
metrics_config = {
    "readability_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
    }}
```

- "COHERENCE"

```python
metrics_config = {
    "coherence_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
    }}
```

- "CLARITY"

```python
metrics_config = {
    "clarity_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
    }}
```

- MODEL_REFUSAL: This metric that has binary output.

```python
metrics_config = {
    "model_refusal_config": {
        "threshold": 0.5,
        "custom_labels": ["bad", "good"],
        "label_thresholds": [0,1]
    }}
```

- DATA_LEAKAGE: This metric that has binary output.

```python
metrics_config = {
    "leakage_config": {
        "threshold": 0.5,
        "custom_labels": ["bad", "good"],
        "label_thresholds": [0,1]
    }}
```

- "DIVERSITY"

```python
metrics_config = {
    "diversity_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
    }}
```

- "CREATIVITY"

```python
metrics_config = {
    "creativity_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
    }}
```

- NARRATIVE_CONTINUITY: This metric that has binary output.

```python
metrics_config = {
    "narrative_continuity_config": {
        "threshold": 0.5,
        "custom_labels": ["bad", "good"],
        "label_thresholds": [0,1]
    }}
```
