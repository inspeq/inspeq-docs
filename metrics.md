# Metrics

### Metric

A metric is a quantifiable measure used to evaluate the performance of a model or algorithm. Metrics help assess how well a model is performing in terms of various aspects such as accuracy, precision, recall, F1-score, and more depending on the specific task at hand (classification, regression, clustering, etc.). 

#### Factual Consistency:

Factual consistency evaluation in LLM applications compares the factuality of the generated actual_output with the provided context, utilizing a pre-trained hallucination detection model to generate scores ranging from 0 to 1.

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

Grammar of the response including punctuation, tenses, spellings, etc. We ask gpt-4 to act as a grammatical evaluator and generate scores for responses. The scores generated are between 0 to 1. 

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

Fluency measures how well the responses are structured, grammatically correct, and linguistically coherent. We ask gpt-4 to generate a score from 1 to 3 (both inclusive) which evaluates the fluency of the generated response.

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

This measures how relevant the `actual_output` of your LLM application is compared to the provided `input`. You don't have to supply `context` or `expected_output` to evaluate answer relevancy. We use a nli based pretrained model for calculating scores.

The scores are in the range of 0 - 1.

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

The word limit test evaluates the ability to handle and process limited text inputs, ensuring efficient performance within defined constraints during tasks such as text generation or classification.

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

Response tone refers to the sentiment or emotional expression conveyed by generated text, which can be categorized into positive, negative, or neutral tones through sentiment analysis techniques.

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

Conceptual Similarity measures how conceptually similar the `actual_output` of your LLM application is compared to the provided `context`. You'll have to supply `context` to evaluate conceptual similarity. We calculate a score for this using cosine similarity applied on embeddings generated for the generated reponse and input using a pretrained model.

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

Readability refers to the ease with which text generated by models can be understood by humans, often assessed based on factors such as sentence structure, vocabulary complexity, and overall coherence.

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

Coherence evaluates how well the model generates coherent and logical responses that align with the context of the question. We take 3 metrics into account for calculating the score for coherence i.e. factual consistency, grammatical correctness and logical consistency.

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
