# Inspeq Metrics

This document provides an overview of the metrics available in the Inspeq AI SDK, along with their definitions and usage examples.

#### Available Metrics
<details> <summary>RESPONSE_TONE</summary>

Assess the tone and style of the generated response.

Usage

```python
metrics_list = ["RESPONSE_TONE"]

input_data = [{
    "response": "Paris is the capital of France."
}]

```
</details>

<details>
<summary>ANSWER_RELEVANCE</summary>

Measures the degree to which the generated content directly addresses and pertains to the specific question or prompt provided by the user.


Usage
```python
metrics_list = ["ANSWER_RELEVANCE"]

input_data = [{
    "prompt": "What is the capital of France?",
    "response": "Paris is the capital of France."
}]
```
</details>
 <details>
<summary>FACTUAL_CONSISTENCY</summary>

Measures the extent of the model hallucinating i.e. model is making up a response based on its imagination or response is grounded in the context supplied


Usage
```python
metrics_list = ["FACTUAL_CONSISTENCY"]

input_data = [{
    "context": "Paris is the capital of France and its largest city.",
    "response": "Paris is the capital of France."
}]
```
</details>
<details>
<summary>CONCEPTUAL_SIMILARITY</summary>

Measures the extent to which the model response aligns with and reflects the underlying ideas or concepts present in the provided context or prompt.

Usage
```python
metrics_list = ["CONCEPTUAL_SIMILARITY"]

input_data = [{
    "context": "Paris is the capital of France and its largest city.",
    "response": "Paris is the capital of France."
}]
```
</details> 
<details>
<summary>READABILITY</summary>

Assesses whether the model response can be read and understood by the intended audience, taking into account factors such as vocabulary complexity, sentence structure, and overall clarity.

Usage
```python
metrics_list = ["READABILITY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```
</details>
 <details>
<summary>COHERENCE</summary>

Evaluates how well the model generates coherent and logical responses that align with the context of the question.

Usage

```python
metrics_list = ["COHERENCE"]

input_data = [{
    "context": "Paris is the capital of France and its largest city.",
    "response": "Paris is the capital of France."
}]

```
</details> <details>
<summary>CLARITY</summary>

Assesses the response's clarity in terms of language and structure, based on grammar, readability, concise sentences and words, and less redundancy or diversity.

Usage

```python
metrics_list = ["CLARITY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```
</details> <details>
<summary>DIVERSITY</summary>

Assesses the diversity of vocabulary used in a piece of text.

Usage

```python
metrics_list = ["DIVERSITY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```
</details> <details>
<summary>CREATIVITY</summary>

Assesses the ability of the model to generate imaginative, and novel responses that extend beyond standard or expected answers.

Usage

```python
metrics_list = ["CREATIVITY"]

input_data = [{
    "response": "Paris is the capital of France.",
    "context": "Paris is the capital of France and its largest city."
}]
```
</details>
<!-- * DATA_LEAKAGE -->
<!-- * DO_NOT_USE_KEYWORDS -->
<!-- * MODEL_REFUSAL -->
<details>
<summary>NARRATIVE_CONTINUITY</summary>

Measures the consistency and logical flow of the response throughout the generated text, ensuring that the progression of events remains coherent and connected. 

Usage
```python
metrics_list = ["NARRATIVE_CONTINUITY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```
</details>
<!-- * WORD_COUNT_LIMIT -->
<!-- * INSECURE_OUTPUT -->
<!-- * ANSWER_FLUENCY -->
<details>
<summary>GRAMMATICAL_CORRECTNESS</summary></br>

Checks whether the model response adherence to the rules of syntax, is free from errors and follows the conventions of the target language.

Usage

```python
metrics_list = ["GRAMMATICAL_CORRECTNESS"]

input_data = [{
    "response": "Paris is the capital of France."
}]
```
</details>

# Metrics for Summarization
<details>
<summary>BERT Score</summary></br>

