# Explaination of Response Structure
### Example Input data

This is the example input data used to evaluate below metrics and get the respective response structure

```py
input_data =   {
        "prompt": "What are the key principles of object-oriented programming?",
        "context": '''Object-oriented programming (OOP) is a programming paradigm based on the concept of 'objects', which can contain data, in the form of fields, and code, in the form of procedures...''',
        "response": '''Object-oriented programming (OOP) revolves around four key principles: encapsulation, inheritance, polymorphism, and abstraction. Encapsulation refers to the bundling of data and methods that operate on the data into a single unit or class. Inheritance enables the creation of new classes based on existing ones, allowing for code reuse and hierarchical classification. Polymorphism allows objects to be treated as instances of their parent class, enabling flexibility and modularity in code design. Abstraction involves simplifying complex systems by focusing on essential properties and hiding implementation details.'''
    }
```

## Factual Consistency

### Definition

Factual Consistency (FC) pertains to the precision and correctness of information articulated in text produced by Large Language Models (LLMs). It involves the comparison of generated information with the given context, input, or anticipated factual knowledge.

### Response Structure

```json
{
  "metricName": "FACTUAL_CONSISTENCY_EVALUATION",
  "actualValue": 0.7631447911262512,
  "actualValueType": "FLOAT",
  "metricLabels": ["Consistent"],
  "others": {}
}
```

- `metricName`: Tells metric name
- `actualValue`: This can range from 0 to 1 (float values), actualValueType is the datatype
  of actualValue (will be float in this case)
- `actualValueType`: The datatype of actualValue, which will be float in this case.
- `others`: Additional metadata (currently not much relevant).
- `metricLabels`:This field categorizes actualValue into different ranges based on pre-defined thresholds.
  Possible labels for different actualValue for "FACTUAL_CONSISTENCY_EVALUATION" ranges:
  - Hallucinated (0-0.5)
  - Inconsistent (0.51-0.7)
  - Consistent (0.71 - 1)

## Response Tonality

### Definition

Tonality refers to the type of tone of the response.

### Response Structure

```json
{
  "metricName": "RESPONSE_TONE_EVALUATION",
  "actualValue": 0.6591,
  "actualValueType": "FLOAT",
  "metricLabels": ["Positive"],
  "others": {}
}
```

- `metricName`: Tells metric name
- `actualValue`: This can range from 0 to 1 (float values), actualValueType is the datatype
  of actualValue (will be float in this case)
- `actualValueType`: The datatype of actualValue, which will be float in this case.
- `others`: Additional metadata (currently not much relevant).
- `metricLabels`:This field categorizes actualValue into different ranges based on pre-defined thresholds.
  Possible labels for different actualValue for "RESPONSE_TONE_EVALUATION" ranges:
  - Negative (0-0.5)
  - Neutral (0.5)
  - Positive (0.5-1)

## Answer Fluency

### Definition

Fluency refers to the ability of the LLM to generate text that is grammatically correct, natural-sounding, and easy to read. 

### Response Structure

```json
{
  "metricName": "ANSWER_FLUENCY_EVALUATION",
  "actualValue": 1.0,
  "actualValueType": "FLOAT",
  "metricLabels": ["Fluent"],
  "others": {}
}
```

- `metricName`: Tells metric name
- `actualValue`: This can range from 0 to 1 (float values), actualValueType is the datatype
  of actualValue (will be float in this case)
- `actualValueType`: The datatype of actualValue, which will be float in this case.
- `others`: Additional metadata (currently not much relevant).
- `metricLabels`:This field categorizes actualValue into different ranges based on pre-defined thresholds.
  Possible labels for different actualValue for "ANSWER_FLUENCY_EVALUATION" ranges:
  - Not Fluent ( 0-0.5)
  - Moderately Fluent (0.51–0.7)
  - Fluent (0.71 - 1)

## Coherence

### Definition

The ability of the LLM to generate text that is organized, well-structured, and easy to understand.

### Response Structure

```json
{
  "metricName": "COHERENCE_EVALUATION",
  "actualValue": 0.8162152668558301,
  "actualValueType": "FLOAT",
  "metricLabels": ["Coherent"],
  "others": {}
}
```

- `metricName`: Tells metric name
- `actualValue`: This can range from 0 to 1 (float values), actualValueType is the datatype
  of actualValue (will be float in this case)
- `actualValueType`: The datatype of actualValue, which will be float in this case.
- `others`: Additional metadata (currently not much relevant).
- `metricLabels`:This field categorizes actualValue into different ranges based on pre-defined thresholds.
  Possible labels for different actualValue for "COHERENCE_EVALUATION" ranges:
  - Incoherent (0-0.5)
  - Slightly Coherent (0.51–0.7)
  - Coherent (0.71 - 1)

## Grammatical Correctness

### Definition

