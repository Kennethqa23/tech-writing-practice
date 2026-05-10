# Payments API

## Overview
The payments API allows you to create and manage customer payments. Use this API to charge customers, track payment status, and handle transaction errors.

## Authentication
All requests must include an API key in the `Authorization` header.

```http
Authorization: Bearer YOUR_API_KEY
```

- Keep your API key secure
- Do not expose it in client-side code

## Base URL
```Bash
https://api.example.com/v1
```

# Create a Payment
**POST** `/payments`

Creates a new payment for a customer.

## Request

### Headers
|Name|Type|Required|Description|
|:--:|:--:|:------:|:---------:|
|Authorization|string|yes|Bearer API key|
|Content-Type|string|Yes|Must be `application/json`|

### Body
```json
{
"amount": 1000,
"currency": "USD",
"customer_id": "cus_123"
}
```

### Parameters
|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|amount|integer|yes|Amount in cents (e.g., 1000 = $10|
|currency|string|Yes|ISO 4217 currency code|
|customer_id|string|Yes|Unique identifier for the customer|

## Response
### 201 Created
```json
{
"id": "pay_458",
"status": "succeeded",
"amount": "1000"
"currency": "USD"
}
```

## Error Responses

### 400 Bad Request
```json
{
  "error": {
    "code": "invalid_request",
    "message": "Amount must be greater than 0"
  }
}
```

### 401 Unauthorized
```json
{
  "error": {
    "code": "unauthorized",
    "message": "Invalid API key"
  }
}
```
