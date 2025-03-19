---
layout: default
title: Fees and revenue
parent: Kamino lend
permalink: /api/kamino/lend/fees-and-revenue/
nav_order: 2
---

# Fees & Revenue
- [Reserve revenue](#reserve-revenue)
- [Market revenue](#market-revenue)

## Reserve revenue

Retrieves hourly revenue data for a specific reserve in the Kamino lending protocol.

```
GET fees-and-revenue/reserves/{reserve}/hourly
```

### Path Parameters

| Parameter | Type   | Description                    |
|-----------|--------|--------------------------------|
| reserve   | string | The address of the reserve     |

### Query Parameters

| Parameter      | Type | Required | Description                                    |
|----------------|------|----------|------------------------------------------------|
| start_timestamp | integer | No | Unix timestamp for the start of the time range |
| end_timestamp   | integer | No | Unix timestamp for the end of the time range   |

### Response

Returns an array of hourly revenue data for the specified reserve.

```json
[
  {
    "timestamp_hour": "2025-03-15 05:00:00",
    "timestamp": 1742014800,
    "lending_market_name": "Main",
    "lending_market": "7u3HeHxYDLhnCoErrtycNokbQYbWGzLs6JSDqGAv5PfF",
    "reserve": "d4A2prbA2whesmvHaL88BH6Ewn5N4bTSU2Ze8P6Bc4Q",
    "token_address": "So11111111111111111111111111111111111111112",
    "token_symbol": "SOL",
    "interest_generated_usd_f": 2234.11853742556,
    "protocol_interest_revenue_usd_f": 335.049876089622,
    "liquidation_fees_usd_f": 0,
    "protocol_liquidation_fees_usd_f": 0,
    "origination_fee_usd_f": 0,
    "protocol_origination_fee_usd_f": 0
  }...
]
```

### Response Fields

| Field | Type | Description |
|-------|------|-------------|
| timestamp_hour | string | Hourly timestamp in ISO format |
| timestamp | integer | Unix timestamp |
| lending_market_name | string | Name of the lending market |
| lending_market | string | Address of the lending market |
| reserve | string | Address of the reserve |
| token_address | string | Address of the token |
| token_symbol | string | Symbol of the token |
| interest_generated_usd_f | number | Total interest generated in USD |
| protocol_interest_revenue_usd_f | number | Protocol's share of interest revenue in USD |
| liquidation_fees_usd_f | number | Total liquidation fees in USD |
| protocol_liquidation_fees_usd_f | number | Protocol's share of liquidation fees in USD |
| origination_fee_usd_f | number | Total origination fees in USD |
| protocol_origination_fee_usd_f | number | Protocol's share of origination fees in USD |

### Notes
- The endpoint returns up to 100 records per request
- All monetary values are in USD with floating-point precision
- Timestamps are in Unix format (seconds since epoch)

---

## Market revenue

Retrieves hourly revenue data for a specific lending market in the Kamino lending protocol.

```
GET fees-and-revenue/markets/{lending_market}/hourly
```

### Path Parameters

| Parameter | Type   | Description                    |
|-----------|--------|--------------------------------|
| lending_market | string | The address of the lending market |

### Query Parameters

| Parameter      | Type | Required | Description                                    |
|----------------|------|----------|------------------------------------------------|
| start_timestamp | integer | No | Unix timestamp for the start of the time range |
| end_timestamp   | integer | No | Unix timestamp for the end of the time range   |

### Response

Returns an array of hourly revenue data for the specified lending market.

```json
[
  {
    "timestamp_hour": "2025-03-18 09:00:00",
    "timestamp": 1742288400,
    "lending_market_name": "Main",
    "lending_market": "7u3HeHxYDLhnCoErrtycNokbQYbWGzLs6JSDqGAv5PfF",
    "interest_generated_usd_f": 4679.9669732065,
    "protocol_interest_revenue_usd_f": 973.11028530416,
    "liquidation_fees_usd_f": 0,
    "protocol_liquidation_fees_usd_f": 0,
    "origination_fee_usd_f": 0,
    "protocol_origination_fee_usd_f": 0
  }...
]
```

### Response Fields

| Field | Type | Description |
|-------|------|-------------|
| timestamp_hour | string | Hourly timestamp in ISO format |
| timestamp | integer | Unix timestamp |
| lending_market_name | string | Name of the lending market |
| lending_market | string | Address of the lending market |
| interest_generated_usd_f | number | Total interest generated in USD |
| protocol_interest_revenue_usd_f | number | Protocol's share of interest revenue in USD |
| liquidation_fees_usd_f | number | Total liquidation fees in USD |
| protocol_liquidation_fees_usd_f | number | Protocol's share of liquidation fees in USD |
| origination_fee_usd_f | number | Total origination fees in USD |
| protocol_origination_fee_usd_f | number | Protocol's share of origination fees in USD |

### Notes
- The endpoint returns up to 100 records per request
- All monetary values are in USD with floating-point precision
- Timestamps are in Unix format (seconds since epoch)