**BERTScore**  is a metric that evaluates how semantically similar a generated summary is to a reference summary using BERT's contextual embeddings. Instead of relying on exact word matches, it compares the meaning of words in the summaries, offering a deeper understanding of content similarity. This makes BERTScore particularly useful for summarization tasks, as it captures nuances in meaning rather than just surface-level similarities.

```python
metrics_list = ["BERT_SCORE"]
input_data= [{
    "llm_input_query": "string",
    "llm_input_context": "A group of researchers have developed a plant-based alternative to plastic packaging that is both biodegradable and sustainable. This innovation could help reduce the environmental impact of single-use plastics.",
    "llm_output": "Researchers create biodegradable, plant-based alternative to plastic packaging, aiming to mitigate the environmental effects of single-use plastics."
  }]
```
</details>
<details>
<summary>Bleu Score</summary></br>
**BLEU score (Bilingual Evaluation Understudy)** is a metric used to evaluate the quality of text generated by models, such as summaries, by comparing it to one or more reference texts. For summarization, it measures how many words or phrases in the generated summary match the reference summary, with a focus on exact word matches, n-grams (sequences of words), and word order. A higher BLEU score indicates a closer match to the reference summary.

```python
metrics_list = ["BLEU_SCORE"]
input_data= [{
    "llm_input_query": "string",
    "llm_input_context": "A group of researchers have developed a plant-based alternative to plastic packaging that is both biodegradable and sustainable. This innovation could help reduce the environmental impact of single-use plastics.",
    "llm_output": "Researchers create biodegradable, plant-based alternative to plastic packaging, aiming to mitigate the environmental effects of single-use plastics."
  }]
```
</details>
<details>
<summary>Compression Score</summary></br>
<b>The compression score</b> in summarization tasks measures the ratio of the length of the generated summary to the length of the original text. It quantifies how much the text has been condensed. Typically, a lower compression score indicates a more concise summary, while a higher score suggests the summary is closer in length to the original text.

```python
metrics_list = ["COMPRESSION_SCORE"]
input_data= [{
    "llm_input_query": "string",
    "llm_input_context": "A group of researchers have developed a plant-based alternative to plastic packaging that is both biodegradable and sustainable. This innovation could help reduce the environmental impact of single-use plastics.",
    "llm_output": "Researchers create biodegradable, plant-based alternative to plastic packaging, aiming to mitigate the environmental effects of single-use plastics."
  }]
```
</details>
<details>
<summary>Cosine Similarity Score</summary></br>
<b>Cosine similarity</b> is used to measure the similarity between the original text and the generated summary. It treats both the original and the summary as vectors in a multi-dimensional space, where each dimension represents a word or token. The cosine similarity metric computes the cosine of the angle between these two vectors, providing a value between -1 and 1. A value closer to 1 indicates high similarity, while a value closer to 0 or negative values suggests low similarity.

```python
metrics_list = ["COSINE_SIMILARITY_SCORE"]
input_data= [{
    "llm_input_query": "string",
    "llm_input_context": "A group of researchers have developed a plant-based alternative to plastic packaging that is both biodegradable and sustainable. This innovation could help reduce the environmental impact of single-use plastics.",
    "llm_output": "Researchers create biodegradable, plant-based alternative to plastic packaging, aiming to mitigate the environmental effects of single-use plastics."
  }]
```
</details>
<details>
<summary>Density Score</summary></br>
<b>Density score</b> is a metric that measures how much of the generated summary reuses words from the original text and how those words are distributed within the summary. A higher density score indicates that the summary is more extractive, meaning it contains more verbatim content from the original text. Lower density scores suggest that the summary is more abstractive, meaning it paraphrases or generates new content rather than copying from the original text.

```python
metrics_list = ["DENSITY_SCORE"]
input_data= [{
    "llm_input_query": "string",
    "llm_input_context": "A group of researchers have developed a plant-based alternative to plastic packaging that is both biodegradable and sustainable. This innovation could help reduce the environmental impact of single-use plastics.",
    "llm_output": "Researchers create biodegradable, plant-based alternative to plastic packaging, aiming to mitigate the environmental effects of single-use plastics."
  }]
```
</details>
<details>
<summary>Euclidian distance</summary></br>

