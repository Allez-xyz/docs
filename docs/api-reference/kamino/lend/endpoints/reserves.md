---
layout: default
title: Reserves
parent: Kamino lend
permalink: /api-reference/kamino/lend/reserves/
nav_order: 4
---

# Reserves

## Latest reserves

Retrieves the latest snapshot of all reserves in the Kamino lending protocol.

```
GET /v1/kamino/lend/reserves/all/latest
```

### Response

Returns an array of the latest reserve data for all reserves in the protocol.

```json
[
  {
    "timestamp": 1742307911,
    "lending_market": "H6rHXmXoCQvq8Ue81MqNh7ow5ysPa1dSozwW3PU1dDH6",
    "reserve": "6gTJfuPHEg6uRAijRkMqNc9kan4sVZejKMxmvx2grT1p",
    "lending_market_name": "Jito",
    "token_symbol": "SOL",
    "available_amount_f": 211704.815866445,
    "available_amount_usd_f": 25845982.4450549,
    "supplied_amount_f": 925096.402832938,
    "supplied_amount_usd_f": 112940394.339859,
    "utilization_f": 0.7713,
    "borrow_apy_f": 0.0547562326721249,
    "supply_apy_f": 0.0376992320108351
  }...
]
```

### Response Fields

| Field | Type | Description |
|-------|------|-------------|
| timestamp | integer | Unix timestamp of the snapshot |
| lending_market | string | Address of the lending market |
| reserve | string | Address of the reserve |
| lending_market_name | string | Name of the lending market |
| token_symbol | string | Symbol of the token |
| available_amount_f | number | Available amount of the token |
| available_amount_usd_f | number | Available amount in USD |
| supplied_amount_f | number | Total amount supplied to the reserve |
| supplied_amount_usd_f | number | Total amount supplied in USD |
| utilization_f | number | Current utilization rate (0-1) |
| borrow_apy_f | number | Current borrow APY |
| supply_apy_f | number | Current supply APY |

### Notes
- All monetary values are in USD with floating-point precision
- Timestamps are in Unix format (seconds since epoch)
- APY values are represented as decimals (e.g., 0.05 for 5%)
- Utilization rate is represented as a decimal between 0 and 1

## Latest reserve

Retrieves the latest snapshot of a specific reserve in the Kamino lending protocol.

```
GET /v1/kamino/lend/reserves/{reserve}/latest
```

### Path Parameters

| Parameter | Type   | Description                    |
|-----------|--------|--------------------------------|
| reserve   | string | The address of the reserve     |

### Response

Returns the latest reserve data for the specified reserve.

```json
[
  {
    "timestamp": 1742307911,
    "lending_market": "H6rHXmXoCQvq8Ue81MqNh7ow5ysPa1dSozwW3PU1dDH6",
    "reserve": "6gTJfuPHEg6uRAijRkMqNc9kan4sVZejKMxmvx2grT1p",
    "lending_market_name": "Jito",
    "token_symbol": "SOL",
    "available_amount_f": 211704.815866445,
    "available_amount_usd_f": 25845982.4450549,
    "supplied_amount_f": 925096.402832938,
    "supplied_amount_usd_f": 112940394.339859,
    "utilization_f": 0.7713,
    "borrow_apy_f": 0.0547562326721249,
    "supply_apy_f": 0.0376992320108351
  }
]
```

### Response Fields

| Field | Type | Description |
|-------|------|-------------|
| timestamp | integer | Unix timestamp of the snapshot |
| lending_market | string | Address of the lending market |
| reserve | string | Address of the reserve |
| lending_market_name | string | Name of the lending market |
| token_symbol | string | Symbol of the token |
| available_amount_f | number | Available amount of the token |
| available_amount_usd_f | number | Available amount in USD |
| supplied_amount_f | number | Total amount supplied to the reserve |
| supplied_amount_usd_f | number | Total amount supplied in USD |
| utilization_f | number | Current utilization rate (0-1) |
| borrow_apy_f | number | Current borrow APY |
| supply_apy_f | number | Current supply APY |

### Notes
- All monetary values are in USD with floating-point precision
- Timestamps are in Unix format (seconds since epoch)
- APY values are represented as decimals (e.g., 0.05 for 5%)
- Utilization rate is represented as a decimal between 0 and 1
