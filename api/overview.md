# API Overview

Inspeq AI provides a RESTful API that allows you to evaluate LLM outputs using our comprehensive suite of metrics. This API provides the same functionality as our SDK but can be accessed directly via HTTP requests.

## Base URL

```
https://prod-api.inspeq.ai/api/v2
```

## Authentication

All API requests require authentication using your project ID and secret key. These credentials can be obtained from the Inspeq AI platform after registration.
<!-- 
## Rate Limits

- Free tier: 200 evaluations and 20 requests per minute
- Enterprise tier: Custom limits based on your plan. Please contact us at support@inspeq.ai for more information. -->

## Response Format

All responses are returned in JSON format and include:
- HTTP status code
- Message describing the operation result
- Results array containing metric evaluations
- User ID and remaining credits information

For detailed response structure, see our [Response Structure Documentation](../ResponseStructure.md). 