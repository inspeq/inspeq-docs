# API Endpoints

## Evaluate LLM Task

Evaluates LLM outputs using specified metrics.

### Endpoint

```
POST /sdk/evaluate_llm
```

### Request Structure

```json
{
  "request_body": {
    "project_id": "your-project-id",
    "secret_key": "your-secret-key",
    "task_name": "Task Description",
    "metrics": [
      "RESPONSE_TONE",
      "BIAS"
      "READABILITY",
      "COHERENCE",
      "ANSWER_RELEVANCE",
      "FACTUAL_CONSISTENCY",
      "BLEU_SCORE"
    ],
    "input_data": [
      {
        "prompt": "Your prompt text",
        "context": "Additional context",
        "response": "LLM response to evaluate"
      }
    ]
  }
}
```

### Optional Configuration

You can customize metric thresholds and labels:

```json
{
  "request_body": {
    // ... other parameters
  },
  "metrics_config": {
    "response_tone_config": {
      "threshold": 0.5,
      "custom_labels": ["Negative", "Positive"],
      "label_thresholds": [0, 0.6, 1]
    }
  }
}
```

### Response Example

```json
{
  "status": 200,
  "message": "2 evaluations successful, 4 evaluations failed",
  "results": [
    {
      "id": "673dbeed-9b3d-4852-a0cb-4fe9fe2989d9",
      "project_id": "37b2c450-9e24-4265-a5e9-11ae67425521",
      "task_name": "Example Task",
      "metric_name": "BLEU_SCORE_EVALUATION",
      "score": "0.31",
      "passed": false,
      "evaluation_details": {
        "actual_value": "0.314",
        "metric_labels": ["Poorly Conforming"],
        "threshold_score": "0.8"
      }
    }
    // ... additional results
  ],
  "user_id": "574999e7-619f-4b7a-be2f-dc84b446e5c0",
  "remaining_credits": 0
}
```

### Error Responses

| Status Code | Description |
|-------------|-------------|
| 400 | Bad Request - Invalid parameters |
| 401 | Unauthorized - Invalid credentials |
| 429 | Too Many Requests - Rate limit exceeded |
| 500 | Internal Server Error |

### Metric Types

For a complete list of available metrics and their descriptions, see our [Metrics Documentation](../metrics.md). 