# Data dictionary

Every table represents simulated activity. File names ending in `.csv.gz` are gzip CSVs and can be passed directly to pandas `read_csv`. Market IDs are fictional integers. Calendar dates are UTC and week starts are Monday. Convert integer epoch seconds with `pd.to_datetime(series, unit="s", utc=True)`. Sort touchpoints and orders by time when building journeys. Event IDs are keys.

## Analyst tables

| File | Grain and key | Fields and conventions |
|---|---|---|
| `geos.csv` | One row per `geo_id` | `modeled_population` is the full simulated addressable pool, including people who have yet to enter. |
| `mmm_geo_daily.csv` | Date and geo | Orders, revenue cents, new orders, eligible audience, organic queries, competitor index, promotion depth, list price index, and spend cents, impressions and clicks for each paid channel. Indices are in basis points with 10,000 as 1.0. A 1,600 bps discount is 16%. |
| `mmm_geo_weekly.csv` | Monday week start and geo | Complete seven-day weeks. Outcomes, query counts and media counts sum. Eligible audience, competitor index, list price index and promotion depth are daily means. |
| `media_daily.csv` | Date, geo and channel | Platform spend cents, impressions, clicks, reach and `unit_price_microusd`. Reach is unique within that cell. Search bills per click. Social and display bill per impression. Unit price is USD millionths per billed event. Rounding occurs once per cell. |
| `transactions.csv.gz` | One row per `order_id` | Geo, `ordered_at_utc_s`, `customer_status` and revenue cents. New means first purchase in the simulated history, including warmup. Contains all orders and omits the private person identifier. |
| `paid_touchpoints.csv.gz` | One row per observed paid touch record, keyed by `touch_id` | Geo, channel and observed `visitor_id`. Impression time and click time may each be blank. If both are present, the click followed that impression. A click with a missing impression remains valid. |
| `organic_visits.csv.gz` | One tracked organic visit per visitor-day when captured | Observed `visitor_id`, geo and `visited_at_utc_s`. Organic visits are distinct from upstream query counts. |
| `mta_conversions.csv.gz` | One row per trackable `order_id` | `visitor_id` links to observed touches. Join to the transaction ledger on order ID to get timestamp and revenue. An order can be observed with no visible prior touch. The same underlying person can have more than one visitor ID over time. |
| `experiment_assignment.csv` | One row per geo | Pair ID, observed arm, channel and window dates. Baseline runs from `pre_start` through the day before `pulse_start`. Pulse and follow-up end dates are inclusive. `normal` has standard social delivery and `holdout` has zero social delivery during the pulse. |

## Evaluation media inputs

These files contain hypothetical media delivery with no outcome columns. Use them after freezing model choices. Their scenario labels identify the two sides of an estimand. They are outside the observed analyst tables.

| File | Grain | Use |
|---|---|---|
| `historical_media_weekly.csv` | Scenario, week and geo | Reference, each channel off, each channel at +20% pressure and all paid off. Contains exact realized spend, impressions and clicks for each policy. |
| `experiment_media_daily.csv` | Scenario, date and geo | Normal and holdout policies for all markets during the baseline, pulse and follow-up. Align model prediction history and forecast horizon before comparing their totals. |

## Sealed truth

| File | Grain | Use |
|---|---|---|
| `historical_geoweek.csv` | Scenario, week and geo | Replay outcomes, spend and outcomes for a fixed consenting, stable-ID audience. Stable-ID outcomes are a separate cohort, since captured MTA conversions can include rotating IDs and miss some orders. |
| `experiment_potential.csv` | Geo and date | Both normal and holdout orders, revenue, spend and stable-ID outcomes for the experiment window. |
| `estimands.csv` | One row per contrast | Period, channel, incremental orders, incremental revenue cents, incremental spend cents and gross revenue iROAS. Effects are higher pressure minus lower pressure. |
| `mechanism_checks.json` | Run-level flags | Generator-side comparisons of paired worlds. The separate read-side QA rechecks accounting and scenario consistency from exported data. |
