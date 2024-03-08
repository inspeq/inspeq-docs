# Quickstart

### Inspeqai Python SDK

Get started by simple example for evaluation of metrics.

### Create a Virtual Environment in Linux or Windows

### Linux OS / MAC OS

### Using venv (Python 3)

1. Open a terminal.
2. Navigate to the directory where you want to create the virtual environment.
3. Run the following command:
```bash
   python3 -m venv venv
```
#### Activate it 
```bash
  source venv/bin/activate
```
### windows

1. Open a terminal.
2. Navigate to the directory where you want to create the virtual environment.
3. Run the following command:
```bash
   python -m venv venv
```
#### Activate it 
```bash
venv\Scripts\activate
```
#### Make sure your environment is activated everytime you use package

### SDK Installation

To install inspeqai python sdk, you can follow these steps:

```bash
pip install inspeqai
```

Get latest version from [Here](https://pypi.org/project/inspeqai/)

#### Get API keys

Get your API keys from [Here](https://app.inspeq.ai/)

#### Usage

Create a python file like main.py where you could use the functions provided by inspeq python sdk.

```python
from inspeq.client import Evaluator


API_KEY="Your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "Seattle is known for its wet climate due to its location in the Pacific Northwest region of the United States. From 1981 to 2010, the average annual precipitation measured at Seattle-Tacoma International Airport was 37.49 inches (952 mm). This significant amount of rainfall contributes to lush vegetation and a generally green landscape throughout the year. The city's proximity to the Pacific Ocean also influences its weather patterns, with maritime air masses bringing moisture-laden air inland. However, despite the overall wetness of the climate, there is a great variance in local climates within the Seattle area.",
            "llm_input_query": "What factors contribute to the variance in local climates in the Seattle area?",
            "llm_output": "Several factors contribute to the variance in local climates in the Seattle area. One significant factor is the presence of the Olympic Mountains to the west of the city. These mountains act as a barrier, causing the 'rain shadow effect' where the western slopes receive abundant rainfall while the eastern slopes experience much drier conditions. Additionally, Seattle's proximity to Puget Sound and other bodies of water can create microclimates, with areas closer to the water experiencing milder temperatures due to the moderating influence of the water. Furthermore, elevation plays a role, with higher elevations generally being cooler and receiving more precipitation compared to lower-lying areas. Urban heat island effects can also impact local climates, with downtown areas typically being warmer than surrounding suburbs and rural areas.",
        }

'''Note : Do not change the structure of input data keep the structure as it
is. Put your data at places of your_llm_input_context, your_llm_input_query
and your_llm_output .

'''

print("\n   grammatical_correctness is:")
print(inspeq_eval.grammatical_correctness(input_data))
#get all metrices in one function

print(inspeq_instance.get_all_metrices(input_data))

```
### All Metrics provided by Inspeq sdk

```py
    print("Factual Consistency:", inspeq_instance.factual_consistency(input_data))
    print("Answer Relevance:", inspeq_instance.answer_relevance(input_data))
    print("Response Tone:", inspeq_instance.response_tone(input_data))
    print("Grammatical Correctness:", inspeq_instance.grammatical_correctness(input_data))
    print("Fluency:", inspeq_instance.fluency(input_data))
    print("Do Not Use Keywords:", inspeq_instance.do_not_use_keywords(input_data))
    print("Word Limit Test:", inspeq_instance.word_limit_test(input_data))
    print("Conceptual Similarity:", inspeq_instance.conceptual_similarity(input_data))
    print("Coherence:", inspeq_instance.coherence(input_data))
    print("Readability:", inspeq_instance.readability(input_data))
    print("Clarity:", inspeq_instance.clarity(input_data))
    print("Get all metrics:", inspeq_instance.get_all_metrics(input_data))

```


Result will display in your terminal once you run your main.py file.