<b>The Euclidean distance</b> score can be used to evaluate how close a generated summary is to a reference summary (or the original text). A smaller distance indicates that the two texts (the summary and reference) are more similar in terms of their underlying feature representations.

```python
metrics_list = ["EUCLIDEAN_DISTANCE_SCORE"]
input_data= [{
    "llm_input_query": "string",
    "llm_input_context": "A group of researchers have developed a plant-based alternative to plastic packaging that is both biodegradable and sustainable. This innovation could help reduce the environmental impact of single-use plastics.",
    "llm_output": "Researchers create biodegradable, plant-based alternative to plastic packaging, aiming to mitigate the environmental effects of single-use plastics."
  }]
```
</details>
<details>
<summary>Fuzzy Score</summary></br>
<b>Fuzzy Score</b> measures the similarity between two pieces of text (the original text and the generated summary) based on approximate matching rather than exact matching. It is useful for capturing partial matches or similarities when exact word or phrase matching might not be suitable, especially when the generated summary paraphrases or uses synonyms of the original text.</br>

<h3>Key Aspects of Fuzzy Score in Summarization:</h3>

* Partial Matching: Unlike traditional exact matching metrics (like BLEU or ROUGE), fuzzy matching considers how similar two texts are even if the words or phrases are not identical but are close in meaning or structure.
* Levenshtein Distance: Often, fuzzy scores are computed using string-matching algorithms like Levenshtein distance, which calculates the minimum number of single-character edits (insertions, deletions, or substitutions) needed to turn one string into another.
* Similarity Score: The fuzzy score is typically a percentage between 0 and 100, where:
100 means the two texts are identical.
A lower score indicates less similarity.
A higher score indicates more similarity, even if the exact words differ.

```python
metrics_list = ["FUZZY_SCORE"]
input_data= [{
    "llm_input_query": "string",
    "llm_input_context": "A group of researchers have developed a plant-based alternative to plastic packaging that is both biodegradable and sustainable. This innovation could help reduce the environmental impact of single-use plastics.",
    "llm_output": "Researchers create biodegradable, plant-based alternative to plastic packaging, aiming to mitigate the environmental effects of single-use plastics."
  }]
```
</details>
<details>
<summary>Meteor Score</summary></br>

METEOR score (Metric for Evaluation of Translation with Explicit ORdering) is a metric used to evaluate the quality of generated summaries by comparing them to reference summaries. Originally designed for machine translation, METEOR has been adapted for summarization tasks as well.</br>
<h3>Key Features of Meteor Score</h3>:

* Precision and Recall: METEOR combines precision (the fraction of relevant words in the generated summary) and recall (the fraction of relevant words from the reference summaries that are captured in the generated summary).

* Synonymy and Stemming: It accounts for variations in wording by including synonyms, stemming (reducing words to their root forms), and paraphrases.

* Chunk Matching: METEOR evaluates the matches between the generated and reference texts in terms of phrases or chunks, rather than individual words, which helps capture meaning even when exact word matches are not present.

* Penalty for Fragmentation: It includes penalties for matches that are scattered throughout the summary, encouraging more coherent and consistent outputs.

```python
metrics_list = ["METEOR_SCORE"]
input_data= [{
    "llm_input_query": "string",
    "llm_input_context": "A group of researchers have developed a plant-based alternative to plastic packaging that is both biodegradable and sustainable. This innovation could help reduce the environmental impact of single-use plastics.",
    "llm_output": "Researchers create biodegradable, plant-based alternative to plastic packaging, aiming to mitigate the environmental effects of single-use plastics."
  }]
```
</details>
<details>
<summary>Rouge Score</summary>
ROUGE score (Recall-Oriented Understudy for Gisting Evaluation) is a set of metrics used to evaluate the quality of generated summaries by comparing them to one or more reference summaries. ROUGE focuses primarily on the overlap of content between the generated and reference summaries. We use `Rouge-L` for our implementation.</br>
<h3>Key variants of Rouge:</h3>

