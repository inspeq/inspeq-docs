## Example

```python


from inspeq.client import Eval


prompt = "query_text" # these are required fields depending on metrics
context = "context_text"  # these are required fields depending on metrics
response = "output_text"  # these are required fields depending on metrics
secret_key = "sdk_api_key" # it is required field
task_name = "abc" #it is compulsory to provide whatever you want to give the task name.

metrics_list = [
    "DIVERSITY"
]
metrics_config = {
    "diversity_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0],
    }
}
inspeq_instance = Eval("secret_key")
result = inspeq_instance.evaluate_task(prompt, context, response, task_name, metrics_list, metrics_config)
print(result)
```

Ouptut:

```json
[
  {
    "metric_name": "DIVERSITY_EVALUATION",
    "actual_value": 1.0,
    "actual_value_type": "FLOAT",
    "metric_labels": ["string"],
    "others": {},
    "threshold": ["Pass"]
  }
]
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

"RESPONSE_TONE",
"DO_NOT_USE_KEYWORDS",
"ANSWER_FLUENCY",
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

- "DO_NOT_USE_KEYWORDS"

```python
metrics_config = {
    "do_not_use_keywords_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
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

- "WORD_LIMIT_TEST"

```python
metrics_config = {
    "word_limit_test_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
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

- "MODEL_REFUSAL"

```python
metrics_config = {
    "model_refusal_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
    }}
```

- "DATA_LEAKAGE"

```python
metrics_config = {
    "leakage_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
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

- "NARRATIVE_CONTINUITY"

```python
metrics_config = {
    "narrative_continuity_config": {
        "threshold": 0.5,
        "custom_labels": ["string"],
        "label_thresholds": [0]
    }}
```
