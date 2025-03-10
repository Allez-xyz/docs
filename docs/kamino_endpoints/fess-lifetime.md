---
layout: default
title: Fees Lifetime
parent: Kamino
grand_parent: API Reference
nav_order: 1
permalink: /api-reference/kamino/fees-lifetime/
---

# Fees Lifetime Endpoint

The Fees Lifetime endpoint provides comprehensive data on Kamino protocol fees and revenue across all product lines, including Klend (lending) and Kamino Liquidity services.

## Endpoint

```http
GET https://api.allez.xyz/kamino/fees
```

Retrieves daily revenue and fee metrics for the Kamino protocol.

## Response Fields

| Field | Description |
|-------|-------------|
| `day` | Date in YYYY-MM-DD format |
| `timestamp` | Unix timestamp for the day |
| `KlendInterestFeesUSD` | Total interest fees collected by Klend in USD |
| `KlendInterestRevenueUSD` | Protocol revenue from interest fees in USD |
| `KlendLiquidationFeesUSD` | Total liquidation fees collected by Klend in USD |
| `KlendLiquidationRevenueUSD` | Protocol revenue from liquidation fees in USD |
| `KlendOriginationFeesUSD` | Total origination fees collected by Klend in USD |
| `KlendOriginationRevenueUSD` | Protocol revenue from origination fees in USD |
| `KlendFeesUSD` | Total fees collected by Klend (sum of interest, liquidation, and origination fees) in USD |
| `KlendRevenueUSD` | Total protocol revenue from Klend in USD |
| `KaminoLiquidityTvlUsd` | Total value locked in Kamino Liquidity in USD |
| `KaminoLiquidityFeesUsd` | Total fees collected by Kamino Liquidity in USD |
| `KaminoLiquidityRevenueUsd` | Protocol revenue from Kamino Liquidity in USD |
| `KaminoFeesUSD` | Total fees collected across all Kamino products (Klend + Kamino Liquidity) in USD |
| `KaminoRevenueUSD` | Total protocol revenue across all Kamino products in USD |

## Example Request

```bash
curl -X GET "https://api.allez.xyz/kamino/fees" 
```

## Notes

- Historical data is available from October 2023 onwards
- The endpoint data is refreshed daily and has a 1-day lag (i.e., yesterday's data is available today)
- All monetary values are denominated in USD