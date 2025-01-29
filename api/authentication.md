# Authentication

## Obtaining Credentials

1. Register at [platform.inspeq.ai](https://platform.inspeq.ai)
2. Create a new project
3. Navigate to API Keys section
4. Copy your Project ID and Secret Key

## Required Headers

Include your credentials in the request body:

```json
{
  "request_body": {
    "project_id": "your-project-id",
    "secret_key": "your-secret-key",
    // ... other request parameters
  }
}
```

<!-- ## Optional Parameters

You can include additional identification parameters:

```json
{
  "request_body": {
    "client_id": "your-client-id",
    "identifier_type": "email",
    "identifier_value": "user@example.com",
    // ... other parameters
  }
} -->
```

## Security Best Practices

1. Never expose your secret key in client-side code
2. Rotate your keys periodically
3. Use environment variables to store credentials
4. Monitor API usage for unauthorized access 