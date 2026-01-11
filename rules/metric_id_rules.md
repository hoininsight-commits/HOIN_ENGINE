# Metric ID Rules

## Format
`category.source.name` (lowercase, snake_case)

## Examples
*   `bonds.fred.us10y`
*   `stocks.yahoo.sp500`
*   `crypto.binance.btc_usdt`

## Constraints
*   Must be unique in `metrics` table.
*   Used as part of the Upsert Key in `metric_values`.
