# Quickstart

### Inspeqai Python SDK

Get started by simple example for evaluation of metrics.

#### Installation

To install inspeqai python sdk, you can follow these steps:

```bash
pip install inspeqai
```

Get latest version from [Here](https://pypi.org/project/inspeqai/)

#### Get API keys

Get your API keys from [Here](https://app.inspeq.ai/)

#### Usage

Create a file where you could use the functions provided by inspeq python sdk.

```python
from inspeq.client import Evaluator


API_KEY="Your_api_key"
inspeq_instance = Evaluator(sdk_api_key=API_KEY)


input_data = {
            "llm_input_context": "Seattle is known for its wet climate due to its location in the Pacific Northwest region of the United States. From 1981 to 2010, the average annual precipitation measured at Seattle-Tacoma International Airport was 37.49 inches (952 mm). This significant amount of rainfall contributes to lush vegetation and a generally green landscape throughout the year. The city's proximity to the Pacific Ocean also influences its weather patterns, with maritime air masses bringing moisture-laden air inland. However, despite the overall wetness of the climate, there is a great variance in local climates within the Seattle area.",
            "llm_input_query": "What factors contribute to the variance in local climates in the Seattle area?",
            "llm_output": "Several factors contribute to the variance in local climates in the Seattle area. One significant factor is the presence of the Olympic Mountains to the west of the city. These mountains act as a barrier, causing the 'rain shadow effect' where the western slopes receive abundant rainfall while the eastern slopes experience much drier conditions. Additionally, Seattle's proximity to Puget Sound and other bodies of water can create microclimates, with areas closer to the water experiencing milder temperatures due to the moderating influence of the water. Furthermore, elevation plays a role, with higher elevations generally being cooler and receiving more precipitation compared to lower-lying areas. Urban heat island effects can also impact local climates, with downtown areas typically being warmer than surrounding suburbs and rural areas.",
        }


inspeq_instance.get_all_metrices(input_data)
```

Result will display in your terminal once you run your main.py file.
