# Metrics

### Metrics

#### Factual Consistency:

Check if the generated text is consistent with known facts.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "your_llm_context",
            "llm_input_query": "your_llm_query",
            "llm_output": "your_llm_output",
        }


print("\n  Factual Consistency   is:")
print(inspeq_instance.factual_consistency(input_data))
```

#### Grammatical Correctness:

Assess the grammatical accuracy of the generated text.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "your_llm_context",
            "llm_input_query": "your_llm_query",
            "llm_output": "your_llm_output",
        }


print("\n  Grammatical correctness response  is:")
print(inspeq_instance.grammatical_correctness(input_data))
```

#### Do Not Use Keywords:

Identify and evaluate the use of specific keywords or phrases.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "your_llm_context",
            "llm_input_query": "your_llm_query",
            "llm_output": "your_llm_output",
        }


print("\n  Do not use keywords response  is:")
print(inspeq_instance.do_not_use_keywords(input_data))
```

#### Fluency:

Assess the overall smoothness and fluency of the generated text

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "your_llm_context",
            "llm_input_query": "your_llm_query",
            "llm_output": "your_llm_output",
        }


print("\n  Fluency is:")
print(inspeq_instance.fluency(input_data))
```

#### Answer Relevance:

Determine the relevance of the generated text in the context of a given query or

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "your_llm_context",
            "llm_input_query": "your_llm_query",
            "llm_output": "your_llm_output",
        }

print("\n  Answer relevance is:")
print(inspeq_instance.answer_relevance(input_data))
```

#### Word Limit Test:

Check if the generated text adheres to specified word limits.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "your_llm_context",
            "llm_input_query": "your_llm_query",
            "llm_output": "your_llm_output",
        }



print("\n  word_limit_test is:")
print(inspeq_instance.word_limit_test(input_data))
```

#### Response Tone:

Assess the tone and style of the generated response.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "your_llm_context",
            "llm_input_query": "your_llm_query",
            "llm_output": "your_llm_output",
        }


print("\n  response_tone is:")
print(inspeq_instance.response_tone(input_data))
```

#### Conceptual Similarity:

Measure how closely the generated text aligns with the intended conceptual content.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "your_llm_context",
            "llm_input_query": "your_llm_query",
            "llm_output": "your_llm_output",
        }


print("\n  conceptual_similarity is:")
print(inspeq_instance.conceptual_similarity(input_data))
```
#### Readability:


#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "your_llm_context",
            "llm_input_query": "your_llm_query",
            "llm_output": "your_llm_output",
        }


print("\n  Readability is:")
print(inspeq_instance.readability(input_data))
```

#### Coherence :
Coherence metric evaluates how well the model generates coherent and logical responses that align with the context of the question.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "your_llm_context",
            "llm_input_query": "your_llm_query",
            "llm_output": "your_llm_output",
        }


print("\n  Coherence is:")
print(inspeq_instance.coherence(input_data))
```
