# Metrics


### Metrics


#### Factual Consistency:


Factual Consistency checks if the generated text is consistent with known facts.


#### Usage


```python


from inspeq.client import InspeqEval


API_KEY = "your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data={
   "context": "Paris is the capital of France and its largest city.",
   "response":"Paris is the capital of France."
 }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,0.5, 1],
   }




results = inspeq_eval.factual_consistency(input_data= input_data ,config_input= config_input ,task_name="your_task_name")


print(results)




```


#### Do Not Use Keywords:


Identify and evaluate the use of specific keywords or phrases.
#### Usage


```python
from inspeq.client import InspeqEval


API_KEY="your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data = {
           "response": "Paris is the capital of France."
       }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,1],
   }




results = inspeq_eval.do_not_use_keywords(input_data= input_data ,config_input= config_input ,task_name="your_task_name")


print(results)


```


#### Answer Relevance:


Determine the relevance of the generated text in the context of a given query or


#### Usage


```python
from inspeq.client import InspeqEval


API_KEY="your_api_key"




inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data = {
   "prompt": "What is the capital of France?",
   "response": "Paris is the capital of France."
   }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,0.5,1],
   }




results = inspeq_eval.answer_relevance(input_data= input_data ,config_input= config_input ,task_name="your_task_name")


print(results)


```


#### Word Limit Test:


Check if the generated text adheres to specified word limits.


#### Usage


```python
from inspeq.client import InspeqEval


API_KEY="your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data = {
   "prompt": "What is the capital of France?",
   "response": "Paris is the capital of France."
   }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,1],
   }




results = inspeq_eval.word_limit_test(input_data= input_data ,config_input= config_input ,task_name="your_task_name")


print(results)


```


#### Response Tone:


Assess the tone and style of the generated response.


#### Usage


```python


from inspeq.client import InspeqEval


API_KEY="your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data = {
   "response": "Paris is the capital of France."
   }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,0.5, 1],
   }


results = inspeq_eval.response_tone(input_data= input_data ,config_input= config_input ,task_name="your_task_name")
print(results)


```


#### Conceptual Similarity:


Measure how closely the generated text aligns with the intended conceptual content.


#### Usage


```python
from inspeq.client import InspeqEval


API_KEY="your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data = {
           "context": "Paris is the capital of France and its largest city.",
           "response": "Paris is the capital of France."
       }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,0.5, 1],
   }




results = inspeq_eval.conceptual_similarity(input_data= input_data ,config_input= config_input ,task_name="your_task_name")


print(results)
```
#### Readability:


It tells how easy is to read and understand the llm output


#### Usage


```python
from inspeq.client import InspeqEval


API_KEY="your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data = {
           "response": "Paris is the capital of France."
       }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,0.5, 1],
   }


results = inspeq_eval.readability(input_data= input_data ,config_input= config_input ,task_name="your_task_name")


print(results)
```


#### Coherence :


Coherence metric evaluates how well the model generates coherent and logical responses that align with the context of the question.


#### Usage


```python
from inspeq.client import InspeqEval


API_KEY="your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data = {
           "context": "Paris is the capital of France and its largest city.",
           "response": "Paris is the capital of France."
       }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,0.5, 1],
   }




results = inspeq_eval.coherence(input_data= input_data ,config_input= config_input ,task_name="your_task_name")


print(results)
```
#### Clarity :


Clarity here refers to the response’s clarity in terms of language and structure. It's a subjective metric and is based on grammar, readability, concise sentences and words, and less redundancy or diversity at the moment. To add contextual clarity, we need to add topic coherence, response relevance, and word ambiguity.






#### Usage


```python
from inspeq.client import InspeqEval


API_KEY="your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data = {
           "response": "Paris is the capital of France."
       }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,0.5, 1],
   }




results = inspeq_eval.clarity(input_data= input_data ,config_input= config_input ,task_name="your_task_name")


print(results)
```


#### Data Leakage :


Detecting whether the model response contains any personal information such as credit card numbers, phone numbers, emails, urls etc.






#### Usage


```python
from inspeq.client import InspeqEval


API_KEY="your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data = {
           "response": "Paris is the capital of France."
       }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,1],
   }




results = inspeq_eval.data_leakage(input_data= input_data ,config_input= config_input ,task_name="your_task_name")


print(results)


```


#### Model Refusal :


Detecting whether the model responds with a refusal response or not






#### Usage


```python
from inspeq.client import InspeqEval




API_KEY="your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)




input_data = {
           "response": "Paris is the capital of France."
       }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,1],
   }




results = inspeq_eval.model_refusal(input_data= input_data ,config_input= config_input ,task_name="your_task_name")


print(results)
```




#### Creativity :


Creativity is also a subjective concept, especially in AI-generated content. LLMs can be very creative but the results are mostly evaluated by humans. For our story generation and document summarization use cases, we define this metric as a combination of different metrics that could provide a more comprehensive evaluation. We use lexical diversity score, contextual similarity score and hallucination score to evaluate creativity.






#### Usage


```python
from inspeq.client import InspeqEval


API_KEY="your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data = {
           "response": "Paris is the capital of France.",
           "context": "Paris is the capital of France and its largest city.",
       }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,0.5, 1],
   }




results = inspeq_eval.creativity(input_data= input_data ,config_input= config_input ,task_name="your_task_name")


print(results)
```




#### Diversity :


Diversity metric assess the diversity of vocabulary used in a piece of text. Higher lexical diversity generally indicates a broader range of words and can contribute to more natural-sounding language.






#### Usage


```python
from inspeq.client import InspeqEval


API_KEY="your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data = {
           "response": "Paris is the capital of France."
       }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,0.5, 1],
   }


results = inspeq_eval.diversity(input_data= input_data ,config_input= config_input ,task_name="your_task_name")
print(results)


```


#### Narrative Continuity :


Narrative continuity metric is a measure that evaluates whether a generated response maintains coherence and logical flow with the preceding narrative, without introducing abrupt or illogical shifts (ex.- story jumps). It analyzes factors like topic consistency, event/character continuity, and overall coherence to detect discontinuities in the narrative.


Narrative Continuity exclusively employs binary custom labels, such as "Not Continuous" and "Continuous".






#### Usage


```python
from inspeq.client import InspeqEval


API_KEY="your_api_key"


inspeq_eval = InspeqEval(inspeq_api_key= API_KEY)


input_data = {
           "response": "Paris is the capital of France."
       }


config_input= {
       "threshold": 0.5,
       "custom_labels": ["custom_label_1","custom_label_2"],
       "label_thresholds": [0,1],
   }




results = inspeq_eval.narrative_continuity(input_data= input_data ,config_input= config_input ,task_name="your_task_name")


print(results)
```



