# Metrics

### Metrics

#### Factual Consistency:

Check if the generated text is consistent with known facts.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="Your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "Seattle is known for its wet climate due to its location in the Pacific Northwest region of the United States. From 1981 to 2010, the average annual precipitation measured at Seattle-Tacoma International Airport was 37.49 inches (952 mm). This significant amount of rainfall contributes to lush vegetation and a generally green landscape throughout the year. The city's proximity to the Pacific Ocean also influences its weather patterns, with maritime air masses bringing moisture-laden air inland. However, despite the overall wetness of the climate, there is a great variance in local climates within the Seattle area.",
            "llm_input_query": "What factors contribute to the variance in local climates in the Seattle area?",
            "llm_output": "Several factors contribute to the variance in local climates in the Seattle area. One significant factor is the presence of the Olympic Mountains to the west of the city. These mountains act as a barrier, causing the 'rain shadow effect' where the western slopes receive abundant rainfall while the eastern slopes experience much drier conditions. Additionally, Seattle's proximity to Puget Sound and other bodies of water can create microclimates, with areas closer to the water experiencing milder temperatures due to the moderating influence of the water. Furthermore, elevation plays a role, with higher elevations generally being cooler and receiving more precipitation compared to lower-lying areas. Urban heat island effects can also impact local climates, with downtown areas typically being warmer than surrounding suburbs and rural areas.",
        }


print("\n  Factual Consistency   is:")
print(inspeq_instance.factual_consistency(input_data))
```

#### Grammatical Correctness:

Assess the grammatical accuracy of the generated text.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="Your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "Seattle is known for its wet climate due to its location in the Pacific Northwest region of the United States. From 1981 to 2010, the average annual precipitation measured at Seattle-Tacoma International Airport was 37.49 inches (952 mm). This significant amount of rainfall contributes to lush vegetation and a generally green landscape throughout the year. The city's proximity to the Pacific Ocean also influences its weather patterns, with maritime air masses bringing moisture-laden air inland. However, despite the overall wetness of the climate, there is a great variance in local climates within the Seattle area.",
            "llm_input_query": "What factors contribute to the variance in local climates in the Seattle area?",
            "llm_output": "Several factors contribute to the variance in local climates in the Seattle area. One significant factor is the presence of the Olympic Mountains to the west of the city. These mountains act as a barrier, causing the 'rain shadow effect' where the western slopes receive abundant rainfall while the eastern slopes experience much drier conditions. Additionally, Seattle's proximity to Puget Sound and other bodies of water can create microclimates, with areas closer to the water experiencing milder temperatures due to the moderating influence of the water. Furthermore, elevation plays a role, with higher elevations generally being cooler and receiving more precipitation compared to lower-lying areas. Urban heat island effects can also impact local climates, with downtown areas typically being warmer than surrounding suburbs and rural areas.",
        }


print("\n  Grammatical correctness response  is:")
print(inspeq_instance.grammatical_correctness(input_data))
```

#### Do Not Use Keywords:

Identify and evaluate the use of specific keywords or phrases.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="Your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "Seattle is known for its wet climate due to its location in the Pacific Northwest region of the United States. From 1981 to 2010, the average annual precipitation measured at Seattle-Tacoma International Airport was 37.49 inches (952 mm). This significant amount of rainfall contributes to lush vegetation and a generally green landscape throughout the year. The city's proximity to the Pacific Ocean also influences its weather patterns, with maritime air masses bringing moisture-laden air inland. However, despite the overall wetness of the climate, there is a great variance in local climates within the Seattle area.",
            "llm_input_query": "What factors contribute to the variance in local climates in the Seattle area?",
            "llm_output": "Several factors contribute to the variance in local climates in the Seattle area. One significant factor is the presence of the Olympic Mountains to the west of the city. These mountains act as a barrier, causing the 'rain shadow effect' where the western slopes receive abundant rainfall while the eastern slopes experience much drier conditions. Additionally, Seattle's proximity to Puget Sound and other bodies of water can create microclimates, with areas closer to the water experiencing milder temperatures due to the moderating influence of the water. Furthermore, elevation plays a role, with higher elevations generally being cooler and receiving more precipitation compared to lower-lying areas. Urban heat island effects can also impact local climates, with downtown areas typically being warmer than surrounding suburbs and rural areas.",
        }