* ROUGE-N: Measures the overlap of n-grams (sequences of n words) between the generated and reference summaries. Commonly used variants include ROUGE-1 (unigrams), ROUGE-2 (bigrams), and ROUGE-3 (trigrams).

* ROUGE-L: Measures the longest common subsequence (LCS) between the generated and reference summaries. It evaluates the fluency and coherence by considering the order of words.

* ROUGE-W: A variant of ROUGE-L that weights the LCS based on its length, providing a more nuanced evaluation of longer matches.

* ROUGE-S: Measures the overlap of skip-bigrams, which are pairs of words in the same order but not necessarily adjacent.

```python
metrics_list = ["ROUGE_SCORE"]
input_data= [{
    "llm_input_query": "string",
    "llm_input_context": "A group of researchers have developed a plant-based alternative to plastic packaging that is both biodegradable and sustainable. This innovation could help reduce the environmental impact of single-use plastics.",
    "llm_output": "Researchers create biodegradable, plant-based alternative to plastic packaging, aiming to mitigate the environmental effects of single-use plastics."
  }]
```
</details>

# Metric Definitions and Usage

### General Usage Pattern

For all metrics, use the following pattern:


```python
from inspeq.client import InspeqEval

# Initialize the client
INSPEQ_API_KEY = "your_inspeq_sdk_key"
INSPEQ_PROJECT_ID = "your_project_id"
INSPEQ_API_URL = "your_inspeq_backend_url"  # Required only for on-prem customers

inspeq_eval = InspeqEval(inspeq_api_key=INSPEQ_API_KEY, inspeq_project_id=INSPEQ_PROJECT_ID)

# Prepare input data
input_data = [{
    "prompt": "Your prompt here",
    "response": "Your response here",
    "context": "Your context here (if applicable)"
}]

# Define the metric to evaluate
metrics_list = ["METRIC_NAME"]

try:
    results = inspeq_eval.evaluate_llm_task(
        metrics_list=metrics_list,
        input_data=input_data,
        task_name="your_task_name"
    )
    print(results)
except Exception as e:
    print(f"An error occurred: {str(e)}")

```

Replace __METRIC_NAME__ with the specific metric you want to evaluate. 

## Below are examples for each metric:
<!-- 
__DATA_LEAKAGE__

Detects whether the model response contains any personal information such as credit card numbers, phone numbers, emails, URLs, etc.

Usage

```python
metrics_list = ["DATA_LEAKAGE"]

input_data = [{
    "response": "Paris is the capital of France."
}]
``` -->

<!-- __DO_NOT_USE_KEYWORDS__

Identifies and evaluate the use of specific keywords or phrases.

Usage

```python
metrics_list = ["DO_NOT_USE_KEYWORDS"]

input_data = [{
    "response": "Paris is the capital of France."
}]

``` -->

<!-- __MODEL_REFUSAL__

Identifies rejections in the model responses.

Usage

```python
metrics_list = ["MODEL_REFUSAL"]

input_data = [{
    "response": "Paris is the capital of France."
}] -->
<!-- ``` -->


<!-- __WORD_COUNT_LIMIT__

Checks if the generated text adheres to specified word limits.

Usage

```python
metrics_list = ["WORD_COUNT_LIMIT"]

input_data = [{
    "prompt": "What is the capital of France?",
    "response": "Paris is the capital of France."
}]
``` -->

<!-- __INSECURE_OUTPUT__

 Detects any potentially harmful responses that could lead to system vulnerabilities. Eg. detects any  mallicious code, Javascript or Markdown generated by the model that could result in XSS.

Usage
```python
metrics_list = ["INSECURE_OUTPUT"]

input_data = [{
    "response": "import os\nprint(os.getcwd())"
}]
```  -->


<!-- __ANSWER_FLUENCY__

Assesses the smoothness and coherence with which the model generates language that is easily understandable and grammatically correct.

Usage

```python
metrics_list = ["ANSWER_FLUENCY"]

input_data = [{
    "response": "Paris is the capital of France."
}]
``` -->

__Note on Configuration__

The SDK uses default configurations for each metric. You can override these defaults by providing your own config_input parameter when calling evaluate_llm_task.
