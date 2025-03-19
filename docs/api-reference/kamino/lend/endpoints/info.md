---
layout: default
title: Info
parent: Kamino lend
permalink: /api/kamino/lend/info/
nav_order: 1
---

# Info

Get info about the reserves and markets in order to query data:
- [Market info](#markets)
- [Reserve info](#reserves)

The base link for all kamino lend data is 
```
https://api.allez.xyz/v1/kamino/lend
```

## Markets
```
GET info/markets
```

The endpoint returns a list of lending market objects with the following fields:

| Field | Type | Description |
|-------|------|-------------|
| `timestamp` | integer | Unix timestamp of when the data was recorded |
| `lending_market` | string | Public key of the lending market program |
| `lending_market_name` | string | Display name of the lending market (e.g., "Allez Restaking") |
| `reserve` | string | Public key of the reserve account |
| `token_address` | string | Public key of the token's mint address |
| `token_symbol` | string | Symbol of the token (e.g., "SOL") |
| `status_str` | string | Current status of the lending market (e.g., "active") |
| `asset_tier_str` | string | Tier classification of the asset (e.g., "regular") |
| `loan_to_value_f` | float | Loan-to-value ratio as a decimal (e.g., 0.65 for 65%) |
| `liquidation_threshold_f` | float | Liquidation threshold as a decimal (e.g., 0.75 for 75%) |
| `borrow_factor_f` | float | Borrow factor multiplier (e.g., 1.25) |

### Example Response

```json
[
  {
    "timestamp": 1742293508,
    "lending_market": "4P4NuGrt1xSTxfgy2wtWLUmssce6AEJnfgp3E6HugyNp",
    "lending_market_name": "Allez Restaking",
    "reserve": "4eoWVc8gtNDUsL12n5Xsfb3SvCtoV87ApZiMbShdp3Wx",
    "token_address": "So11111111111111111111111111111111111111112",
    "token_symbol": "SOL",
    "status_str": "active",
    "asset_tier_str": "regular",
    "loan_to_value_f": 0.65,
    "liquidation_threshold_f": 0.75,
    "borrow_factor_f": 1.25
  }
]
```



## Reserves
```
GET info/reserves
```

### Response

The endpoint returns a list of reserve objects with the following fields:

| Field | Type | Description |
|-------|------|-------------|
| `timestamp` | integer | Unix timestamp of when the data was recorded |
| `lending_market` | string | Public key of the lending market program |
| `lending_market_name` | string | Display name of the lending market (e.g., "Allez Restaking") |
| `reserve` | string | Public key of the reserve account |
| `token_address` | string | Public key of the token's mint address |
| `token_symbol` | string | Symbol of the token (e.g., "SOL") |
| `status_str` | string | Current status of the lending market (e.g., "active") |
| `asset_tier_str` | string | Tier classification of the asset (e.g., "regular") |
| `loan_to_value_f` | float | Loan-to-value ratio as a decimal (e.g., 0.65 for 65%) |
| `liquidation_threshold_f` | float | Liquidation threshold as a decimal (e.g., 0.75 for 75%) |
| `borrow_factor_f` | float | Borrow factor multiplier (e.g., 1.25) |

### Example Response

```json
[
  {
    "timestamp": 1742293508,
    "lending_market": "4P4NuGrt1xSTxfgy2wtWLUmssce6AEJnfgp3E6HugyNp",
    "lending_market_name": "Allez Restaking",
    "reserve": "4eoWVc8gtNDUsL12n5Xsfb3SvCtoV87ApZiMbShdp3Wx",
    "token_address": "So11111111111111111111111111111111111111112",
    "token_symbol": "SOL",
    "status_str": "active",
    "asset_tier_str": "regular",
    "loan_to_value_f": 0.65,
    "liquidation_threshold_f": 0.75,
    "borrow_factor_f": 1.25
  }
]
``` 