print("\n  Do not use keywords response  is:")
print(inspeq_instance.do_not_use_keywords(input_data))
```

#### Fluency:

Assess the overall smoothness and fluency of the generated text

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="Your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "Seattle is known for its wet climate due to its location in the Pacific Northwest region of the United States. From 1981 to 2010, the average annual precipitation measured at Seattle-Tacoma International Airport was 37.49 inches (952 mm). This significant amount of rainfall contributes to lush vegetation and a generally green landscape throughout the year. The city's proximity to the Pacific Ocean also influences its weather patterns, with maritime air masses bringing moisture-laden air inland. However, despite the overall wetness of the climate, there is a great variance in local climates within the Seattle area.",
            "llm_input_query": "What factors contribute to the variance in local climates in the Seattle area?",
            "llm_output": "Several factors contribute to the variance in local climates in the Seattle area. One significant factor is the presence of the Olympic Mountains to the west of the city. These mountains act as a barrier, causing the 'rain shadow effect' where the western slopes receive abundant rainfall while the eastern slopes experience much drier conditions. Additionally, Seattle's proximity to Puget Sound and other bodies of water can create microclimates, with areas closer to the water experiencing milder temperatures due to the moderating influence of the water. Furthermore, elevation plays a role, with higher elevations generally being cooler and receiving more precipitation compared to lower-lying areas. Urban heat island effects can also impact local climates, with downtown areas typically being warmer than surrounding suburbs and rural areas.",
        }


print("\n  Fluency is:")
print(inspeq_instance.fluency(input_data))
```

#### Answer Relevance:

Determine the relevance of the generated text in the context of a given query or

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="Your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "Seattle is known for its wet climate due to its location in the Pacific Northwest region of the United States. From 1981 to 2010, the average annual precipitation measured at Seattle-Tacoma International Airport was 37.49 inches (952 mm). This significant amount of rainfall contributes to lush vegetation and a generally green landscape throughout the year. The city's proximity to the Pacific Ocean also influences its weather patterns, with maritime air masses bringing moisture-laden air inland. However, despite the overall wetness of the climate, there is a great variance in local climates within the Seattle area.",
            "llm_input_query": "What factors contribute to the variance in local climates in the Seattle area?",
            "llm_output": "Several factors contribute to the variance in local climates in the Seattle area. One significant factor is the presence of the Olympic Mountains to the west of the city. These mountains act as a barrier, causing the 'rain shadow effect' where the western slopes receive abundant rainfall while the eastern slopes experience much drier conditions. Additionally, Seattle's proximity to Puget Sound and other bodies of water can create microclimates, with areas closer to the water experiencing milder temperatures due to the moderating influence of the water. Furthermore, elevation plays a role, with higher elevations generally being cooler and receiving more precipitation compared to lower-lying areas. Urban heat island effects can also impact local climates, with downtown areas typically being warmer than surrounding suburbs and rural areas.",
        }
print("\n  Answer relevance is:")
print(inspeq_instance.answer_relevance(input_data))
```

#### Word Limit Test:

Check if the generated text adheres to specified word limits.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="Your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "Seattle is known for its wet climate due to its location in the Pacific Northwest region of the United States. From 1981 to 2010, the average annual precipitation measured at Seattle-Tacoma International Airport was 37.49 inches (952 mm). This significant amount of rainfall contributes to lush vegetation and a generally green landscape throughout the year. The city's proximity to the Pacific Ocean also influences its weather patterns, with maritime air masses bringing moisture-laden air inland. However, despite the overall wetness of the climate, there is a great variance in local climates within the Seattle area.",
            "llm_input_query": "What factors contribute to the variance in local climates in the Seattle area?",
            "llm_output": "Several factors contribute to the variance in local climates in the Seattle area. One significant factor is the presence of the Olympic Mountains to the west of the city. These mountains act as a barrier, causing the 'rain shadow effect' where the western slopes receive abundant rainfall while the eastern slopes experience much drier conditions. Additionally, Seattle's proximity to Puget Sound and other bodies of water can create microclimates, with areas closer to the water experiencing milder temperatures due to the moderating influence of the water. Furthermore, elevation plays a role, with higher elevations generally being cooler and receiving more precipitation compared to lower-lying areas. Urban heat island effects can also impact local climates, with downtown areas typically being warmer than surrounding suburbs and rural areas.",
        }


print("\n  word_limit_test is:")
print(inspeq_instance.word_limit_test(input_data))
```

#### Response Tone:

Assess the tone and style of the generated response.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="Your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "Seattle is known for its wet climate due to its location in the Pacific Northwest region of the United States. From 1981 to 2010, the average annual precipitation measured at Seattle-Tacoma International Airport was 37.49 inches (952 mm). This significant amount of rainfall contributes to lush vegetation and a generally green landscape throughout the year. The city's proximity to the Pacific Ocean also influences its weather patterns, with maritime air masses bringing moisture-laden air inland. However, despite the overall wetness of the climate, there is a great variance in local climates within the Seattle area.",
            "llm_input_query": "What factors contribute to the variance in local climates in the Seattle area?",
            "llm_output": "Several factors contribute to the variance in local climates in the Seattle area. One significant factor is the presence of the Olympic Mountains to the west of the city. These mountains act as a barrier, causing the 'rain shadow effect' where the western slopes receive abundant rainfall while the eastern slopes experience much drier conditions. Additionally, Seattle's proximity to Puget Sound and other bodies of water can create microclimates, with areas closer to the water experiencing milder temperatures due to the moderating influence of the water. Furthermore, elevation plays a role, with higher elevations generally being cooler and receiving more precipitation compared to lower-lying areas. Urban heat island effects can also impact local climates, with downtown areas typically being warmer than surrounding suburbs and rural areas.",
        }


