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
