---
layout: default
title: TVL Data
parent: Kamino
grand_parent: API Reference
nav_order: 2
permalink: /api-reference/kamino/tvl/
---

# TVL Data Endpoint

The TVL (Total Value Locked) endpoint provides historical and current data on the total value locked across Kamino protocol products.

## Endpoint

```http
https://api.allez.xyz/kamino/tvl
```

Retrieves daily TVL metrics for the Kamino protocol.

## Query Parameters

| Parameter | Type   | Required | Description |
|-----------|--------|----------|-------------|
| `start_date` | string | No | Filter results from this date onwards (format: YYYY-MM-DD) |
| `end_date` | string | No | Filter results up to this date (format: YYYY-MM-DD) |
| `product` | string | No | Filter by product: `all` (default), `lending`, or `liquidity` |
| `limit` | integer | No | Maximum number of days to return (default: 30, max: 365) |

## Response Fields

| Field | Description |
|-------|-------------|
| `day` | Date in YYYY-MM-DD format |
| `timestamp` | Unix timestamp for the day |
| `lending_tvl` | Total value locked in Klend (lending) in USD |
| `liquidity_tvl` | Total value locked in Kamino Liquidity in USD |
| `total_tvl` | Combined TVL across all Kamino products in USD |

## Example Request

```bash
curl -X GET "https://api.allez.xyz/kamino/tvl?product=lending&start_date=2023-12-01&end_date=2023-12-31" \
  -H "Authorization: Bearer YOUR_API_KEY"
```

## Notes

- Historical data is available from October 2023 onwards
- The endpoint data is refreshed daily and has a 1-day lag
- All monetary values are denominated in USD