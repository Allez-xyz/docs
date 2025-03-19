---
layout: default
title: API Reference
permalink: /api/
nav_order: 2
has_children: true
has_toc: false
---

# API Reference

Welcome to the Allez API Reference. Our APIs provide comprehensive access to on-chain data and analytics for various protocols in the Solana ecosystem.

- [Overview](#overview)
- [Authentication](#authentication-scheme)
- [Rate limits](#rate-limits)
- [Response format](#response-format)
- [Error handling](#error-handling)
- [Support](#support)

## Overview

The Allez API suite offers a collection of endpoints designed to help you integrate protocol data into your applications, dashboards, and analytics tools. Our APIs are built with performance and reliability in mind, providing real-time and historical data access.

| API | Description | Status |
|-----|-------------|---------|
| [Kamino](/api/kamino) | Access comprehensive data about the Kamino protocol, including fees, revenue,  information | Testing |
| [Prices](/api/prices) | Access price data aggregated from multiple sources | Dev |
| [Liquidity](/api/liquidity) | Access liquidity data aggregated from multiple sources | Dev |

## Base link
All endpoints are served over HTTPS, the base link is the following:
```
https://api.allez.xyz
```

Most of the endpoints available through our API do not require any authentication unless stated otherwise. For users wanting access to private endpoints with more granular and up to date data reach out to us on [X](https://x.com/AllezLabs) or by email [hey@allez.xyz](mailto:hey@allez.xyz) to get an API key.


## Authentication scheme
Each authenticated endpoint requires an API key in the header of every request you make.

The format for the API is the standard bearer token format with the following name:

```
X-ALLEZ-API-KEY: <your api key>
```
### Verify your API key is valid.

```
POST /auth/verify
```

#### Headers

| Name | Type | Required | Description |
|------|------|----------|-------------|
| X-ALLEZ-API-KEY | string | Yes | Your API key |

#### Response

```json
{
  "data": {
    "username": "string",
    "authenticated": true
  },
  "status": 200
}
``` 

## Rate Limits

There are currently no rate limits for the public api endpoints, depending on the load and usage this might change.

## Response Format

All API responses follow a consistent format:

```json
{
  "data": [...],
  "status": 200
}
```

## Error Handling

All endpoints may return error responses with the following structure:

```json
{
  "error": {
    "message": "string",
    "details": "string",
    "code": "integer"
  },
  "status": "integer"
}
```

## Support

For technical support or questions about our APIs:
- Email: [hey@allez.xyz](mailto:hey@allez.xyz)
- X: [AllezLabs](https://x.com/AllezLabs)