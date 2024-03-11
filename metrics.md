# Metrics

### Metrics

#### Factual Consistency:

Factual Consistency checks if the generated text is consistent with known facts.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY = "sdk_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)

input_data={
    "context": "your_llm_context",
    "response":"your_llm_response"
  }

'''Note : Do not change the structure of input data keep the structure as it
is. Put your data at places of Your_llm_response'''


print("Factual Consistency:", inspeq_instance.factual_consistency(input_data))

```

#### Grammatical Correctness:

Assess the grammatical accuracy of the generated text.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "response": "your_llm_response"
        }


print("Grammatical Correctness: ", inspeq_instance.grammatical_correctness(input_data))

```

#### Do Not Use Keywords:

Identify and evaluate the use of specific keywords or phrases.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "response": "your_llm_response"
        }


print("Do Not Use Keywords: ", inspeq_instance.do_not_use_keywords(input_data))

```

#### Fluency:

Assess the overall smoothness and fluency of the generated text

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "response": "your_llm_response"
        }

print("Fluency:", inspeq_instance.fluency(input_data))

```

#### Answer Relevance:

Determine the relevance of the generated text in the context of a given query or

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
    "prompt": "your_llm_prompt",
    "response": "your_llm_response"
    }


print("Answer Relevance:", inspeq_instance.answer_relevance(input_data))

```

#### Word Limit Test:

Check if the generated text adheres to specified word limits.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
    "prompt": "your_llm_prompt",
    "response": "your_llm_response"
    }



print("Word Limit Test:", inspeq_instance.word_limit_test(input_data))

```

#### Response Tone:

Assess the tone and style of the generated response.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
    "response": "your_llm_response"
    }


print("Response Tone:", inspeq_instance.response_tone(input_data))

```

#### Conceptual Similarity:

Measure how closely the generated text aligns with the intended conceptual content.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "context": "your_llm_context",
            "response": "your_llm_response",
        }

print("Conceptual Similarity:", inspeq_instance.conceptual_similarity(input_data))

```
#### Readability:


#### Usage

```python
from inspeq.client import Evaluator


API_KEY="your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "response": "your_llm_response"
        }


print("Readability:", inspeq_instance.readability(input_data))

```

#### Coherence :
Coherence metric evaluates how well the model generates coherent and logical responses that align with the context of the question.

#### Usage

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