print("\n  response_tone is:")
print(inspeq_instance.response_tone(input_data))
```

#### Conceptual Similarity:

Measure how closely the generated text aligns with the intended conceptual content.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="Your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "Seattle is known for its wet climate due to its location in the Pacific Northwest region of the United States. From 1981 to 2010, the average annual precipitation measured at Seattle-Tacoma International Airport was 37.49 inches (952 mm). This significant amount of rainfall contributes to lush vegetation and a generally green landscape throughout the year. The city's proximity to the Pacific Ocean also influences its weather patterns, with maritime air masses bringing moisture-laden air inland. However, despite the overall wetness of the climate, there is a great variance in local climates within the Seattle area.",
            "llm_input_query": "What factors contribute to the variance in local climates in the Seattle area?",
            "llm_output": "Several factors contribute to the variance in local climates in the Seattle area. One significant factor is the presence of the Olympic Mountains to the west of the city. These mountains act as a barrier, causing the 'rain shadow effect' where the western slopes receive abundant rainfall while the eastern slopes experience much drier conditions. Additionally, Seattle's proximity to Puget Sound and other bodies of water can create microclimates, with areas closer to the water experiencing milder temperatures due to the moderating influence of the water. Furthermore, elevation plays a role, with higher elevations generally being cooler and receiving more precipitation compared to lower-lying areas. Urban heat island effects can also impact local climates, with downtown areas typically being warmer than surrounding suburbs and rural areas.",
        }

print("\n  conceptual_similarity is:")
print(inspeq_instance.conceptual_similarity(input_data))
```
#### Readability:


#### Usage

```python
from inspeq.client import Evaluator


API_KEY="Your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "Seattle is known for its wet climate due to its location in the Pacific Northwest region of the United States. From 1981 to 2010, the average annual precipitation measured at Seattle-Tacoma International Airport was 37.49 inches (952 mm). This significant amount of rainfall contributes to lush vegetation and a generally green landscape throughout the year. The city's proximity to the Pacific Ocean also influences its weather patterns, with maritime air masses bringing moisture-laden air inland. However, despite the overall wetness of the climate, there is a great variance in local climates within the Seattle area.",
            "llm_input_query": "What factors contribute to the variance in local climates in the Seattle area?",
            "llm_output": "Several factors contribute to the variance in local climates in the Seattle area. One significant factor is the presence of the Olympic Mountains to the west of the city. These mountains act as a barrier, causing the 'rain shadow effect' where the western slopes receive abundant rainfall while the eastern slopes experience much drier conditions. Additionally, Seattle's proximity to Puget Sound and other bodies of water can create microclimates, with areas closer to the water experiencing milder temperatures due to the moderating influence of the water. Furthermore, elevation plays a role, with higher elevations generally being cooler and receiving more precipitation compared to lower-lying areas. Urban heat island effects can also impact local climates, with downtown areas typically being warmer than surrounding suburbs and rural areas.",
        }

print("\n  Readability is:")
print(inspeq_instance.readability(input_data))
```

#### Coherence :
Coherence metric evaluates how well the model generates coherent and logical responses that align with the context of the question.

#### Usage

```python
from inspeq.client import Evaluator


API_KEY="Your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "Seattle is known for its wet climate due to its location in the Pacific Northwest region of the United States. From 1981 to 2010, the average annual precipitation measured at Seattle-Tacoma International Airport was 37.49 inches (952 mm). This significant amount of rainfall contributes to lush vegetation and a generally green landscape throughout the year. The city's proximity to the Pacific Ocean also influences its weather patterns, with maritime air masses bringing moisture-laden air inland. However, despite the overall wetness of the climate, there is a great variance in local climates within the Seattle area.",
            "llm_input_query": "What factors contribute to the variance in local climates in the Seattle area?",
            "llm_output": "Several factors contribute to the variance in local climates in the Seattle area. One significant factor is the presence of the Olympic Mountains to the west of the city. These mountains act as a barrier, causing the 'rain shadow effect' where the western slopes receive abundant rainfall while the eastern slopes experience much drier conditions. Additionally, Seattle's proximity to Puget Sound and other bodies of water can create microclimates, with areas closer to the water experiencing milder temperatures due to the moderating influence of the water. Furthermore, elevation plays a role, with higher elevations generally being cooler and receiving more precipitation compared to lower-lying areas. Urban heat island effects can also impact local climates, with downtown areas typically being warmer than surrounding suburbs and rural areas.",
        }

print("\n  Coherence is:")
print(inspeq_instance.coherence(input_data))
```