This metric refers to how grammatically correct the response generated.

### Response Structure

```json
{
  "metricName": "GRAMMATICAL_CORRECTNESS_EVALUATION",
  "actualValue": 1.0,
  "actualValueType": "FLOAT",
  "metricLabels": ["Correct"],
  "others": {}
}
```

- `metricName`: Tells metric name
- `actualValue`: This can range from 0 to 1 (float values), actualValueType is the datatype
  of actualValue (will be float in this case)
- `actualValueType`: The datatype of actualValue, which will be float in this case.
- `others`: Additional metadata (currently not much relevant).
- `metricLabels`:This field categorizes actualValue into different ranges based on pre-defined thresholds.
  Possible labels for different actualValue for "GRAMMATICAL_CORRECTNESS_EVALUATION" ranges:
  - Incorrect (0-0.5)
  - Partially Correct (0.51–0.7)
  - Correct (0.71 - 1)

## Answer Relevance

### Definition

Answer Relevance assesses the alignment between the model's responses and the intended meaning of the input.

### Response Structure

```json
{
  "metricName": "ANSWER_RELEVANCE_EVALUATION",
  "actualValue": 0.9981426000595093,
  "actualValueType": "FLOAT",
  "metricLabels": ["Relevant Answer"],
  "others": {}
}
```

- `metricName`: Tells metric name
- `actualValue`: This can range from 0 to 1 (float values), actualValueType is the datatype
  of actualValue (will be float in this case)
- `actualValueType`: The datatype of actualValue, which will be float in this case.
- `others`: Additional metadata (currently not much relevant).
- `metricLabels`:This field categorizes actualValue into different ranges based on pre-defined thresholds.
  Possible labels for different actualValue for "ANSWER_RELEVANCE_EVALUATION" ranges:
  - Irrelevant Answer (0-0.5)
  - Marginally Relevant Answer (0.51–0.7)
  - Relevant Answer (0.71 - 1)

## Readability

### Definition

Readability scores help assess whether the LLM’s generated text is appropriate for the target audience’s reading level.

### Response Structure

```json
{
  "metricName": "READABILITY_EVALUATION",
  "actualValue": 0.20579999999999998,
  "actualValueType": "FLOAT",
  "metricLabels": ["Sophisticated"],
  "others": {}
}
```

- `metricName`: Tells metric name
- `actualValue`: This can range from 0 to 1 (float values), actualValueType is the datatype
  of actualValue (will be float in this case)
- `actualValueType`: The datatype of actualValue, which will be float in this case.
- `others`: Additional metadata (currently not much relevant).
- `metricLabels`:This field categorizes actualValue into different ranges based on pre-defined thresholds.
  Possible labels for different actualValue for "READABILITY_EVALUATION" ranges:
  - Sophisticated (0 – 0.3)
  - Moderate (0.31 - 0.6)
  - Easy (0.61 - 1 )

## Clarity

### Definition

Clarity is a subjective metric and refers to the response’s clarity in terms of language and structure.

### Response Structure

```json
{
  "metricName": "GRAMMATICAL_CORRECTNESS_EVALUATION",
  "actualValue": 1.0,
  "actualValueType": "FLOAT",
  "metricLabels": ["Correct"],
  "others": {}
}
```

- `metricName`: Tells metric name
- `actualValue`: This can range from 0 to 1 (float values), actualValueType is the datatype
  of actualValue (will be float in this case)
- `actualValueType`: The datatype of actualValue, which will be float in this case.
- `others`: Additional metadata (currently not much relevant).
- `metricLabels`:This field categorizes actualValue into different ranges based on pre-defined thresholds.
  Possible labels for different actualValue for "GRAMMATICAL_CORRECTNESS_EVALUATION" ranges:
  - Not Clear (0-0.5)
  - Partially Clear (0.51–0.7)
  - Clear (0.71 - 1)

## Conceptual Similarity

### Definition

This refers to the semantic similarity or relatedness between response generated and provided context.


### Response Structure

```json
{
  "metricName": "CONCEPTUAL_SIMILARITY_EVALUATION",
  "actualValue": 0.7542403340339661,
  "actualValueType": "FLOAT",
  "metricLabels": ["Similar"],
  "others": {}
}
```

- `metricName`: Tells metric name
- `actualValue`: This can range from 0 to 1 (float values), actualValueType is the datatype
  of actualValue (will be float in this case)
- `actualValueType`: The datatype of actualValue, which will be float in this case.
- `others`: Additional metadata (currently not much relevant).
- `metricLabels`:This field categorizes actualValue into different ranges based on pre-defined thresholds.
  Possible labels for different actualValue for "CONCEPTUAL_SIMILARITY_EVALUATION" ranges:
  - Dissimilar (0-0.5)
  - Somewhat similar (0.51–0.7)
  - Similar (0.71 - 1)
