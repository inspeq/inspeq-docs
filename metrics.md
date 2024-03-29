# Metrics

### Metrics

#### Factual Consistency:

Factual Consistency checks if the generated text is consistent with known facts.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY = "your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)

input_data={
    "context": "Paris is the capital of France and its largest city.",
    "response":"Paris is the capital of France."
  }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2", "custom_label_3"],
        "label_thresholds": [0,0.5, 0.8],
    }


print("Factual Consistency:", inspeq_instance.factual_consistency(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```

#### Do Not Use Keywords:

Identify and evaluate the use of specific keywords or phrases.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "response": "Paris is the capital of France."
        }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2"],
        "label_thresholds": [0,1],
    }

print("Do Not Use Keywords: ", inspeq_instance.do_not_use_keywords(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```

#### Answer Relevance:

Determine the relevance of the generated text in the context of a given query or

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
    "prompt": "What is the capital of France?",
    "response": "Paris is the capital of France."
    }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2", "custom_label_3"],
        "label_thresholds": [0,0.5,0.8],
    }


print("Answer Relevance:", inspeq_instance.answer_relevance(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```

#### Word Limit Test:

Check if the generated text adheres to specified word limits.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
    "prompt": "What is the capital of France?",
    "response": "Paris is the capital of France."
    }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2"],
        "label_thresholds": [0,1],
    }


print("Word Limit Test:", inspeq_instance.word_limit_test(input_data = input_data,config_input=config_input, task_name="your_task_name" ))

```

#### Response Tone:

Assess the tone and style of the generated response.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
    "response": "Paris is the capital of France."
    }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2", "custom_label_3"],
        "label_thresholds": [0,0.5,0.8],
    }


print("Response Tone:", inspeq_instance.response_tone(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```

#### Conceptual Similarity:

Measure how closely the generated text aligns with the intended conceptual content.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "context": "Paris is the capital of France and its largest city.",
            "response": "Paris is the capital of France."
        }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2", "custom_label_3"],
        "label_thresholds": [0,0.5,0.8],
    }


print("Conceptual Similarity:", inspeq_instance.conceptual_similarity(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```
#### Readability:

It tells how easy is to read and understand the llm output

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "response": "Paris is the capital of France."
        }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2", "custom_label_3"],
        "label_thresholds": [0,0.5,0.8],
    }


print("Readability:", inspeq_instance.readability(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```

#### Coherence :

Coherence metric evaluates how well the model generates coherent and logical responses that align with the context of the question.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "context": "Paris is the capital of France and its largest city.",
            "response": "Paris is the capital of France."
        }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2", "custom_label_3"],
        "label_thresholds": [0,0.5,0.8],
    }


print("Coherence:", inspeq_instance.coherence(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```
#### Clarity :

Clarity here refers to the response’s clarity in terms of language and structure. It's a subjective metric and is based on grammar, readability, concise sentences and words, and less redundancy or diversity at the moment. To add contextual clarity, we need to add topic coherence, response relevance, and word ambiguity.



#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "response": "Paris is the capital of France."
        }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2", "custom_label_3"],
        "label_thresholds": [0,0.5,0.8],
    }


print("Clarity:", inspeq_instance.clarity(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```

#### Data Leakage :

Detecting whether the model response contains any personal information such as credit card numbers, phone numbers, emails, urls etc.



#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "response": "Paris is the capital of France."
        }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2"],
        "label_thresholds": [0,1],
    }


print("Data Leakage:", inspeq_instance.data_leakage(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```

#### Model Refusal :

Detecting whether the model responds with a refusal response or not



#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "response": "Paris is the capital of France."
        }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2"],
        "label_thresholds": [0,1],
    }


print("Model Refusal:", inspeq_instance.model_refusal(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```


#### Creativity :

Creativity is also a subjective concept, especially in AI-generated content. LLMs can be very creative but the results are mostly evaluated by humans. For our story generation and document summarization use cases, we define this metric as a combination of different metrics that could provide a more comprehensive evaluation. We use lexical diversity score, contextual similarity score and hallucination score to evaluate creativity.



#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "response": "Paris is the capital of France.", 
            "context": "Paris is the capital of France and its largest city.",
        }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2", "custom_label_3"],
        "label_thresholds": [0,0.5,0.8],
    }


print("Creativity:", inspeq_instance.creativity(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```


#### Diversity :

Diversity metric assess the diversity of vocabulary used in a piece of text. Higher lexical diversity generally indicates a broader range of words and can contribute to more natural-sounding language.



#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "response": "Paris is the capital of France."
        }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2", "custom_label_3"],
        "label_thresholds": [0,0.5,0.8],
    }


print("Diversity:", inspeq_instance.diversity(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```

#### Narrative Continuity :

Narrative continuity metric is a measure that evaluates whether a generated response maintains coherence and logical flow with the preceding narrative, without introducing abrupt or illogical shifts (ex.- story jumps). It analyzes factors like topic consistency, event/character continuity, and overall coherence to detect discontinuities in the narrative.

Not Continuous and  Continuous 



#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "response": "Paris is the capital of France."
        }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2"],
        "label_thresholds": [0,1],
    }


print("Narrative Continuity:", inspeq_instance.narrative_continuity(input_data = input_data,config_input=config_input, task_name="your_task_name"))

```


#### Get All Metics :

Provide  result of all metrics.

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "prompt":"What is the capital of France?",
            "context": "Paris is the capital of France and its largest city.",
            "response": "Paris is the capital of France."
        }

config_input= {
        "threshold": 0.5,
        "custom_labels": ["custom_label_1","custom_label_2"],
        "label_thresholds": [0,0.5],
    }



print("Get all metrics:", inspeq_instance.get_all_metrics(input_data = input_data,config_input=config_input, task_name="your_task_name") )

```