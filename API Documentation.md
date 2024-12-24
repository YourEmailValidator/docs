# YourEmailValidator API Documentation

YourEmailValidator provides a reliable email validation service through RESTful APIs. Our service helps you validate email addresses, check for disposable email providers, and verify domain MX records.

## Table of Contents

- [Authentication](#authentication)
- [Rate Limits](#rate-limits)
- [Base URL](#base-url)
- [Endpoints](#endpoints)
- [Response Format](#response-format)
- [Error Handling](#error-handling)
- [Account Types](#account-types)
- [Code Examples](#code-examples)

## Authentication

All API requests require an API key to be included in the header:

```http
Authorization: Bearer your-api-key-here
```

To obtain an API key, sign up at [youremailvalidator.com](https://youremailvalidator.com).

## Rate Limits

- Free tier: 100 requests/day
- Basic tier: 10,000 requests/day
- DONATUR tier: 100,000 requests/day + bulk validation access

## Base URL

```
https://youremailvalidator.com/api/v1
```

## Endpoints

### Single Email Validation

`POST /validate-email`

Validates a single email address for format, disposable status, and MX records.

**Request Body:**

```json
{
  "email": "user@example.com",
  "allow_smtputf8": false,
  "allow_empty_local": false,
  "allow_quoted_local": false,
  "allow_domain_literal": false,
  "allow_display_name": false,
  "check_deliverability": true,
  "globally_deliverable": true,
  "timeout": 10
}
```

**Response:**

```json
{
  "email": "user@example.com",
  "is_valid": true,
  "message": "Email is valid."
}
```

### Check Disposable Email

`POST /check-disposable`

Checks if an email address uses a disposable email provider.

**Request Body:**

```json
{
  "email": "user@example.com"
}
```

**Response:**

```json
{
  "email": "user@example.com",
  "is_valid": true,
  "message": "Email is not disposable."
}
```

### Check MX Records

`POST /check-mx-record`

Verifies if the email domain has valid MX records.

**Request Body:**

```json
{
  "email": "user@example.com"
}
```

**Response:**

```json
{
  "email": "user@example.com",
  "is_valid": true,
  "message": "Email has valid MX records."
}
```

### Bulk Email Validation (DONATUR Only)

`POST /bulk-email-validate`

Validates multiple email addresses in a single request.

**Request Body:**

```json
{
  "email": ["user1@example.com", "user2@example.com", "user3@example.com"]
}
```

**Response:**

```json
[
  {
    "email": "user1@example.com",
    "is_valid": true,
    "message": "Email is valid."
  },
  {
    "email": "user2@example.com",
    "is_valid": false,
    "message": "Invalid email format."
  },
  {
    "email": "user3@example.com",
    "is_valid": true,
    "message": "Email is valid."
  }
]
```

### Check Bulk Access

`GET /check-bulk-access`

Checks if the current API key has access to bulk validation.

**Response:**

```json
{
  "has_access": true,
  "current_status": "DONATUR",
  "required_status": "DONATUR",
  "upgrade_required": false
}
```

## Response Format

All successful responses follow this format:

```json
{
  "email": "string",
  "is_valid": "boolean",
  "message": "string"
}
```

## Error Handling

The API uses standard HTTP status codes:

- `200`: Success
- `400`: Bad Request
- `401`: Unauthorized
- `403`: Forbidden
- `429`: Too Many Requests
- `500`: Internal Server Error

Error responses include a detail message:

```json
{
  "detail": "Error message here"
}
```

## Account Types

1. **Free Tier**

   - Basic email validation
   - 100 requests per day
   - Standard support

2. **DONATUR Tier**
   - All Basic tier features
   - 100,000 requests per day
   - Bulk validation (up to 1,000 emails per request)
   - Premium support
   - Advanced validation options
   - Custom timeout settings

## Code Examples

### Python

```python
import requests

api_key = "your-api-key"
headers = {"Authorization": f"Bearer {api_key}"}

# Single email validation
response = requests.post(
    "https://youremailvalidator.com/api/v1/validate-email",
    headers=headers,
    json={"email": "user@example.com"}
)

print(response.json())
```

### Node.js

```javascript
const axios = require("axios");

const apiKey = "your-api-key";
const headers = { Authorization: `Bearer ${apiKey}` };

// Single email validation
axios
  .post(
    "https://youremailvalidator.com/api/v1/validate-email",
    { email: "user@example.com" },
    { headers }
  )
  .then((response) => console.log(response.data))
  .catch((error) => console.error(error));
```

### cURL

```bash
curl -X POST \
  -H "Authorization: Bearer your-api-key" \
  -H "Content-Type: application/json" \
  -d '{"email":"user@example.com"}' \
  https://youremailvalidator.com/api/v1/validate-email
```
