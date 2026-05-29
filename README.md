# Fixer

Fixer is a lightweight JSON API for real-time and historical foreign exchange rates and currency conversion. Built on top of European Central Bank reference rates plus 15+ additional data sources, Fixer supports 170+ world currencies and is delivered through the APILayer marketplace under a freemium subscription model.

- **APIs.yml:** [apis.yml](apis.yml)
- **Website:** https://fixer.io
- **Documentation:** https://docs.apilayer.com/fixer/docs/api-documentation
- **API Reference:** https://apilayer.com/marketplace/fixer-api
- **Parent provider:** APILayer

## Type and Tier

- **x-type:** company
- **x-tier:** 3 (bulk-registered from public-apis)
- **x-parent:** apilayer
- **Source:** [public-apis/public-apis](https://github.com/public-apis/public-apis) — category: Currency Exchange

## API Surface

| Method | Endpoint | Summary | Min Plan |
|---|---|---|---|
| GET | `/symbols` | List Supported Currency Symbols | Free |
| GET | `/latest` | Get Latest Exchange Rates | Free |
| GET | `/{date}` | Get Historical Exchange Rates | Free |
| GET | `/convert` | Convert Currency Amount | Basic |
| GET | `/timeseries` | Get Time Series Exchange Rates | Professional |
| GET | `/fluctuation` | Get Fluctuation Data | Professional Plus |

Base URL: `https://api.apilayer.com/fixer` &middot; Auth: `apikey` header.

## Artifacts

### Contract
- [openapi/fixer-openapi.yml](openapi/fixer-openapi.yml) — full OpenAPI 3.0 contract with all six operations and the success/error envelope.

### Schemas
- [json-schema/fixer-rates-schema.json](json-schema/fixer-rates-schema.json)
- [json-schema/fixer-symbols-schema.json](json-schema/fixer-symbols-schema.json)
- [json-schema/fixer-convert-schema.json](json-schema/fixer-convert-schema.json)
- [json-schema/fixer-timeseries-schema.json](json-schema/fixer-timeseries-schema.json)
- [json-schema/fixer-fluctuation-schema.json](json-schema/fixer-fluctuation-schema.json)
- [json-schema/fixer-error-schema.json](json-schema/fixer-error-schema.json)

### JSON Structure
- [json-structure/fixer-rates-structure.json](json-structure/fixer-rates-structure.json)
- [json-structure/fixer-symbols-structure.json](json-structure/fixer-symbols-structure.json)
- [json-structure/fixer-convert-structure.json](json-structure/fixer-convert-structure.json)
- [json-structure/fixer-timeseries-structure.json](json-structure/fixer-timeseries-structure.json)
- [json-structure/fixer-fluctuation-structure.json](json-structure/fixer-fluctuation-structure.json)

### JSON-LD Context
- [json-ld/fixer-context.jsonld](json-ld/fixer-context.jsonld) — semantic mapping for the Fixer response envelope.

### Examples
- [examples/fixer-getsymbols-example.json](examples/fixer-getsymbols-example.json)
- [examples/fixer-getlatest-example.json](examples/fixer-getlatest-example.json)
- [examples/fixer-gethistorical-example.json](examples/fixer-gethistorical-example.json)
- [examples/fixer-convertcurrency-example.json](examples/fixer-convertcurrency-example.json)
- [examples/fixer-gettimeseries-example.json](examples/fixer-gettimeseries-example.json)
- [examples/fixer-getfluctuation-example.json](examples/fixer-getfluctuation-example.json)

### Spectral Rules
- [rules/fixer-rules.yml](rules/fixer-rules.yml) — enforces operationId / summary / Title Case / Fixer envelope / `apikey` auth conventions.

### Naftiko Capabilities
- [capabilities/shared/fixer-shared.yaml](capabilities/shared/fixer-shared.yaml) — per-API operation primitives with plan gating.
- [capabilities/currency-conversion.yaml](capabilities/currency-conversion.yaml) — convert an amount with `/latest` fallback.
- [capabilities/treasury-reporting.yaml](capabilities/treasury-reporting.yaml) — daily window FX exposure report via `/timeseries` + `/fluctuation`.
- [capabilities/historical-rate-lookup.yaml](capabilities/historical-rate-lookup.yaml) — point-in-time rate lookup for reconciliation and audit.

### Vocabulary
- [vocabulary/fixer-vocabulary.yml](vocabulary/fixer-vocabulary.yml) — resources, endpoints, parameters, capabilities, commercial dimensions, and data sources.

### Commercial & FinOps
- [plans/fixer-plans-pricing.yml](plans/fixer-plans-pricing.yml) — Free, Basic ($14.99), Professional ($59.99), Professional Plus ($99.99), Enterprise (custom).
- [rate-limits/fixer-rate-limits.yml](rate-limits/fixer-rate-limits.yml) — monthly quotas, overage policy, freshness cadence.
- [finops/fixer-finops.yml](finops/fixer-finops.yml) — FOCUS mapping, allocation tags, optimization plays.

## Plan and Feature Gating

| Plan | Price (mo) | Requests/mo | Refresh | HTTPS | Base Switching | /convert | /timeseries | /fluctuation |
|---|---|---|---|---|---|---|---|---|
| Free | $0 | 100 | Hourly | No | No | No | No | No |
| Basic | $14.99 | 10,000 | Hourly | Yes | Yes | Yes | No | No |
| Professional | $59.99 | 100,000 | 10-min | Yes | Yes | Yes | Yes | No |
| Professional Plus | $99.99 | 500,000 | 60-sec | Yes | Yes | Yes | Yes | Yes |
| Enterprise | Custom | Volume | 60-sec | Yes | Yes | Yes | Yes | Yes |

Overage pricing per request: Basic $0.005996 &middot; Professional $0.0023996 &middot; Professional Plus $0.00079992 &middot; Enterprise negotiated. Annual billing offers ~15% effective savings.

## Tags

Currency Exchange, Foreign Exchange, FX, Forex, ECB, Conversion, Historical Rates, Time Series, Fluctuation, APILayer, Public APIs

## Timestamps

- **Created:** 2026-05-28
- **Modified:** 2026-05-29

## Maintainers

- **Kin Lane** — kin@apievangelist.com
